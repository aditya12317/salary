EXPLANATION:                                                                                                                                                                                                 This Java program is a simple yet effective command-line application designed to display employee details based on a user-provided employee ID. At its core, it consists of a Project1 class that handles user input and program logic, and an Employee class that serves as a blueprint for employee data, encapsulating properties such as ID, name, department, designation, and salary. When the program is executed, it expects an employee ID to be passed as a command-line argument. It then parses this input and searches through a predefined array of Employee objects. If a match is found, it neatly displays the employee's information in a structured tabular format using System.out.printf; otherwise, it notifies the user that the employee does not exist. The program emphasizes fundamental object-oriented programming principles such as encapsulation, data abstraction, and modular design. It also introduces array iteration and input validation. This application can be expanded further to include more dynamic features like accepting data from user input at runtime, connecting to a database, or using a graphical user interface (GUI) for a better user experience. Overall, it serves as a strong foundation for beginners learning Java, especially in understanding how classes and objects work together to form real-world applications.
CODE:                                                                                                                                                                                                                public class Project1 {
        public static void main(String[] args) {
            if (args.length == 0) {
                System.out.println("Please provide an employee ID.");
                return;
            }

            int empId = Integer.parseInt(args[0]);
            printEmployeeDetails(empId);
        }

        public static void printEmployeeDetails(int empId) {
            // Sample employee data
            Employee[] employees = {
                new Employee(1001, "Rahul", "Acct", "Clerk", 29000),
                new Employee(1002, "Priya", "HR", "Manager", 55000),
                new Employee(1003, "Sam", "IT", "Developer", 40000)
            };

            for (Employee emp : employees) {
                if (emp.getId() == empId) {
                    System.out.printf("Emp No.    Emp Name    Department    Designation    Salary%n");
                    System.out.printf("%-10d  %-10s  %-10s  %-10s  %d%n", emp.getId(), emp.getName(), emp.getDepartment(), emp.getDesignation(), emp.getSalary());
                    return;
                }
            }

            System.out.printf("There is no employee with empid : %d%n", empId);
        }
    }

    class Employee {
        private int id;
        private String name;
        private String department;
        private String designation;
        private int salary;

        public Employee(int id, String name, String department, String designation, int salary) {
            this.id = id;
            this.name = name;
            this.department = department;
            this.designation = designation;
            this.salary = salary;
        }

        public int getId() {
            return id;
        }

        public String getName() {
            return name;
        }

        public String getDepartment() {
            return department;
        }

        public String getDesignation() {
            return designation;
        }

        public int getSalary() {
            return salary;
        }
    }
