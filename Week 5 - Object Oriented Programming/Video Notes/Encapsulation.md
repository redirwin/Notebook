### Access Modifiers
-   **public** - accessible everywhere
    
-   **private** - only accessible within the class itself
    
-   **protected** - accessible within the class, other classes in the same package, and all subclasses
    
-   **No Modifier** - same as protected but not accessible in a subclass in a different package

```java
    public class Student {
    

      static int numberOfStudents;
    
      private String firstName;  // creating blueprint, don't assign value
      private String lastName;
      private String phoneNumber;
      private int gradeLevel;
    
    
      public Student() {} // overloaded version makes this available instead of Java's default
      
    
      /*
       * Constructors
       */
    
      public Student(String firstName, String lastName) {
      	this.firstName = firstName;
      	this.lastName = lastName;
      }
      
      public Student(String firstName, String lastName, String phoneNumber, int gradeLevel) {
      	this.firstName = firstName; // 'this' inside a class represents the specific instance
      	this.lastName = lastName;
      	this.phoneNumber = phoneNumber;
      	this.gradeLevel = gradeLevel;
      }
      
    
      /*
       * Public Methods
       */
    
      public void introduce() {
      	System.out.println("Hello, my name is " + firstName + " " + lastName);
      	System.out.println("I am in grade " + gradeLevel);
      	System.out.println("My phone number is " + phoneNumber);
      }
    
      /*
       * Private Methods
       */ 
    
      private boolean checkLength(String str, int length) {
      	return str.length() > length;
      }
    
    
      /*
       * GETTERS & SETTERS (Accessors & Mutators)
       */
    
      public void setFirstName(String firstName) {
      	if(checkLength(firstName, 1)) {
      		this.firstName = firstName;
      	}	    
    }
    
      public String getFirstName() {
      	return firstName;
      }
    
      public void setLastName(String lastName) {
      	if (checkLength(lastName, 1)) {
      		this.lastName = lastName;
      	}
      }
    
      public String getLastName() {
      	return lastName;
      }
    
      public void setPhoneNumber(String phoneNumber) {
      	if (checkLength(phoneNumber, 9) {
      		this.phoneNumber = phoneNumber;
      	}
      }
    
      public String getPhoneNumber() {
      	return  phoneNumber;
      }
    
      public void setGradeLevel(int gradeLevel) {
      	this.gradeLevel = gradeLevel;
      }
    
      public int getGradeLevel() {
      	return gradeLevel;
      }    
    }
```
```java    
    public static void main(String[] args) {
    
    
      Student student = new Student();
      student.setFirstName("S");	
      System.out.println(student.getFirstName());
      
      // prints: null    
    }
   ```
 ```java   
    public static void main(String[] args) {
    
      student.setFirstName("Sally");	
      System.out.println(student.getFirstName());
      
      // prints: Sally    
    }
   ```
  ```java
    
    public static void main(String[] args) {
    
      student.setFirstName("Dave");
      student.setPhoneNumber("555-555-5555");
      student.introduce();
    
      // prints:
      // Hello, my name is Dave null
      // I am in grade 0;
      // My phone number is 555-555-5555    
    }
   ```
    

### Rectangle Example

```java
public class Rectangle {

	private double width;
	private double length;
	private double area;

	public Rectangle(double width, double length) {
		this.width = width;
		this.length = length;
		this.area = width * length;
	}

	// Getters & Setters

	public double getWidth() {
		return width;
	}

	public void setWidth(double width) {
		this.width = width;
		area = width * length;
	}

	public double getLength() {
		return Length;
	}

	public void setLength(double length) {
		this.length = length;
		area = width * length;
	}

}
```
```java
public static void main(String[] args) {

	Rectangle rec = new Rectangle(10.0, 15.0);
	System.out.println(rec.getArea());

}

// prints: 150.0
```
```java
public static void main(String[] args) {

	Rectangle rec = new Rectangle(10.0, 15.0);
	rec.setLength(10.0);
	System.out.println(rec.getArea());

}

// prints: 100.0
```