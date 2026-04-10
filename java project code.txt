package Project;
import java.util.*;
class Student {
    int id;
    String name;
    List<String> subjects;

    Student(int id, String name) {
        this.id = id;
        this.name = name;
        this.subjects = new ArrayList<>();
    }

    void enroll(String subject) {
        subjects.add(subject);
    }

    void display() {
        System.out.println("ID: " + id);
        System.out.println("Name: " + name);
        System.out.println("Subjects: " + subjects);
        System.out.println("----------------------");
    }
}

public class CourseRegistrationSystem {
	static ArrayList<Student> students = new ArrayList<>();

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        while (true) {
            System.out.println("\n1. Add Student");
            System.out.println("2. Enroll Subject");
            System.out.println("3. View Records");
            System.out.println("4. Exit");

            System.out.print("Enter choice: ");
            int ch = sc.nextInt();

            switch (ch) {
                case 1:
                    System.out.print("Enter ID: ");
                    int id = sc.nextInt();
                    sc.nextLine();

                    System.out.print("Enter Name: ");
                    String name = sc.nextLine();

                    students.add(new Student(id, name));
                    System.out.println("Student added!");
                    break;

                case 2:
                    System.out.print("Enter Student ID: ");
                    int sid = sc.nextInt();
                    sc.nextLine();

                    for (Student s : students) {
                        if (s.id == sid) {
                            System.out.print("Enter Subject: ");
                            String sub = sc.nextLine();
                            s.enroll(sub);
                            System.out.println("Subject enrolled!");
                        }
                    }
                    break;

                case 3:
                    for (Student s : students) {
                        s.display();
                    }
                    break;

                case 4:
                    System.exit(0);
            }
        }
    }
}
