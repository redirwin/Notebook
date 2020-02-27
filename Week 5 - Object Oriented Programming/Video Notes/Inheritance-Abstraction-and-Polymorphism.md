## Inheritance, Abstraction, and Polymorphism

```java
public class InheritanceAbstractionPolymorphism {

	public static void main(String[] args) {

		Employee salary = new SalariedEmployee("Tom", "Sawyer", 2500.00);
		Employee hourly = new HourlyEmployee("Tim", "Smith", 15.00, 75.5);
		Employee manager = new Manager("Rob", "Lincoln", 4500.00, 15.5);

		System.out.println(salary.calculatePay());
		System.out.println(hourly.calculatePay());
		System.out.println(manager.calculatePay());

	}

}
```
```java
public abstract class Employee {

	private String firstName;
	private String lastName;
	private double pay;
	private String address;
	private String reportsTo;

	public Employee(String firstName, String lastName, double pay) {
		this.firstName = firstName;
		this.lastName = lastName;
		this.pay = pay;
	}

	public abstract double calculatePay(); // polymorphic, must be implemented in inheriting classes

	public String getInformation() {
		return "Name: " + firstName + " " lastName
						+ "\\nReports to: " + reportsTo
						+ "\\nAddress: " + address;
	}

	// Getters & Setters

	........
	
}
```
```java
public class SalariedEmployee extends Employee {

	public SalariedEmployee(String firstName, String lastName, double pay) {
		super(firstName, lastName, pay); // super refers to the class we're inheriting from
	}

	@Override
	public double calculatePay() {
		return getPay() * 80;
	}

}
```
```java
public class HourlyEmployee extends Employee {

	private double hoursWorked;

	public HourlyEmployee(String firstName, String lastName, double pay, double hoursWorked) {
		super(firstName, lastName, pay); 
		this.hoursWorked = hoursWorked;
	}

	@Override
	public double calculatePay() {
		return getPay() * hoursWorked;
	}

}
```
```java
public class Manager extends Employee {

	private double bonusPercentage;

	public Manager(String firstName, String lastName, double pay, double bonusPercentage) {
		super(firstName, lastName, pay); 
		this.bonusPercentage = bonusPercentage;
	}

	@Override
	public double calculatePay() {
		return getPay() * 80 * bonusePercentage;
	}

}
```