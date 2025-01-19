#Q3 Erstellt am 19.01.2025 um 21:04 Uhr

---

- **Synchrone Sockets**: Blockierend; der Thread wartet, bis eine Operation abgeschlossen ist. Einfach, aber ineffizient bei vielen Verbindungen.
- **Asynchrone Sockets**: Nicht-blockierend; Operationen laufen im Hintergrund, und das Programm reagiert auf Ereignisse. Komplexer, aber skalierbarer.

### **Klasse `TcpClient`**

- **Prinzip:** Höher abstrahierte Klasse für TCP-Verbindungen (Client-seitig).
- **Flexibilität:** Einfacher zu verwenden, da viele Details der Socket-Programmierung (z. B. Verbindungsaufbau) abstrahiert werden.
- **Verwendung:** Zum Aufbau von Client-Verbindungen zu einem Server, um Daten zu senden und zu empfangen.


### **Klasse `TcpListener`**

- **Prinzip:** Höher abstrahierte Klasse für TCP-Server.
- **Flexibilität:** Abstrahiert die Konfiguration eines Sockets zum Abhören von eingehenden Verbindungen.
- **Verwendung:** Wird verwendet, um Verbindungen von Clients zu akzeptieren, ideal für serverseitige Anwendungen.