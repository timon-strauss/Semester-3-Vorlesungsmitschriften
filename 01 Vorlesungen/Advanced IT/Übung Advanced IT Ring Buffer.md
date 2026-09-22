---
Dozent: Pagnia
tags:
- übung
---

# Ringbuffer Implementierung

```Java
Class Ringbuffer{
	private int ctr;
	private int nextfree;
	private int nextfull;
	
	private String[] buffer = new String[4];
	
	public void append(String s){
		if(ctr == buffer.Length) { //warten }
		
		/* kritischer Abschnitt */
		buffer[nextfree] = s;
		ctr++;
		/* kritischer Abschnitt */
		
		nextfree = (nextfree + 1) % buffer.Length; //modulo für ring
	}
	
	public String remove(){
		if(ctr == 0) { //warten }
			
		s = buffer[nextfull];
		
		/* kritischer Abschnitt */
		ctr--;
		nextfull = (nextfull + 1) % buffer.Length;
		/* kritischer Abschnitt */
		
		return s;
	}
}
```

# Mit Semaphore 

```Java
Class Ringbuffer{
	private int nextfree;
	private int nextfull;
	
	private String[] buffer = new String[4];
	
	Semaphore mutex = new Semaphore(1, true);
	Semaphore free = new Semaphore(buffer.Length, true)
	Semaphore full = new Semaphore(buffer.Length, true)
	
	public void append(String s){
		mutex.acquire(); //gegenseitiger ausschluss für Zugriff kritischer Daten
		free.acquire(); //Nutzt Semaphore Counter für Anzahl freier Daten
		
		buffer[nextfree] = s;
		nextfree = (nextfree + 1) % buffer.Length;
		
		full.release(); //Datensatz hinzugefügt => full counter erhöhen
		mutex.release();
	}
	
	public String remove(){
		mutex.acquire();
		full.acquire(); //Nutzt Semaphore Counter für Anzahl besetzter Daten
			
		s = buffer[nextfull];
		nextfull = (nextfull + 1) % buffer.Length;
		
		free.release(); //Datensatz gelöscht => free counter erhöhen
		mutex.release();
		return s;
	}
}
```

# Synchronisationsgraph

E: Erzeuger
V: Verbraucher

- Für jeden Verbraucher muss 1 Erzeuger gelaufen sein
- Für jeden Erzeuger nach 4 muss 1 Verbraucher gelaufen sein

Beobachtung: Der gegenseitige Ausschluss ist hinfällig, da:
- nextfree und nextfull sind nie gleich 
- außer wenn der buffer voll oder leer ist => da wird aber nicht erzeugt/verbraucht

![[Screenshot 2026-09-22 at 10.43.32.png]]