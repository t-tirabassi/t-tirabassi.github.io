---
layout: essay
type: essay
title: "UI Frameworks Unveiled: Enhancing Experiences"
date: 2024-02-16
published: false
labels:
  - UI Frameworks
  - Web Design
  - HTML
  - CSS
  - Bootstrap 5
  - Software Engineering
---

<img width="300px" 
     class="rounded float-start pe-4" 
     src="../img/consistency/sitcode.jpeg" >

## Etiquette in Education

Upon being requested or prompted to write a paper, essay, or even an email, many of us are familiar with a certain style or format that we have learned and conform to in an academic and professional setting. We are taught these standards to conform to these styles so that they can be easily recognized and interpreted amongst the general public. Similarly, different coding languages offer their own etiquette of sorts, that being coding standards. Coding standards are essentially a collection of rules, guidelines, and practices that are generally considered the best ways to code, especially within a collaborative setting. These standards are set to not only produce neat and formatted code, but to make it easily readable for anyone who views, interacts with, or even builds upon said code. Coding standards are sometimes seen as beneficial for any individual learning a programming language, and I believe that there is some credence to this. I also believe that these coding standards should be put into more practice within beginner level coding exercises and teachings. Allow me to entreat you with my personal experience in learning coding standards, some insight upon its usefulness, some of its challenges, and how it can ultimately benefit you within your career.

## IntelliJ Impressions

As of now, my experience with coding standards revolves around the integrated development environment (IDE) IntelliJ IDEA and ESLint, which essentially works to help you practice and learn proper coding format within the programming language of Javascript. These fixes and recommendations can range from proper indentation or spacing, to using proper methods and variable assignments. In order to provide a more visual representation of how ESLint works, allow me to present an example. Here we have a javascript file containing numerous errors found by ESLint:
```j
var foo = 3;
const car = "Toyota";
const obj = {
  car: car,
  'foo': 3,
  bar: 'this' + 'is' + this.car,
  baz: 'b\az'
};
const zumba = obj['car'];
const stuff = new Array();

function f(){};
function zob(param) {
  param = 2;
  let foob=4+param;
  if (param == 4) {
    return foob;
  }
}
[1, 2, 3].map(function (x) {
  const y = x + 1;
  return x * y;
});
class MyClass {
  constructor() {}
  getName() {
    return this.name;
  }
  getName() {
    return this.name;
  }
}
const TheTitle = 'The Title';

export default {  obj, stuff, zumba, f, zob, MyClass, TheTitle };
```

When presented with these errors, ESLint prompts the user to either manually retype the found errors, or provides options for ESLint to explain the error and fix it for you upon request. Now, upon fixing the errors found by ESLint in the above javascript code, we now have a javascript file that follows proper coding standards set by ESLint:

```j
const car = 'Toyota';
const obj = {
  car,
  foo: 3,
  // eslint-disable-next-line no-template-curly-in-string
  bar: 'this is ${this.car}',
  baz: 'baz',
};
const zumba = obj.car;
const stuff = [];

function f() {}
// eslint-disable-next-line consistent-return
function zob(param) {
  const foob = 4 + param;
  if (param === 4) {
    return foob;
  }
}
[1, 2, 3].map(function (x) {
  const y = x + 1;
  return x * y;
});
class MyClass {
  getName() {
    return this.name;
  }
}
const TheTitle = 'The Title';

export default {
  obj, stuff, zumba, f, zob, MyClass, TheTitle,
};
```
As you can see, there is a clear difference between the formatting, spacing, and neatness found within both instances of the code. You can also see that ESLint presents you with parts of your code that go unused, allowing one to cut out any excess code that may be lingering within their program. ESLint is good at catching these types of things that would otherwise go unnoticed by a programmer.  However, there is also something that ESLint provides that has both its pros and its cons, depending on the individual.


## Proper Perfection

One thing that differs between writing code and writing a paper is that when writing a paper, you can write it using numerous different approaches, all providing their own uniqueness. When it comes to writing code, while there may be numerous approaches, there is ultimately the deciding factor of whether it works or not. In other words, when coding you are either wrong or you are right, with no in between. ESLint reinforces this by providing a green checkmark for correctness, yellow signs for warnings, and red bubbles for errors. I believe that this green checkmark is both useful and painful at given times. On one hand, the green checkmark can certify that you are following the proper coding standards and are correct. However, on the other hand, this checkmark can prove to be frustrating if the error is not explicitly presented to you or if fixing on error creates more. One personal experience I have had is that upon including a source script into an html file, I am presented with a constant warning from ESLint, despite the fact that its formatting is correct according to the ESLint standards provided by the analysis tool. Once again, this is a case to case basis, of which both sides can make arguments for why or why not this aspect is beneficial.

<img width="350px" 
     class="rounded float-start pe-4" 
     src="../img/consistency/codeworkplace.jpeg" >

## Workplace Wisdom 

Perhaps the most beneficial aspect of learning programming while following coding standards is its uses that can be found within the workplace, especially within the field of higher technology. For those pursuing careers in any field, whether tech related or not, knowing how to demonstrate professionalism is key to excelling within a career. Within the tech and programming industry, this demonstration of professionalism can be seen as crucial, as the ability to conform to these practices can allow for productive and efficient collaboration and time use. As mentioned earlier, the purpose of coding standards is to allow outsiders or other people to be able to look at your code, understand it, and know how it works. Neatness in presentation and stylized professionalism allows this process to go over smoothly. If you were to present a program to someone without this proper presentation, they may be struggling to follow or understand it. It may even be hard to read if it's just a giant lump of code with no proper segmentation or navigation to follow. This will ultimately make getting work done and collaboration within the workplace much harder than it needs to be. Therefore, I recommend that anyone who programs, whether you’re just learning or advanced, should follow good coding standards in order to not only become proficient in a professional setting, but to also make your own coding experiences more beneficial for yourself. Overall, coding standards are a thing that aren’t discussed as much as they should be, especially within an educational setting, and should be taught to aspiring programmers so that these future programmers can develop professional skills early and work towards more ambitious goals, whether career based or personal.
