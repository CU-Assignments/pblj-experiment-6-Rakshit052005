[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/pAwhWXY5)

Que 1
import java.util.*;

class Employee {
    String name;
    int age;
    double salary;

    Employee(String name, int age, double salary) {
        this.name = name;
        this.age = age;
        this.salary = salary;
    }

    @Override
    public String toString() {
        return name + " - " + age + " - " + salary;
    }
}

public class Main {
    public static void main(String[] args) {
        List<Employee> employees = Arrays.asList(
            new Employee("Alice", 30, 50000),
            new Employee("Bob", 25, 45000),
            new Employee("Charlie", 35, 70000)
        );

        employees.sort(Comparator.comparing((Employee e) -> e.name)
                                 .thenComparing(e -> e.age)
                                 .thenComparing(e -> e.salary));

        employees.forEach(System.out::println);
    }
}


Que 2

import java.util.*;
import java.util.stream.*;

class Student {
    String name;
    double marks;

    Student(String name, double marks) {
        this.name = name;
        this.marks = marks;
    }

    public String getName() {
        return name;
    }

    public double getMarks() {
        return marks;
    }
}

public class Main {
    public static void main(String[] args) {
        List<Student> students = Arrays.asList(
            new Student("Alice", 80),
            new Student("Bob", 70),
            new Student("Charlie", 85),
            new Student("David", 90),
            new Student("Eve", 60)
        );

        students.stream()
                .filter(s -> s.getMarks() > 75)  
                .sorted(Comparator.comparingDouble(Student::getMarks))  
                .forEach(s -> System.out.println(s.getName()));  
    }
}
