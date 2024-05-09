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

### Simulating Self-Pay

  In this project, I was tasked with creating and simulation a self-pay kiosk program. This project was a part of a course I took, ICS 211. This course mainly focused on upper introductory practices within Java and gave us several projects to work on throughout the course, with this one being the final. I worked independently on this project and developed a better understanding of not only Java, but the process of being presented with an unfamiliar challenge and tackling it. While I had been pretty proficient in Java, I was having some minor syntax issues, which since then has caused my mind to adapt to a professional programming mindset, by making sure each line runs instead of fully typing out the program for it to simply not run properly.

<img width="210px" 
     class="rounded float-start pe-4" 
     src="../img/selfpay/selfpaykiosk1.jpeg" >

### Knowledge from the Kiosk

  Some of the skills I took away from this project, and honestly the class as a whole is time management, problem solving, resourcefulness, and rethinking. I feel that since then, I have become much beteer with time management with more complex programming challenges and projects. Upon initially being presented with the problem, I was hesitant upon starting, as I often found myself not knowing where to start until that initial spark hit. This initial implementation was assisted in part due to revieweing my past work to conjure up ideas on how to approach the problem at hand. It also taught me that if you are truly stuck on something, take a step back, let those thoughts sit in the back of your mind, and eventually you will have that "Eureka!" moment where everything become clear. I feel that as a whole, this project was the first instance where my mind began to adapt into the mindset of a programmer, and taught me how to face future endeavors in the field.

Here is the code for the LabProgram file used to test the operations of the system and simulate sales done as if done by a user:

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
(Note: The original files are privated through the course site, so I am unable to link the full program for public viewing.)
