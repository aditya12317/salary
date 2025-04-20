    public class Project1 {
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
