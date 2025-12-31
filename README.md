Maven Prime Number Projects
===========================

This repository contains two simple Java projects built using Apache Maven:

1. PrimeNumberProj - Checks if a given number is prime.
2. BtwPrimeNumber - Prints all prime numbers between two input numbers.

------------------------------------------------------------
Project 1: PrimeNumberProj
------------------------------------------------------------

Step 1: Create project
mvn archetype:generate -DgroupId=com.su2 -DartifactId=PrimeNumberProj -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false

Step 2: Change directory
cd PrimeNumberProj

Step 3: Edit App.java
Path: src/main/java/com/su2/App.java

Code:
package com.su2;
import java.util.Scanner;

public class App {
    public static boolean check_prime(int n) {
        if (n <= 1) return false;
        for (int i = 2; i <= Math.sqrt(n); i++) {
            if (n % i == 0) return false;
        }
        return true;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter a number:");
        int n = sc.nextInt();
        if (check_prime(n))
            System.out.println("Num = " + n + " is prime");
        else
            System.out.println("Num = " + n + " is NOT prime");
        sc.close();
    }
}

Step 4: Build project
mvn clean package

Step 5: Run project
mvn exec:java -Dexec.mainClass=com.su2.App

------------------------------------------------------------
Project 2: BtwPrimeNumber
------------------------------------------------------------

Step 1: Create project
mvn archetype:generate -DgroupId=com.su2 -DartifactId=BtwPrimeNumber -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false

Step 2: Change directory
cd BtwPrimeNumber

Step 3: Edit App.java
Path: src/main/java/com/su2/App.java

Code:
package com.su2;
import java.util.Scanner;

public class App {
    public static boolean isPrime(int n) {
        if (n <= 1) return false;
        if (n == 2) return true;
        if (n % 2 == 0) return false;
        for (int i = 3; i <= Math.sqrt(n); i += 2) {
            if (n % i == 0) return false;
        }
        return true;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter start number: ");
        int start = sc.nextInt();
        System.out.print("Enter end number: ");
        int end = sc.nextInt();

        System.out.println("Prime numbers between " + start + " and " + end + " are:");
        for (int i = start; i <= end; i++) {
            if (isPrime(i)) {
                System.out.print(i + " ");
            }
        }
        sc.close();
    }
}

Step 4: Build project
mvn clean package

Step 5: Run project
mvn exec:java -Dexec.mainClass=com.su2.App

------------------------------------------------------------
Example Outputs
------------------------------------------------------------

PrimeNumberProj:
Enter a number:
7
Num = 7 is prime

BtwPrimeNumber:
Enter start number: 10
Enter end number: 30
Prime numbers between 10 and 30 are:
11 13 17 19 23 29
