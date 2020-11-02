## DOCUMENTATION

- [Inheritance](https://www.geeksforgeeks.org/inheritance-in-java/)
- [Polymorphism](https://www.geeksforgeeks.org/polymorphism-in-java/)
- [Polymorphism - W3Schools](https://www.w3schools.com/java/java_polymorphism.asp)
- [Polymorphism vs Inheritance](https://www.geeksforgeeks.org/difference-between-inheritance-and-polymorphism)


# EXERCISES

> Definiți clasa Employee (angajat) derivată clasa Person prezentată, având câmpul suplimentar salary. Introduceți de la tastatură 5 obiecte de tip Employee într-un tablou. Căutați și afișați angajatul cu salariul cel mai mare.

```
// Person.java
public class Person {
    protected String name;
    protected String address;
    protected int age;


    public Person(String name, String address, int age){
        this.name = name;
        this.address= address;
        this.age = age;
    }

    public String whoAmI(){
        return "I'm a person";
    }

    @Override
    public String toString() {
        return "Person [address=" + address + ", age=" + age + ", name=" + name + "]";
    }
   
}

//Angajat.java
public class Angajat extends Person {
    protected int salary;

    public Angajat(String name,  String address, int age, int salary){   
        super(name, address, age);
        this.salary = salary;
    }

	@Override
	public String toString() {
        return "Angajat [salary=" + salary + "]" + super.toString();
	} 
}

// main()
	Scanner sc = new Scanner(System.in);
    int n = sc.nextInt();
    sc.nextLine();
    Angajat tab[] = new Angajat[n];
    
    for(int i=0; i<tab.length; i++){
	    System.out.println("Introduceti numele: ");
        String nume = sc.nextLine();
        System.out.println("Introduceti adresa: ");
        String adresa = sc.nextLine();
        System.out.println("Introduceti varsta: ");
        Integer varsta = sc.nextInt();
        sc.nextLine();
        System.out.println("Introduceti salariul: ");
        Integer salary = sc.nextInt();
        sc.nextLine();
        Angajat angajat = new Angajat(nume, adresa, varsta, salary);
        tab[i]= angajat;
	  }

	Angajat angajatulCuCelMaiMareSalariu = tab[0];
    for (Angajat angajat:tab){
		if(angajat.salary>angajatulCuCelMaiMareSalariu.salary){
			angajatulCuCelMaiMareSalariu = angajat;
        }
    }
	System.out.println(angajatulCuCelMaiMareSalariu);
```
