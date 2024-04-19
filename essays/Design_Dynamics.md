---
layout: essay
type: essay
title: "Design Dynamics: Patterns in Practice"
date: 2024-04-17
published: true
labels:
  - Design Patterns
  - Coding Practices
  - Software Engineering
  - Coding Standards
---

<img width="500px" height="275px"
     class="rounded float-start pe-4" 
     src="../img/dynamics/chill-diving-suit.jpeg" >

## Navigating the Depths of Design

Within the sea of software development and engineering, design patterns serve as a path to maintaining the efficient functionality and navigation of one's code. Similarly to the way sailors use stars and different constellations to navigate the open sea, software developers and engineers use design patterns within their projects or work to accomplish their goals and succeed. Design patterns are repeatable solutions to common problems that arise when working with software. These patterns are used to avoid unnecessary efforts and time on otherwise insignificant problems in regards to the project. They work to speed up the development process and encompass formats that do not tie to specific problems. These patterns also improve communication amongst software engineers and developers where they become widely known and used, allowing for an easier understanding of the project. The benefits of using design patterns are relatively clear, but this begs the question: What types of design patterns are present within the industry?

## Patterns of Proficiency

As mentioned previously, design patterns are typically made so that they may be applied as a general solution that does not need to adhere to the specifics of the project or task at hand. In the 1994 book on software engineering title “Design Patterns: Elements of Reusable Object-Oriented Software”, one quote that portrays this sentiment is “Program to the abstraction, not to the implementation” (Gamma et al.). In other words, design patterns should be fluid so that they may be used in any setting, and the consideration of the implementation should not present itself when creating or using a design pattern. 

Design patterns usually fall under three categories: creational, structural, and behavioral. Creational design patterns revolve around class instantiation, separated by those that use inheritance for instantiation and those that use delegation. Some examples of these patterns include builder, abstract factory, prototype, and singleton design patterns. Structural design patterns focus on class and object composition, where class creation patterns use inheritance to compose interfaces and object patterns compose objects in terms of functionality. Examples of structural design patterns include adapters, decorators, facades, and proxies. Behavioral design patterns are used for the interactions between classes and objects, specifically with the communications between the two. These patterns may be a command, iterator, observer, state, or strategy design pattern. In short, the different types of design patterns and what they do encapsulate a lot of common issues that you may encounter. However, these are just a bunch of descriptions that don’t necessarily tell us how to use them or what they do, so let’s take a look at an example.


## Canvases of Code

In order to gain a better understanding of how to use these design patterns and what they typically look like, let’s examine a piece of code from an application that my team and I have been developing. More specifically, let’s take a look at the one of the constants found within the code for the user profile page:

```jsx
const { ready, profile, interests, tags } = useTracker(() => {
    const sub1 = Meteor.subscribe(Interests.userPublicationName);
    const sub2 = Meteor.subscribe(Profiles.userPublicationName);
    const sub3 = Meteor.subscribe(ProfilesInterests.userPublicationName);
    const sub4 = Meteor.subscribe(Tags.userPublicationName);
    const sub5 = Meteor.subscribe(ProfilesTags.userPublicationName);
    const userProfile = Profiles.collection.findOne({ email: Meteor.user()?.username });
    const userInterests = ProfilesInterests.collection.find({ profile: userProfile?.email }).fetch();
    const userTags = ProfilesTags.collection.find({ profile: userProfile?.email }).fetch();
    const userInterestsNames = userInterests.map(({ interest }) => {
      const interestDoc = Interests.collection.findOne({ name: interest });
      return interestDoc?.name;
    });
```

The code above works to display the different data values tied to a user's profile within the application. This behavioral design pattern uses the useTracker function hook to track changes in the data and data sources. The data it fetches is the user’s profile, interests and tags stored within the MongoDB collections. This useTracker function is linked to these collections using Meteor.subscribe within the application and fetches the data using the find and findOne methods. If the data changes, useTracker will re-execute and re-render the updated data to reflect that. As an observer design pattern, this then notifies these changes to other classes linked to this data. To put things simply, the useTracker tracks the data within the collections and if it observes a difference between the original data and the new data, it will update and notify other classes to update the user’s profile with these new changes.

## Smooth Sailing through Software 

Throughout my experiences with software engineering, there have been a few design patterns that I typically rely upon, especially when working in Javascript XML (JSX). The design patterns that I use when relaying and working with data is the behavioral observer design pattern, such as the previously presented example. For structural constructs, I tend to use composite design patterns for site and app creation, as it nests each component which then allows you to easily construct the layout of the app itself. As for a creational design pattern, I like to use singleton design patterns for application components, as it allows me to set specific attributes and then apply them to other parts of the application where I see fit. 

<img width="375px" 
     class="rounded float-start pe-4" 
     src="../img/dynamics/sailboat.jpg" >

When working on a project, I often combine many of these design patterns together so that the code itself not only runs more efficiently compared to a large page of code, but also is a lot more navigable for others. Using design patterns makes the work of a project much more manageable both in personal interest as well as in a team setting. These patterns also allow for other people to easily understand your code, which I believe is especially important when meeting the standards set within a highly competitive industry such as software engineering. As a whole, design patterns can serve as essential navigational tools that can allow software engineers to sail through the sea of challenges that await them when tackling a new software project.


### __References:__ 

[_Design Patterns_. SourceMaking. (n.d.).](https://sourcemaking.com/design_patterns)

[_Design patterns: Elements of Reusable Object-Oriented Software_. Gamma, E., Helm, R., Johnson, R., & Vlissides, J. (1994).](https://en.wikipedia.org/wiki/Design_Patterns)
