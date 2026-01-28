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
public class ArraySum {
    static int calculateSum(int[] arr) {
        int sum = 0;
        for (int i = 0; i < arr.length; i++) {
            sum += arr[i];
        }
        return sum;
    }
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 40, 50};
        int result = calculateSum(numbers);
        System.out.println("Sum of array elements: " + result);
    }
}
import java.util.Scanner;
public class SmallestPositiveRoot {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter coefficients a, b, and c: ");
        int a = sc.nextInt();
        int b = sc.nextInt();
        int c = sc.nextInt();
        double discriminant = b * b - 4 * a * c;
        if (discriminant >= 0) {
            double root1 = (-b + Math.sqrt(discriminant)) / (2 * a);
            double root2 = (-b - Math.sqrt(discriminant)) / (2 * a);
            if (root1 > 0 && root2 > 0) {
                System.out.println("The smallest positive root is: " + Math.min(root1, root2));
            } else if (root1 > 0) {
                System.out.println("The smallest positive root is: " + root1);
            } else if (root2 > 0) {
                System.out.println("The smallest positive root is: " + root2);
            } else {
                System.out.println("No positive roots.");
            }
        } else {
            System.out.println("No real roots.");
        }
        sc.close();
    }
}

import java.util.Scanner;
public class CheckCharacter {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a character: ");
        char ch = sc.next().charAt(0);
        if (Character.isLetter(ch)) {
            System.out.println("It is a Letter.");
        }
        else if (Character.isDigit(ch)) {
            System.out.println("It is a Digit.");
        }
        else if (Character.isWhitespace(ch)) {
            System.out.println("It is a Whitespace.");
        }
        else {
            System.out.println("Other character.");
        }
        sc.close();
    }
}

