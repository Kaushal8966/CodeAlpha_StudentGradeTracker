# CodeAlpha_StudentGradeTracker
import java.util.ArrayList;
import java.util.Scanner;

public class StudentGradeTracker1 {
    public static void main(String[] args) {
        ArrayList<Double> grades = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);
        
        //System.out.println("Enter student grades :");
        
        while (true) {
            System.out.print("Enter grade: ");
            double grade = scanner.nextDouble();
            if (grade < 0) {
                break;
            }
            grades.add(grade);
        }
        
        if (grades.isEmpty()) {
            System.out.println("No grades entered.");
        } else {
            double total = 0;
            double highest = Double.MIN_VALUE;
            double lowest = Double.MAX_VALUE;
            
            for (double grade : grades) {
                total += grade;
                if (grade > highest) {
                    highest = grade;
                }
                if (grade < lowest) {
                    lowest = grade;
                }
            }
            
            double average = total / grades.size();
            
            System.out.printf("Average grade: %.2f%n", average);
            System.out.printf("Highest grade: %.2f%n", highest);
            System.out.printf("Lowest grade: %.2f%n", lowest);
        }
        
        scanner.close();
    }
}
