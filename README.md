package studentmanagementsystem;

import java.util.Scanner;

public class StudentManagementSystem {

    // Student class
    static class Student {
        String id;
        String name;
        String course;
        int marks;
        String grade; // use String for clarity

        Student(String id, String name, String course, int marks) {
            this.id = id;
            this.name = name;
            this.course = course;
            this.marks = marks;
            this.grade = calculateGrade(marks); // calculate grade immediately
        }

        // Calculate grade based on marks
        private String calculateGrade(int marks) {
            if (marks >= 70) return "A";
            else if (marks >= 60) return "B";
            else if (marks >= 50) return "C";
            else if (marks >= 40) return "D";
            else return "F";
        }

        // Display student details neatly
        public void display() {
            System.out.println("\n========== STUDENT DETAILS ==========");
            System.out.println("Student ID : " + id);
            System.out.println("Name       : " + name);
            System.out.println("Course     : " + course);
            System.out.println("Marks      : " + marks);
            System.out.println("Grade      : " + grade);
            System.out.println("====================================");
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter Student ID: ");
        String id = scanner.nextLine();

        System.out.print("Enter Name: ");
        String name = scanner.nextLine();

        System.out.print("Enter Course: ");
        String course = scanner.nextLine();

        System.out.print("Enter Marks: ");
        int marks = scanner.nextInt();

        // Create student object
        Student student = new Student(id, name, course, marks);

        // Display student details
        student.display();

        scanner.close();
    }
}
