import java.io.PrintWriter;
import java.util.Scanner;
public class Main {
    public static void main(String[] args) throws Exception {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter numbers separated by comma:");
        String data = sc.nextLine();
        Scanner fileScanner = new Scanner(data);
        fileScanner.useDelimiter(",");
        int highest = Integer.MIN_VALUE;
        int sumOfSeries = 0;
        while (fileScanner.hasNextInt()) {
            int num = fileScanner.nextInt();
            sumOfSeries += num;
            if (num > highest) {
                highest = num;
            }
        }
        fileScanner.close();
        int naturalSum = highest * (highest + 1) / 2;
        PrintWriter pw = new PrintWriter(System.out);
        pw.println("Highest Number: " + highest);
        pw.println("Sum of Given Numbers: " + sumOfSeries);
        pw.println("Sum of Natural Numbers up to " + highest + ": " + naturalSum);
        pw.flush();
        pw.close();
        sc.close();
    }
}
