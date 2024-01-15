---
layout: project
type: project
image: img/hotel-management-system.webp
title: "Hotel Management System"
date: 2023-12-10
published: true
labels:
  - VS Code
  - Replit
  - C++
summary: "My team and I created a basic hotel management system in the language of C++ for a final project, displaying our capabilities and skills from the course."
---


The Hotel Management System Project was a final project for the course ICS 212 in which we had to construct a basic hotel management syetm in C++. The class was divided into teams of 5 or 6 and we were all responsible for programming different sections of the code and then putting the program together. I took the lead in this project, by guiding my team and fine-tuning the program. My team and I used cstring arrays, structures, andf class derivation to achieve this goal. We went through several different versions of the program, in which we were encountering bugs in our original implementation of a vector aproach. I took on the role of debugging the majority of the program, and realized that a cstring approach would be much more manageable for the build. Using the framework of the original code, we developed a fully functioning hotel management system that would store user input, rely on a main menu with sub-menus present based on the user's input, and the ability to combine multiple system options into one diaplayable output.

For this project, I was the lead programmer who was responsible for programming the various capabilities of the mouse.  I started by programming the basics, such as sensor polling and motor actuation using interrupts.  From there, I then programmed the basic PD controls for the motors of the mouse.  The PD control the drive so that the mouse would stay centered while traversing the maze and keep the mouse driving straight.  I also programmed basic algorithms used to solve the maze such as a right wall hugger and a left wall hugger algorithm.  From there I worked on a flood-fill algorithm to help the mouse track where it is in the maze, and to map the route it takes.  We finished with the fastest mouse who finished the maze within our college.

Here is the main menu that users would be presented with upon running the program:

```cpp
int main() {
    int opt, rno;
    char pname[100]; //char name array
    HotelMgnt hm; //used to call in hm class functions

    do { //do while statement for main menu
        std::cout << "######## Hotel Management #########\n";
        std::cout << "\n1. Manage Rooms";
        std::cout << "\n2. Check-In Room";
        std::cout << "\n3. Available Rooms";
        std::cout << "\n4. Search Customer";
        std::cout << "\n5. Check-Out Room";
        std::cout << "\n6. Guest Summary Report";
        std::cout << "\n7. Exit";
        std::cout << "\n\nEnter Option: ";
        std::cin >> opt;
...}
```
