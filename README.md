# Method-Calling
This program illustrates writing and calling methods by estimating the price of a job with a painting company.


import java.util.Scanner;

public class CallingMethods {
    public static void main (String [] arg) {
        //Write a welcome message and read in the price per gallon and the wall space (in square feet) to be painted
        Scanner sc = new Scanner(System.in);
        System.out.println("Welcome to our Painting Company! We can assist you in getting a sense of how much a paint job" +
                " with us would cost.\n" + "Please enter the price per gallon of paint: ");
        double pricePerGallon = sc.nextDouble();
        System.out.println("Please enter the number, in square feet, of wall space to be painted: ");
        double wallSpace = sc.nextDouble();
        System.out.println("The wall space to be painted is " + wallSpace + " square feet, with a price of $" + pricePerGallon +
                " per gallon of paint.\n");
        //Call all the methods that will each do a single calculation and display them
        double numOfGallons=calculateGallons(wallSpace);
        System.out.println("The number of gallons used will be " + numOfGallons + " gallons.");
        double laborHours=calculateLaborHours(numOfGallons);
        System.out.println("The number of hours required to complete the job is "+ laborHours + " hours.");
        double paintCost=calculateCostOfPaint(numOfGallons, pricePerGallon);
        System.out.println("The cost of the paint will come out to $" + paintCost);
        double laborCharges=calculateLaborCharges(laborHours);
        System.out.println("The labor pay will be $" + laborCharges);
        double totalCost=calculateTotalCost(paintCost,laborCharges);
        System.out.println("The total cost of the paint job is $" + totalCost);

    }


    //Write a method for the number of gallons required and return the value
    public static double calculateGallons (double wallSpace) {
        double numOfGallons = wallSpace / 100.0;
        return numOfGallons;
    }

    //Write a method for the hours of labor required and return the value
    public static double calculateLaborHours (double numOfGallons) {
        double laborHours= numOfGallons * 6;
        return laborHours;
    }

    //Write a method for the cost of the paint and return the value
    public static double calculateCostOfPaint (double numOfGallons, double pricePerGallon) {
        double paintCost= numOfGallons * pricePerGallon;
        return paintCost;
    }

    //Write a method for the labor charges and return the value
    public static double calculateLaborCharges (double laborHours) {
        double laborCharges= laborHours * 32;
        return laborCharges;
    }

    //Write a method for the total cost of the paint job and return the value
    public static double calculateTotalCost (double paintCost, double laborCharges) {
        double totalCost= paintCost + laborCharges;
        return totalCost;
    }

    }

