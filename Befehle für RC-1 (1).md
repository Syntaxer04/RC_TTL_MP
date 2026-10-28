Befehle für RC-1  
00AAABBB - IMOV8  
	- Bewegt Inhalt A nach speicher B in 8 Bit  
	AAA: Erster Speicherpunkt  
	BBB: Zweiter Speicherpunkt  
11dscznx aaaaaaaa aaaaaaaa - IGOTO  
	- Springt zu den angegebenen Speicherpunkt mit             
	   PC, kann auch mit Konditionen springen  
	d: Ziel (0=M, 1=J)  
	s: Sign  
	c: Carry  
	z: Zero  
	n: not Zero  
	x: Keine Konditioneller Sprung.   
01rddddd - ISETAB  
	- Lädt Zahlen von -16. bis +15 in entweder A oder B   
	   Register  
	r: Register (1: A, 0: B)  
	ddddd: 5-Bit Wert, sign extended auf 8 Bit  
10110000 - IINC16  
	- inkrementiert das XY-Register um 1  
	XY <- XY +1  
	xxxx: unbenutzt   
10100SDD - IMOV16  
	- Bewegt den Inhalt eines 16 Bit Registers in ein anderes 16 Bit Register  
	S:	0 - XY  
		1 - J  
	DD:	00 XY  
		01 J  
		10 M  
1000rfff - IALU  
	- Führt Befehle auf der ALU aus, ergo   
	 kombinatorische mathematik  
	r: Ziel (1:D,0:A)  
	fff: 	000 - unbenutzt  
		001 - ADD  
		010 - INC (8 Bit)  
		011 - AND  
		100 - OR  
		101 - XOR  
		110 - NOT  
		111 - SHL ( Circular Shift )  
100100DD - ILOAD  
	- Lädt einen Wert aus einer festgelegten Speicheradresse auf ein beliebiges Register  
	DD:	00 - A  
		01 - B  
		10 - C  
		11 - D  
100110DD - ISTORE  
	- Speichert einen Wert aus einem beliebigen Register an einer festgelegten Speicheradresse  
	DD:	00 - A  
		01 - B  
		10 - C  
		11 - D  
100101DD - OUT  
	- Gibt den Wert eines beliebigen Registers auf zwei Sieben-Segment Anzeigen durch ein spezielles Anzeigeregister aus.  
	DD:	00 - A  
		01 - B  
		10 - C  
		11 - D  
10011100 - HALT  
	- Quasi ein NMI. Setzt ein Register, das den Takt anhält, bis eine externe Quelle den Takt wiederherstellt. Günstig für komplexe externe Peripherie   
  
10011101 - WAIT  
	- Ein Maskable Interrupt. Die CPU wartet einen vollständigen Sequencer Zyklus ab (40 Schritte), und macht dann weiter. Da es auf zum warten benutzt werden kann, wird er hier als WAIT bezeichnet. Jetzige (Simulations-) Geschwindigkeiten mögen es jetzt noch nicht benötigen, könnte aber trotzdem sinnvoll sein.  
10011111 - CPUFORK ( Oder auch nur FORK() )
	- Lässt eine CPU einer anderen CPU an einer vorbestimmten Adresse starten. Diese Adresse wird durch das M Register definiert. Bislang sind es nur zwei CPUs, bedeutet der Befehl ist quasi einmalig, da die CPU bis jetzt nur einmal verwendbar ist

	