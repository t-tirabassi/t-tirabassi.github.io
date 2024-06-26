---
layout: project
type: project
image: img/repcompanion/uh-repcompanion.png
title: "UH RepCompanion"
date: 2024-05-05
published: true
labels:
  - Meteor
  - React
  - Bootstrap
  - MongoDB
  - Software Engineering
  - Web Application Development
  - HTML
  - CSS
  - JSX
summary: "My team and I created UH Repcompanion, an application designed to connect University of Hawai'i students seeking gym partners."
---

&nbsp;

### What is UH RepCompanion?

<img width="220px" height="200px"
     class="float-start pe-4" 
     src="../img/repcompanion/uh-repcompanion.png" >

UH RepCompanion was the result of the final project for the course ICS 314: Software Engineering I, in which teams were tasked with developing a web application based on a set of given prompts. My group and I were tasked with developing a web application that would allow for University of Hawai'i students to connect with one another to find compatible gym companions who they could then workout with at the on campus gym, hence the name UH RepCompanion. This process of development followed Issue Drive Project Management (IDPM), more commonly referred to as Agile Project Management, which included a consistent group work schedule, prioritizing communication, dividing and assigning tasks to individual group member (with each task being separate within its own branch), documenting the development process, and three separate milestones to account for the different stages of development and progress we had made towards the final product. This approach allowed us to properly keep track of our advances towards the end goal for the application.

The application itself allows University of Hawai'i student to register using their UH email and create a profile for themselves consisting of their name, major, a short biography, a profile picture, workout interests, a tag to designate their level of experience, and optionally social media. Through the application, users can view upcoming workout events created by other users and then connect with that user for that event. Users can also search through other users profiles to connect with others who may share similar workout interests or share the same experience level. Essentially, UH RepCompanion works as a type of social media application for UH students interested in fitness, where they can connect with others and plan out workouts with a gym buddy.

### Milestone 1

<img width="300px" height="390px"
    class="float-end pe-4" 
     src="../img/repcompanion/UH-RepCompanion-17.png" >

For each milestone of the project, each member within my group was assigned a few tasks that would contribute to the end goal for that milestone. For the first milestone, designated as M1, my tasks included the creation of the Landing Page of the site and serve as the nexus for the application, as well as the creation of the Profile and Edit Profile Pages, where the logged in user would be able to view their profile and allow the user to edit the information associated with it. For the Landing Page, my focus was on not only creating a user friendly and aesthetic ui for the user to navigate, especially in terms first time users of the application, but also the functionality of this page. Given that it served as the foundation for the navigation and access for the rest of the site, it had to be easily discernable and portray professionalism. This page also provided a short description of what UH RepCompanion is and served as the access point for loggin in or registering an account. I mainly focused on the functionality and layout of the page, and later incorporated more unique stylization further into development. As for the Profile Page, I focused more on properly conveying a readble layout for the information that was being drawn from the Profiles collection database. The page itself consisted of a card displaying the information mentioned previously upon registration. Later on in a future milestone, I would incorporate more features and stylization to the page itself. The Edit Profile Page basically was a form that the user would fill out and then it would be saved into the MongoDB for the Profiles collection, so the creation of this page was not too difficult. This page would be later updated in accordance to changes within the Profile Page. I also took time within this milestone to create a recognizable logo for the application. Much of the work done for this milestone was very basic, as it served as a way for us to build up the foundations for the app to then later expand upon these ideas and incorporate new features for user functionality.

### Milestone 2

<img width="330px" height="390px"
    class="float-start pe-4" 
    src="../img/repcompanion/UH-RepCompanion-15.png" >

In the second milestone, designated as M2, I was tasked with revising the Landing Page not only in styliziation, but also in providing a more in depth introduction to the application and its functionalities. I took the time to create a unique style that could be used across the site, starting with the Landing Page as once again it would be the first thing users are introduced to. I also updated the layout of different access points to other pages, as the original layout was very bare-bones and not clear for users. As for the informational component found on the Landing Page, I provided photos to accompany the descriptions of the app to match the professionalism found with other gym sites, such as 24 Hour Fitness. This gives the user a visualization of what they can accomplish in using the application, as well as its purpose. Apart from those two tasks, I was also assigned to implement a calendar feature on the user's Profile Page, which had been one of the ideas my group and I had brainstormed during our initial planning process. To do this, I constructed a table that would display a weekly calendar, and then the user could then click on that day for a dumbell icon to appear, which would act as a way for the user to personally keep track of what days they planned on working out, allowing them to create a personal routine. This would coincide with user Events, in which a user would create a workout event on the Event Page detailing the day they plan to workout, a short description of their routine, what equipment they plan on using, who created it, and when it was created. This event would also appear on the user's Profile Page underneath their profile card. Other users could then view their profile, see which weekdays they will be working out, and then see what the workout entails. From here, that user can then connect with the creator of th workout if they wish to join them. This milestone was where the shape of the application really began to take place and where some of the more major features were incorporated.

### Milestone 3

For the third and final milestone, the tasks that I was assigned to complete was implementing a way for user's to include their social media links which would then appear on their profile, fixing the informational footer's format and style, incorporating dynamic image sizing into user profile pictures, linking the weekly calendar to the user's schedule, styling the event cards, and adding accessibility to the Events and Finder page upon login. To implement the social links, I first had to update the Profiles collection so that upon submitting the form whether it be through registration or editing their profile, a user's social media would be tied to their accounts within the database. After doing this, I then incorporated a url identification which would then check the links being input into the form to verify whether or not they were valid. The social links available to a user were limited to Instagram, Discord, LinkedIn, Snapchat Facebook, and Twitter. This identification process would check to see that these links matched the expression of these social media platforms, and would pass if validated. Within the Profile Page, I then implemented a function that used different cases to display only the social links that the user chose to add to their profile, represented by an icon for that social media platform, which also served as a link that other users could clik on to visit that users social media. For example, if a user were input a link to their Instagram account, it would then check and validate whether or not the link is a valid Instagram link, then display the Instagram icon on their profile, which when upon clicking said icon, would redirect them to that user's Instagram page. Here's how the incorporation of these social links works in the code:

```jsx
  const renderIconForSocialLink = (platform, link) => {
    if (link) {
      let IconComponent;
      let url;

      switch (platform) {
      case 'Instagram':
        IconComponent = Instagram;
        url = `https://instagram.com/${link}`;
        break;
      case 'Discord':
        IconComponent = Discord;
        url = `https://discord.com/${link}`;
        break;
      case 'LinkedIn':
        IconComponent = Linkedin;
        // eslint-disable-next-line no-unused-vars
        url = `https://linkedin.com/in/${link}`;
        break;
      case 'Snapchat':
        IconComponent = Snapchat;
        url = `https://www.snapchat.com/add/${link}`;
        break;
      case 'Facebook':
        IconComponent = Facebook;
        url = `https://www.facebook.com/${link}`;
        break;
      case 'Twitter':
        IconComponent = Twitter;
        // eslint-disable-next-line no-unused-vars
        url = `https://twitter.com/${link}`;
        break;
      default:
        // If the platform is not recognized, return null
        return null;
      }

      // Render the icon with the corresponding link
      return (
        <Col xs="auto" className="text-center" key={platform}>
          {/* eslint-disable-next-line jsx-a11y/control-has-associated-label */}
          <a href={link} target="_blank" rel="noopener noreferrer">
            <IconComponent className="mt-2 icon" />
          </a>
        </Col>
      );
    }
    return null; // Return null if the link is not present

  };

  // Function to render icon links based on social media platforms
  const renderSocialLinks = () => (
    <Row>
      {profile && (
        <>
          {renderIconForSocialLink('Instagram', profile.socialLink1)}
          {renderIconForSocialLink('Discord', profile.socialLink2)}
          {renderIconForSocialLink('LinkedIn', profile.socialLink3)}
          {renderIconForSocialLink('Snapchat', profile.socialLink4)}
          {renderIconForSocialLink('Facebook', profile.socialLink5)}
          {renderIconForSocialLink('Twitter', profile.socialLink6)}
          {/* Add more social links as needed */}
        </>
      )}
    </Row>
  );
```

<img width="370px" height="400px"
    class="float-end pe-4" 
    src="../img/repcompanion/UH-RepCompanion-21.png" >

On the Landing Page, I refined the layout of the informational section, as it was originally very bland and did not have texture nor proper formatting. I opted to lower the opacity percentage of the image as to not obscure the main background image, and also incorporated stylized Greek pillars as a symbol of strength to fit with the theme of the application. This incorporation was also an idea that was discussed during development. I also once again updated these sources of information to make clear what UH RepCompanion really is, and how it canhelp UH students connect with one anohter over similar fitness goals. Another task that I set out to accomplish was the dynamic sizing of user profile pictures. Originally, if you were to use a picture that had a large widht, it would stretch the image border to create an oval shape, yet we wanted the image to remain circular and within the border regardless of the original size. To do this, I updated the stylized elements of these images to ensure consistent sizing, and tested to this to ensure its effectiveness.

In regards to linking the calendar to the schedule, I changed its original usage so that if a user adds anything to their schedule page, it would reflect this within the small weekly calendar on the profile page, indicated by a dumbbell icon. Originally, this weekly calendar would just be controlled via the profile page, but this updated usage is much more proficient at tracking one's workout plans. I stylizied the event cards by adding icons and coloring to fill them out more, and finally added more accessible links upon login to visit the Events and Finder page on the landing page. Essentially, on the login page you would be presented with the Login and Register button, but after loggin in, these would be replaced with two icons for the Events and Finder page. This milestone was definitely the heaviest, as it required a lot of additions and revisions to be made to conclude the final stretch of the project.

### Closing Thoughts

This project managed to teach me a lot about collaborative projects especially within a software engineering setting. This experience gave me a sense of how software engineers operate within the workforce, along with the organization and efficient use of time that one must have. I feel that I was able to develop a stronger sense of communication while working within a group, and the importance of documentation throughout development. By following the style of Issue Driven Project Management (IDPM), I learned to slowly build upon a foundation by taking each addition step by step, which was important when attempting to decipher any issues that would arise especially upon merging. I also learned more technical skills such as the deployment aspect of a web application, as well as the means to acquiring custom domains. On top of that, I learned of a lot more functions and features that I can incorporate into my future projects, mainly driven by the research done when I was attempting to add a new feature such as the weekly calendar mentioned previously. Overall, this experience gave me insight into how these projects are carried out within real world settings, and has prepared me for my future endeavors and career within software engineering.

&nbsp;

If you would like to see the final results of this project, feel free to visit [https://uh-repcompanion.github.io/](https://uh-repcompanion.github.io/)

To better understand the inner workings of the application, please visit [https://github.com/UH-RepCompanion/RepCompanion-1](https://github.com/UH-RepCompanion/RepCompanion-1)

In order to access the deployed application, you can visit [https://uhrepcompanion.site/](https://uhrepcompanion.site/)

(Note: Based on the time period in which you are attempting to access the deployed application, it may no longer be accessible.)
