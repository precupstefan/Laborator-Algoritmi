## DOCUMENTATION

- [Exceptions in Java](https://www.geeksforgeeks.org/exceptions-in-java/)
- [BufferedReader class](https://www.geeksforgeeks.org/java-io-bufferedreader-class-java/)
- [DataInputStream](https://www.javatpoint.com/java-datainputstream-class)
- [DataOutputStream](https://www.javatpoint.com/java-dataoutputstream-class)
- [Scanner class](https://www.geeksforgeeks.org/scanner-class-in-java/)

# EXERCISES

> Să se scrie un program care cere introducerea numelui utilizatorului și afișează pe ecran mesajul Hello urmat de numele introdus (afișare-citire-afișare).

```
Scanner sc= new Scanner(System.in);
System.out.println("Introduceti numele: "); String nume = sc.nextLine();
System.out.println("Hello, " + nume);
sc.close();
```

> Sa se scrie un program care cere introducerea varstei utilizatorului.
> Dacă vârsta introdusă depășește 100 să afișeze mesajul "Ești bătrân!",  altfel să afișeze "Ești tânăr!".

```  
Scanner sc = new Scanner(System.in);  
System.out.println("Introduceti varsta: ");  
//int varsta=sc.nextInt();  
String str = sc.nextLine();  
try {  
Integer varsta = Integer.parseInt(str);  
if (varsta > 100) System.out.println("Esti batran!");  
else System.out.println("Esti tanar!");  
} catch (Exception e1) {  
System.out.println("Nu ati dat un numar");  
}
```

> Să se implementeze un program care citește dintr-un fișier într-un  tablou de tip String numele studenților din semigrupă. Sortați în ordine alfabetică tabloul (v. metoda sort a clasei Arrays). Atenție, șirurile trebuie transformate după citire astfel încât toate literele să fie mici sau toate mari (v. toLowerCase sau toUpperCase din String).
```
String nume[] = new String[10];
int i=0;
FileInputStream f = null;
try {
	f = new FileInputStream("NumeStudenti");
} catch (FileNotFoundException ex) {
	ex.printStackTrace();
}
Scanner sc = new Scanner(f);
while (sc.hasNext()) {
	nume[i]=sc.nextLine().toUpperCase();
	i++;
}
Arrays.sort(nume);
for (String j:nume) {
	System.out.println(j);
}
sc.close();
```


