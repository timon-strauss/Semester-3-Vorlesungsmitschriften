---
Dozent: Pagnia
---

**warum BufferedReader**: Mehrere Pakete aus einer Message werden gepuffert
- kommunikation ist flüssiger

```Java
new BufferedReader( //Buffer für Nachrichtenstrom
	 new InputStreamReader( //Leser für die Bits am connection Input
		 conn.getInputStream() //Connection Input Stream holen
     ) 
)
```

**non persistant**: Beendung der Connection nach einer abgehandelten Abfrage

**Klausur**: Exception handling über Exception e

**Unterschied**: UDP und TCP
- TCP Verpackt selbst, UDP nicht
- TCP gibt Fehlerkontrolle, UDP nicht
- UDP gibt höhere Geschwindigkeit
- TCP ist connection orientiert, UDP nicht
- UDP kann viele Nachrichten bekommen, TCP braucht Verbindung

**private Ports**: irgendein freier port

