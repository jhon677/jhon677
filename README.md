import java.util.Scanner;

public class StudentEnrollment {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        // Input student information
        System.out.print("Enter Student Name: ");
        String studentName = input.nextLine();

        System.out.print("Enter Course: ");
        String course = input.nextLine();

        System.out.print("Enter Course Code: ");
        String courseCode = input.nextLine();

        int numberOfUnits;
        do {
            System.out.print("Enter Number of Units (Maximum 10): ");
            numberOfUnits = input.nextInt();
        } while (numberOfUnits <= 0 || numberOfUnits > 10);

        // Compute enrollment fee
        int feePerUnit = 1000;
        int totalEnrollmentFee = numberOfUnits * feePerUnit;

        // Output student name and total enrollment fee
        System.out.println("\nStudent Name: " + studentName);
        System.out.println("Total Enrollment Fee: " + totalEnrollmentFee);

        // Payment processing
        System.out.print("\nEnter Payment Amount: ");
        int paymentAmount = input.nextInt();

        if (paymentAmount == totalEnrollmentFee) {
            System.out.println("Fully Paid");
        } else if (paymentAmount < totalEnrollmentFee) {
            int amountDue = totalEnrollmentFee - paymentAmount;
            System.out.println("Partial Payment");
            System.out.println("Amount Paid: " + paymentAmount);
            System.out.println("Amount Due: " + amountDue);
        } else {
            System.out.println("Invalid Payment Amount");
        }

        input.close();
    }
}
