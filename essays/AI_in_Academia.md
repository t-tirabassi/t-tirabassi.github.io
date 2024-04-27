---
layout: essay
type: essay
title: "AI in Academia: A Personal Perspective"
date: 2024-04-24
published: true
labels:
  - AI
  - Higher Education
  - Software Engineering
  - Coding Ethics
  - Learning
---

<img width="375px" height="325px"
     class="rounded float-start pe-4" 
     src="../img/academia/ai-robot-coding.jpeg" >

## The Aid of AI

Artificial Intelligence or AI is not only becoming more advanced within the modern day, but also much more prevalent, particularly within academia. Within educational discussions, there is currently the debate of how AI is impacting the education system, and whether or not its use is seen as positive or negative. On one hand, AI can be seen as a tool that can be used as a type of easily accessible support tool for students, while on the other hand it can be argued that students may rely too heavily on the use of AI, passing AI generated work off as their own and not learning the subject properly. Both of these cases hold equal weight, with evidence to support the claims made from these two sides. Software engineering is a field that I personally feel has benefitted from the use of AI, supported by my personal use of ChatGPT as somewhat of a tool or assistant within my programming. The key part here is that while I have used ChatGPT as a tool, I have not completely depended on it, and use it purely as a supportive academic tool within my current software engineering course ICS 314: Software Engineering I. 

To gain a better understanding of the usage of AI within an academic setting, let’s take a look at how I have used it through different elements of the course:

### 1. Experience WODs

Within ICS 314, one of the ways we have learned and practiced new material is through Experience WODs, which act as at-home assignments meant for students to exercise and practice what is covered throughout each module. For these WODs, I did not use any AI assistance such as ChatGPT as the format of these WODs are very straightforward, and include a video of the professor walking you through each step. It would not make sense to use AI here given the resources available to me as well as the fact that there is no such way to necessarily use AI in this setting beneficially. 

### 2. In-class Practice WODs

The same can be said for the in-class Practice WODs that we did, as they are for practice, meaning you do not necessarily need to provide a result within the given class period. I would use these WODs to genuinely try to apply the knowledge I had gained and to see if I could do it without assistance.

### 3. In-class WODs

However, that being said, I did use ChatGPT for some of the in-class WODs which acted as assessments to test our knowledge and skill of each module. While I would initially try my best to complete the assessment within the given time frame, after having practiced for the WOD extensively the day prior, I would rely upon ChatGPT if I was running into issues that I could not fix within the time limit. I would also use ChatGPT if I was unsure of where to start. However, this reliance mainly occurred during the early WODs revolving around Javascript. For example, within the WOD: Javascript 2, I asked ChatGPT to assist me in computing some of the calculations that I was stuck on, as well as fixing the ES6 syntax for the printing statements within the code, which can be seen here:

```js
class Score {
    constructor(judge, line, angle, style, xfactor) {
  this.judge = judge;
  this.line = line;
  this.angle = angle;
  this.style = style;
  this.xfactor = xfactor;
  this.total = line + angle + style + xfactor;
  }
}

class Run {
    constructor(driver) {
  this.driver = driver;
  this.scores = [];
  
  }
  
  addScore(score) {
  this.scores.push(score);
  }
  
  printAllScores() {
    this.scores.forEach((score) => {
      console.log(
`${score.judge} gave a score of line: ${score.line}, angle: ${score.angle}, style: ${score.style}, and x-factor: ${score.xfactor}, total: ${score.total}`
      );
    });
  }
  
  printOverallScore() {
  const totalScore = this.calcTotalScore();
  console.log(totalScore.toFixed(2));
  }
  
  printXFactorAveragedScore() {
      const xFactorAv = this.calcXFactAv();
    console.log(xFactorAv.toFixed(2));
  }
  
  printNoXFact() {
      const noXFact = this.calcNoXFact();
    console.log(noXFact.toFixed(2));
  }
  
  calcTotalScore() {
      const total = this.scores.reduce((sum, score) =>sum + score.total, 0);
    return total/ this.scores.length;
  }
  
  calcXFactAv() {
      const xFact = this.scores.reduce((sum, score) =>sum + score.xfactor, 0);
    return xFact/ this.scores.length;
  }
  
  calcNoXFact() {
      const noX = this.scores.reduce((sum, score) => sum + score.total - score.xfactor, 0);
    return noX / this.scores.length;
  }
}

const run = new Run('Ken Gushi');
run.addScore(new Score('Ryan Lanteigne', 35, 28, 19, 8));
run.addScore(new Score('Chris Uhl', 38, 27, 20, 10));
run.addScore(new Score('Brian Eggert', 39, 28, 20, 9));
run.printAllScores();
// "Ryan Lanteigne gave a score of line: 35, angle: 28, style: 19, and x-factor: 8, total: 90"
// "Chris Uhl gave a score of line: 38, angle: 27, style: 20, and x-factor: 10, total: 95"
// "Brian Eggert gave a score of line: 39, angle: 28, style: 20, and x-factor: 9, total: 96"

run.printOverallScore();
// "93.67"

run.printXFactorAveragedScore();
// "9.00"

run.printNoXFact();
// "84.67"
```


### 4. Essays

As for the technical essays that we were required to write over the course of the semester, I did not use ChatGPT as I personally enjoy writing and also have my own unique style when it comes to writing essays. This style of writing that I have uses different sentence forms and grammar layouts, which is something that I have found that AI cannot replicate. The only thing I did use ChatGPT for in regards to the essays is to help me brainstorm a title and some headers for each essay, as I decided to have them all use alliteration and would sometimes struggle with finding good words to express the paper and each section within it. 

### 5. Final project

For the final project of the class, I have been working in a group to develop a web application called UH Companion, which works as a social media app that allows for UH students to connect with other students and find gym partners to plan workout events with. My team and I are currently still working on at the time of writing this, I have been incorporating the use of ChatGPT mainly when I am unsure of how to implement a feature I want into the web application we have been developing. 

When adding a weekly calendar to a user’s profile page, I had included an image of a clickable space that would display an image of a dumbbell under each day of the week, allowing for the user to keep track of their personal routine. I wanted to have it so that once the user had clicked and added the dumbbell for that day of the week, it would keep track of it and not be lost upon reloading the page. I then provided ChatGPT with the section of code for the images and asked, “Is there a way that I can have the visibility of these cells track across a user’s usage of the UH RepCompanion app?” To this question, it then provided me with the following code which would keep track of the image across one’s local browser usage, allowing for it to stick with the user’s profile without having to be added the to the Profiles collection:

```jsx
 // Initialize image visibility state from local storage or default to false
  const [imageVisibility, setImageVisibility] = useState(() => ({
    cell1: JSON.parse(localStorage.getItem('cell1Visible')) || false,
    cell2: JSON.parse(localStorage.getItem('cell2Visible')) || false,
    cell3: JSON.parse(localStorage.getItem('cell3Visible')) || false,
    cell4: JSON.parse(localStorage.getItem('cell4Visible')) || false,
    cell5: JSON.parse(localStorage.getItem('cell5Visible')) || false,
    cell6: JSON.parse(localStorage.getItem('cell6Visible')) || false,
    cell7: JSON.parse(localStorage.getItem('cell7Visible')) || false,
  }));

  // Update local storage whenever image visibility state changes
  useEffect(() => {
    localStorage.setItem('cell1Visible', JSON.stringify(imageVisibility.cell1));
    localStorage.setItem('cell2Visible', JSON.stringify(imageVisibility.cell2));
    localStorage.setItem('cell3Visible', JSON.stringify(imageVisibility.cell3));
    localStorage.setItem('cell4Visible', JSON.stringify(imageVisibility.cell4));
    localStorage.setItem('cell5Visible', JSON.stringify(imageVisibility.cell5));
    localStorage.setItem('cell6Visible', JSON.stringify(imageVisibility.cell6));
    localStorage.setItem('cell7Visible', JSON.stringify(imageVisibility.cell7));
  }, [imageVisibility]);

  // Function to toggle the visibility of the image for a specific cell
  const toggleImageVisibility = (cellName) => {
    setImageVisibility((prevState) => ({
      ...prevState,
      [cellName]: !prevState[cellName],
    }));
  };
```

### 6. Learning a concept / tutorial

I did not ever use ChatGPT when learning a new concept within the course as I felt the materials provided and the professors explanations were enough for me to understand and replicate what I had learnt. 

### 7. Answering a question in class or in Discord

I also never used any kind of AI when asking or answering a question within the class or on the ICS 314 Discord, as many of the questions asked could not be answered via AI, as many of them were practical issues that required human cognition and response. 

### 8. Asking or answering a smart-question

Similarly to any questions within class or on Discord, I did not feel it necessary to use AI for the smart-questions that we defined towards the middle of the semester. The purpose of many of these questions was not only to get assistance, but to also practice communicating effectively within a software environment.

### 9. Coding example

Occasionally, I would ask ChatGPT to provide a coding example to confirm that I understood something before I would implement it. For example, when we first began using Simple Schema, I wanted to better understand how the collections worked with the schema. I asked ChatGPT, “How do collections typically work using Simple Schema?” ChatGPT responded by providing me with the following code and explanation:

*SimpleSchema in Meteor.js helps define and validate MongoDB document schemas. Here's a concise example:*

```jsx
import SimpleSchema from 'simpl-schema';
import { Mongo } from 'meteor/mongo';

// Define a collection
export const Books = new Mongo.Collection('books');

// Define schema for 'books' collection
const BookSchema = new SimpleSchema({
  title: String,
  author: String,
  publishedAt: Date
});

Books.attachSchema(BookSchema);

// Insert document (data validated against schema)
Books.insert({
  title: 'The Great Gatsby',
  author: 'F. Scott Fitzgerald',
  publishedAt: new Date('1925-04-10')
});
```

### 10. Explaining code

I did not use any AI when I needed an explanation of code, as I felt that any reponse that ChatGPT could give me could be found through a simple search on Stack Exchange. therefore, I felt it was not necessary to inquire about a code's functionality.

### 11. Writing code

As for writing code, I have used ChatGPT which is present within the example I gave earlier, when I used it for the final project to track the appearance of the dumbbell images within the weekly calendar found on the profile page within the application. 

### 12. Documenting code

I do not believe that I ever used ChatGPT to document code, as I would tend to go through and manually document the code myself so that I could justify that I understood the code itself. 

### 13. Quality assurance

ChatGPT has been very useful at times when I am checking for quality assurance within any file project. Typically I would make use of the AI when I was encountering an error that I could not comprehend or merely find. A good example of this would be when I was working on recreating a site of our choice using Meteor. I had completed everything, but couldn't help notice that there was a border around the entire page that I wasn't able to get rid of no matter all the different CSS and component changes I made. Eventually, I decided to ask ChatGPT, "How can I get rid of the thin white border around my Meteor project?" and provided it with the CSS code, as I believed it to be the issue. ChatGPT then suggested that there could be an automatic padding being applied to the site, and that to change it I had to modify the css of the root of the page. Low and behold, this was found to be the case and the AI then gave me the following code to include within my CSS file in order to fix the issue:

```jsx
div#root {
  padding: 0;
}
```

### 14. Other uses in ICS 314 not listed

For other uses outside of just the course of ICS 314: Software Engineering I, I have found ChatGPT to be a helpful tool with other coding assignments and learning experiences. At the time of writing this, I am also currently taking EE 367: Computer Data Structures and Algorithms. Within the class, many assignments require the use of various algorithms in the programming language of C, with some of these assignments being quite difficult even after having the professor explain it. I find ChatGPT helpful when completing these, as it can guide me through each line of code and assist with any errors I encounter. Outside of academia altogether, I have found ChatGPT to be helpful when trying to generate new ideas for things, whether it be a name, a title, etc. I use it mainly due to the fact that when starting something new, I tend to get writer’s block when starting and find it hard to generate a starting point to then build off of. A similar example to this is the mention of how I used ChatGPT to help me generate alliterative titles and headers for my essays, in order to catch the reader’s eye and keep them interested. This usage of the AI is even present within this essay itself, apparent by the alliteration present within the title and headers.

## Lending to Learning

<img width="500px" height="300px"
     class="rounded float-start pe-4" 
     src="../img/academia/ai-robot-coding-4.jpeg" >

In regards to the use of AI, I do feel that it has significantly altered the learning experiences I have when approaching various concepts and topics. I believe that AI can assist individuals with the comprehension of different academic materials and experiences, as it can allow for those learning to gain a better understanding or grasp on a topic that they may be struggling with, and have it explained in a way that they can understand. I feel that many students struggle with academic materials not due to their personal fault or that of the one teaching, but the way in which the material is communicated and presented. This stems from the fact that everyone has their own way of learning and the way in which something is taught may be easier for one person to understand, but harder for another. The use of AI also allows an individual to ask more questions that once again, can be explained in a way that they understand and add to an overall better understanding of said topic.

In terms of skill development, this is where AI becomes a bit more debated within academic circles. From a personal standpoint, I try to develop my skills properly as I know that if we were to rely on AI now the lack of these skills would drastically hinder my abilities and career for the future. The way in which I use AI to develop my skills is if I am unsure of how to incorporate something within my code or something specific I wish to incorporate, I may provide ChatGPT with the code I currently have and then ask it a question while being specific. For example, say I have an idea for a feature that I would like to incorporate into my code, but am unsure of how to do so. I may provide the code and ask ChatGPT how I could do this with the given code, and then it may provide me with an answer, but more often than not this answer is incomplete or slightly incorrect. I will then use the base insight it has given me and use the skills I have to incorporate that feature not only properly, but in a way that makes sense to me. This process is present earlier where I mentioned I had used ChatGPT to help me incorporate a visibility feature and tracker within the final project for ICS 314: Software Engineering I.

I feel that in regards to problem-solving abilities, ChatGPT serves as a hindrance. The purpose of developing problem-solving abilities is to not only help you within your career, but also with all other aspects of life and the challenges you may encounter. By leaving the process that goes into solving a problem to an AI, you rob yourself of skills that not only apply to your career, but also to your life as a whole. By following this, one will eventually confront the consequences to this avoidance. Due to this, I personally have focused on developing these abilities personally through years of practice. However, as I mentioned earlier, I may occasionally ask ChatGPT a question if I am genuinely stuck and am unable to find online resources to assist me. For example, say I am running into an error where my code isn’t working properly. I then may provide the code to ChatGPT and ask what the cause of the issue may be, to which it will then provide me with a specific result or possible causes. By seeing how the AI dissects the code to find the problem. I can then use that method to influence how I go about problem solving moving forward, now having gained this new knowledge.

## Applying AI

Taking a step outside of an academic setting, AI has also been used in many practical ways in order to serve as a tool for software programmers. For example, Github Copilot is an AI model by Github, OpenAI, and Microsoft that serves as a programming assistant using publicly available sources and training data to provide suggested changes and automatically filled lines of code. Github Copilot has become a staple for many ambitious software engineering projects and collaborations, such as in the University of Hawai’i Game Dev Club’s yearly Game Jam, allowing for a more efficient usage of time and resources to be allocated towards development. In terms of taking on real-world software engineering challenges, I believe that Github Copilot proves to be effective given that its model acts as a secondary programmer and merely makes the suggestions, allowing for the individual programmer to decide whether or not they wish to incorporate the use of the AI. The use of Github Copilot can ease the workload of a programmer within a real-world setting, and while I have not personally used it, I believe that it holds its supportive value. Essentially, Github Copilot works as a personal assistant to optimize the time spent in coding, but does not outwardly remove the skill and knowledge required from the programmer, which I believe provide the perfect balance that AI should have when used in any software engineering setting.

## Characterizing Challenges

While AI has been useful to myself personally throughout ICS 314, I do believe that there are challenges that come with using AI as well as limitations that these simulations of human intelligence impose. For starters, AI uses information from testing and across the web to simulate human response and explanations, yet it is just that, a simulation. AI can not recreate the distinct difference between the assistance or teachings of another human being because it is unable to truly replicate that which makes us human. I think that AI itself is limited due to this, in that it can only spew out the information that has been fed or built upon pre-existing knowledge to attempt to create something new, even though it is essentially a recycled response. Due to this, it may not always prove helpful to use AI when confronting certain problems within software engineering, which is why one should not solely rely upon AI and again use it as a support tool. 

In order to even have the AI assist you, you not only have to understand the concepts you are learning about and working with, but also how the AI receives the information and how you have to interpret it with your own pre-existing knowledge. This presents the challenge of getting the AI to actually prove useful rather than hindering your own performance. Essentially, there are many things that AI can’t do, but you can, and if you are struggling with something, you must combine what you know with the database of knowledge the AI has to produce useful results. However, I believe that the education of software engineering can further integrate AI by educating people on the uses of AI as a tool, what it can and can’t be helpful with, and using it in a way that better educates people on software engineering through the accessibility of more knowledge outside of the classroom.

<img width="420px" height="300px"
     class="rounded float-start pe-4" 
     src="../img/academia/ai-robot-coding-3.jpeg" 
    align="right" >


## Tradition vs. Technology

Comparatively, traditional teaching methods drastically outweigh those of AI approaches within software engineering. I feel that with any type of programming especially, it is more often than not beneficial to work with others in-person within a collaborative setting, allowing for a flow of communication and assistance all around. Personally, I feel that I learn more when I am taught something verbally alongside a visual or physical demonstration, which then allows me to take that knowledge and replicate it. In contrast, AI simply presents you with a result and not the process behind getting to that result. The difference between these ways of learning is time, where traditional teaching methods allow for information to settle and be practiced, whereas with AI it is instantaneous, so the knowledge and skills do not produce as a result. Traditional teaching methods allow for engagement considering you are physically present, focused, and communicating with another person rather than a non-living artificial intelligence. This allows for a sense of common ground and understanding which is vital towards the process of learning.

In a traditional academic setting, students are also able to retain knowledge much more well, given that for many of us it is essentially all we can think about given the enforced repetitive practice we all tend to endure. While one may despise this overwhelming push for more and more practice constantly, it does end up paying off given the skills and knowledge you were able to acquire it. Due to this repetition, you are also more likely to remember it given the time you spent with it, and perhaps the memories of never-ending hours spent on that one homework assignment. However, an AI simply produces an instant result, which allows students for an easy way to opt out of learning that material. Therefore, the knowledge does not stick with the student not only due to the lack of time, repetition, and memory associated with said knowledge or skill, but also that this allows students to completely skip out on ever learning it in the first place. Hence, they move on and forget. 

Similarly, this can be applied to skill development, as the time spent physically on building a skill is vital to actually learning it. For example, say you wish to become better at shooting three-pointers in basketball. You decide that you’re going to watch a bunch of NBA three-pointer shot videos to develop this skill. After watching these videos for 20 minutes, you then believe you are now better at taking these shots. However, you’re going to find that you haven’t improved, and that you are at the same spot you began in. On the other side of things, say instead you dedicate an hour a day to practicing these shots. You manage to stay consistent for a month, and then decide to test your skills. By practicing and progressing exponentially over this time, you’ll find that you have improved, because you were physically and mentally there and applying yourself. No one was forcing you to practice and you could’ve stopped at any time, but you kept consistent and achieved the result you desired. Therefore, if you wish to become better at anything, whether it is software engineering or not, you must put in the time and effort in order to not only achieve what you want, but to also benefit yourself in the process.

<img width="350px" height="350px"
     class="rounded float-start pe-4" 
     src="../img/academia/ai-robot-coding-2.jpeg" >

## Focuses on the Future

While I believe that traditional teaching methods are much more effective in education than AI, I believe that AI will most likely play a bigger part in education as time goes on. Software engineering in education can benefit from the incorporation of AI in many ways. For one, AI could be used to allow for more focus on the vital part of the lesson or module and remove that which is deemed a waste of time. For example, say the professor is teaching students about React and the code they are working with includes repetitive classes or containers such as div. The AI can then be used to cut out unnecessary time put into manually typing out all of these lines that all are the same if not similar. While students can just copy and paste these lines of code, it would be a more effective use of time for the AI to handle this and allow for students to focus more on the parts of the code the professor wishes to emphasize. AI could also be used within classrooms as a part of the curriculum, allowing for professors to incorporate AI into their assignments and help students be able to implement AI within any software projects they may do for the course.

Some of the challenges with incorporating AI within software engineering education of course is the regulation of its usage. Tying back into the debates about AI within education, professors do not want their students to not be learning the material and relying upon AI to do it for them. This challenge will likely need to be addressed within the decade given the rapid evolution of AI and its advancements towards human creativity. Perhaps there may be AI models that can be programmed solely for the use of education, acting as a personal assistant to students while learning. These educational AI models can work alongside professors and teaching assistants to better balance out the help students are receiving within the classroom. This will also aid the issue in that while they will do what they can, those teaching cannot help everyone at once, which can often lead to some not getting the amount of help they need throughout their education.

As a whole, I believe that AI can be beneficial in educational settings if used properly. From a personal perspective, I believe that AI is a tool to be harnessed rather than abused, and that it can provide personal assistance with learning in a way that I understand. Within the Software Engineering I course here at the University of Hawai’i at Manoa, I have used AI as a crutch to fall back on when I am left stuck on an issue and am unable to find assistance via online resources or through the course material and assignments. In combination with pre-existing knowledge, AI can be used to further understanding in software engineering skills and practice. It can provide individual help in the comprehension of unfamiliar topics, but does not prove useful in the development of software engineering skills and problem-solving abilities. I feel that AI can be applied in many ways outside of the classroom, and that the better we understand AI, the better we will be able to incorporate it effectively into our approaches towards future challenges. Using AI comes with its own challenges and has its own limitations in capability, but can be overcome depending on the way in which you approach it given the skills and knowledge you currently possess. While AI will never likely replace traditional teaching methods, I believe it’s important to recognize the responsibility we have when using AI and what that means for our future, as you solely are responsible for the future you wish to have. Perhaps as AI continues to progress, we will not only see its further incorporation within the education of software engineering, but also the benefits that may come with doing so.
