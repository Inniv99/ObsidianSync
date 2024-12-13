#Q3 #TW Erstellt am 13.12.2024 um 21:06 Uhr

---

##### Serial-Klasse

Zur Implementierung der [[RS232]] wird eine Wrapper Klasse `Serial` zu Verfügung gestellt:

![[Pasted image 20241213210919.png]]

Der Constructor `Serial()` erstellt ein Serial Object mit Kommunikationsport und gewollten [[Kommunikationsparameter RS-232]].

`open()` und `close()` geben Port frei und schließen ihn.
`dataAvailable()` ermittelt Empfangspuffer
`write()`-Methoden senden einzelne Bytes, ByteArrays oder Strings
`read()`-Method liest ein Byte, `readLine()` liest einen String mit `\n` Terminierung

##### Beispielprogramm: Loopback

```cs
using __Serial__; // Zur Nutzung der Klasse Serial und
 using System.IO.Ports; // der Angaben zu Stoppbits und Parität
 namespace Loopback
 {
    class Program
    {
        static void Main(string[] args)
        {
            // Gewünschter COM-Port mit den Kommunikationsparametern
            Serial s = new Serial("COM1", 9600, 8, StopBits.One, Parity.None);
            if ( s.open() ) // Öffnen des gewünschten COM-Ports
            { 
                // Übertragt ein Byte in einer Endlosschleife
                // und liest es per Loopback wieder ein
                byte value = 0x41;
                byte rcv = 0x00;
                while (true)
                {
                    s.write(value);
                    rcv = (byte)s.read();
                    Console.WriteLine("rcv = {0}", Convert.ToChar(rcv));
                }
            }
            else
                Console.WriteLine("COM-Port ist bereits belegt!");
            s.close();
        }
    }
 }
```

##### Beispielprogramm: [[XON-XOFF]]

###### Sender

```cs
using __Serial__; // Zur Nutzung der Klasse Serial und
using System.IO.Ports; // der Angaben zu Stoppbits und Parität
using System;
using System.Threading;

namespace SerialSender
{
    class Program
    {
        static void Main(string[] args)
        {
            // Gewünschter COM-Port mit den Kommunikationsparametern
            Serial serial = new Serial("COM1", 9600, 8, StopBits.One, Parity.None);
            const byte XOFF = 0x13;
            const byte XON = 0x11;

            if (serial.open()) // Öffnen des gewünschten COM-Ports
            {
                Console.WriteLine("COM-Port open");

                // Übertragt ein Byte in einer Endlosschleife
                // und liest es per Loopback wieder ein

                byte value = 0x41;
                byte rcv = 0x00; 

                while (true)
                {
                    rcv = (byte)serial.read();
                    
                    if (rcv == XON)
                    {
                        Console.Write("Write Message: ");
                        string toSend = Console.ReadLine();
                        serial.write(toSend + "\n");
                        Console.WriteLine($"Message sent. Code: {rcv}");
                        Thread.Sleep(1000);
                    } else
                    {
                        Console.WriteLine("XOFF received, sending terminated");
                    }

                    //Console.WriteLine("rcv = {0}", Convert.ToChar(rcv));

                }
            }
            else Console.WriteLine("COM-Port already in use");

            serial.close();
        }
    }
}

```

###### Empfänger

```cs
using __Serial__; // Zur Nutzung der Klasse Serial und
using System.IO.Ports; // der Angaben zu Stoppbits und Parität
using System;

namespace SerialReceive
{
    class Program
    {
        static void Main(string[] args)
        {
            const int bufferSize = 50;

            char[] receiveBuffer = new char[bufferSize];

            for (int i = 0; i < receiveBuffer.Length; i++)
            {
                receiveBuffer[i] = Convert.ToChar(0x00);
            }

            const byte XOFF = 0x13;
            const byte XON = 0x11;

            bool XOFF_Flag = true;

            // Gewünschter COM-Port mit den Kommunikationsparametern
            Serial serial = new Serial("COM1", 9600, 8, StopBits.One, Parity.None);

            if (serial.open()) // Öffnen des gewünschten COM-Ports
            {
                Console.WriteLine("COM-Port open");

                // Übertragt ein Byte in einer Endlosschleife
                // und liest es per Loopback wieder ein

                byte value = 0x41; 
                byte rcv = 0x00;

                int bufferCounter = 0;

                serial.write(XON);
                
                while (true)
                {

                    if (!XOFF_Flag)
                    {
                        serial.write(XON);

                        //if (bufferCounter == 0) Console.WriteLine("--- Ready to receive ---");
                        rcv = (byte)serial.read(); //Paused till received

                        if (bufferCounter >= receiveBuffer.Length)
                        {
                            Console.WriteLine(": Receivebuffer upper water mark reached ---");
                            XOFF_Flag = true;
                            serial.write(XOFF);
                            bufferCounter = 0;
                            continue;
                        }

                        receiveBuffer[bufferCounter] = Convert.ToChar(rcv);
                        bufferCounter++;


                        //Console.Write("c: {0}, rc: {1}", bufferCounter, receiveBuffer[bufferCounter - 1]);
                        Console.Write(receiveBuffer[bufferCounter - 1]);
                        if (serial.dataAvailable() == 0) bufferCounter = 0;
                    } else
                    {
                        Console.Write("XON senden? Y/N: ");

                        string ans = Console.ReadLine();

                        if (ans.ToLower() == "y")
                        {
                            XOFF_Flag = false;
                            serial.write(XON);
                        }
                    }

                }
            }
            else Console.WriteLine("COM-Port already in use");

            serial.close();
        }
    }
}

```