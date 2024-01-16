---
layout: project
type: project
image: img/selfpay/selfpaykiosk2.jpeg
title: "Self-Pay Kiosk"
date: 2023-06-05
published: true
labels:
  - VS Code
  - Java
summary: "I was tasked with creating a program to replicate a self-pay kiosk using two different files in Java."
---


  *Description of project*

<img width="200px" 
     class="rounded float-start pe-4" 
     src="../img/selfpay/selfpaykiosk1.jpeg" >

  *What skills learned*

Here is the LabProgram file used to test the operations of the system and simulate sales done by a user:

```java

public class LabProgram {
   public static void main(String[] args) {
      SelfPayKiosk kiosk = new SelfPayKiosk();
      
      // Test basic operations
      kiosk.scanItem(20.49);
      kiosk.checkOut();
      kiosk.makePayment(25.20);
      System.out.println("Number of customers: " + kiosk.getNumCustomers());
      System.out.printf("Amount due: %.2f\n", kiosk.getAmountDue());
      System.out.printf("Total Sales: %.2f\n", kiosk.getTotalSales());
 
      // Add statements as methods are completed to support development mode testing
      
      
      // Test simulateSales()
      kiosk.resetKiosk();
      kiosk.simulateSales(100, 5, 2.5); 
      System.out.println("Number of customers: " + kiosk.getNumCustomers());
      System.out.printf("Amount due: %.2f\n", kiosk.getAmountDue());
      System.out.printf("Total Sales: %.2f\n", kiosk.getTotalSales());
   }
}
```
(The original files are privated through the course site, so I am unable to link the full program for public viewing)
