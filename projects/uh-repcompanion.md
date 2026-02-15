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
summary: "UH Repcompanion, an web application designed to connect University of Hawai'i students seeking gym partners and track workout progress."
---

&nbsp;

### What is UH RepCompanion?

&nbsp;

<img width="220px" height="200px"
     class="float-start pe-4" 
     src="../img/repcompanion/uh-repcompanion.png" >

**UH RepCompanion** was developed as the final project for the course **ICS 314: Software Engineering I**, where our team created a web application enabling University of Hawai'i students to find compatible gym partners for on-campus workouts. Following **Issue Driven Project Management (IDPM)**, a form of **Agile Project Management (APM)**, we distributed task assignments, held regular team meetings, upheld thorough documentation, and worked via milestone-based progress tracking. The application itself allowed students to register with their UH email and create profiles including name, major, bio, profile picture, workout interests, experience level, and optional social media links. Users were able to track their workouts, browse upcoming workout events, connect with other participants, and search profiles to find partners with similar interests or experience levels. Essentially, UH RepCompanion acted as a fitness-focused social platform, helping students to plan workouts and build connections with gym partners.

&nbsp;

### Milestone 1

&nbsp;

<img width="300px" height="390px"
    class="float-end ps-4" 
     src="../img/repcompanion/UH-RepCompanion-17.png" >

For the first milestone (**M1**), each team member was assigned tasks that contributed to the foundational development of the application. My responsibilities as the **lead Front-end Developer** included designing the **Landing Page**, **Profile Page**, and **Edit Profile Page**.

The **Landing Page** served as the central hub of the application, providing first-time users with a clear and welcoming introduction to UH RepCompanion, as well as access to login and registration. I focused on creating an intuitive layout and functional navigation to ensure a seamless user experience while laying the groundwork for future stylistic enhancements.

The **Profile Page** displayed user information from the database in a clean, readable card format, while the **Edit Profile Page** allowed users to update their information, with changes saved directly to **MongoDB**. Additionally, I designed a recognizable logo to establish a visual identity for the application. This milestone established the core structure of UH RepCompanion, providing a solid foundation for subsequent features and design improvements.

**View Milestone 1 Project Board:** [https://github.com/orgs/UH-RepCompanion/projects/1](https://github.com/orgs/UH-RepCompanion/projects/1)

&nbsp;

&nbsp;

### Milestone 2

&nbsp;

<img width="330px" height="390px"
    class="float-start pe-4" 
    src="../img/repcompanion/UH-RepCompanion-15.png" >

In the second milestone (**M2**), I focused on enhancing the **Landing Page** and implementing key features to improve user engagement and functionality. I revised the layout and styling of the **Landing Page** to provide a clearer, more intuitive introduction to UH RepCompanion, including updating navbar access to other pages. I also incorporated visual elements through **UI/UX design**, such as personally created images and graphics, to give users a professional, gym-inspired aesthetic and a clear understanding of the app’s purpose.

In addition to the **Landing Page** improvements, I implemented a **weekly calendar** feature on the **Profile Page**. This feature allowed users to track their planned workouts by clicking a day to display a dumbbell icon, creating a personal routine. The calendar integrated with user-created **Events** on the **Events Page**, which included workout details such as date, description, equipment, and creator. These events appeared on the user’s profile, enabling other users to view schedules and connect with workout partners with similar schedules.

This milestone was a significant step in shaping the application’s structure and introducing major interactive **UI/UX features**, setting the foundation for the more advanced functionality and design enhancements implemented in the third and final milestone (**M3**).

<div style="margin-left: 330px;">
  <strong>View Milestone 2 Project Board:</strong> <a href="https://github.com/orgs/UH-RepCompanion/projects/9">https://github.com/orgs/UH-RepCompanion/projects/9</a>
</div>

&nbsp;

&nbsp;

### Milestone 3

&nbsp;

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
```
<details><summary><strong>Show full code </strong></summary>

```jsx
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
</details>

<img width="370px" height="400px"
    class="float-end ps-4" 
    src="../img/repcompanion/UH-RepCompanion-21.png" >

On the Landing Page, I refined the layout of the informational section, as it was originally very bland and did not have texture nor proper formatting. I opted to lower the opacity percentage of the image as to not obscure the main background image, and also incorporated stylized Greek pillars as a symbol of strength to fit with the theme of the application. This incorporation was also an idea that was discussed during development. I also once again updated these sources of information to make clear what UH RepCompanion really is, and how it canhelp UH students connect with one anohter over similar fitness goals. Another task that I set out to accomplish was the dynamic sizing of user profile pictures. Originally, if you were to use a picture that had a large widht, it would stretch the image border to create an oval shape, yet we wanted the image to remain circular and within the border regardless of the original size. To do this, I updated the stylized elements of these images to ensure consistent sizing, and tested to this to ensure its effectiveness.

In regards to linking the calendar to the schedule, I changed its original usage so that if a user adds anything to their schedule page, it would reflect this within the small weekly calendar on the profile page, indicated by a dumbbell icon. Originally, this weekly calendar would just be controlled via the profile page, but this updated usage is much more proficient at tracking one's workout plans. I stylizied the event cards by adding icons and coloring to fill them out more, and finally added more accessible links upon login to visit the Events and Finder page on the landing page. Essentially, on the login page you would be presented with the Login and Register button, but after loggin in, these would be replaced with two icons for the Events and Finder page. This milestone was definitely the heaviest, as it required a lot of additions and revisions to be made to conclude the final stretch of the project.

**View Milestone 3 Project Board:** [https://github.com/orgs/UH-RepCompanion/projects/17](https://github.com/orgs/UH-RepCompanion/projects/17)

&nbsp;

### Closing Thoughts

&nbsp;

This project managed to teach me a lot about collaborative projects especially within a software engineering setting. This experience gave me a sense of how software engineers operate within the workforce, along with the organization and efficient use of time that one must have. I feel that I was able to develop a stronger sense of communication while working within a group, and the importance of documentation throughout development. By following the style of Issue Driven Project Management (IDPM), I learned to slowly build upon a foundation by taking each addition step by step, which was important when attempting to decipher any issues that would arise especially upon merging. I also learned more technical skills such as the deployment aspect of a web application, as well as the means to acquiring custom domains. On top of that, I learned of a lot more functions and features that I can incorporate into my future projects, mainly driven by the research done when I was attempting to add a new feature such as the weekly calendar mentioned previously. Overall, this experience gave me insight into how these projects are carried out within real world settings, and has prepared me for my future endeavors and career within software engineering.

&nbsp;

You can explore the final deployed application here:  
**[https://uhrepcompanion.site/](https://uhrepcompanion.site/)**

To view the project overview and documentation, visit:  
**[https://uh-repcompanion.github.io/](https://uh-repcompanion.github.io/)**

For the full source code and technical details, see the GitHub repository:  
**[https://github.com/UH-RepCompanion/RepCompanion-1](https://github.com/UH-RepCompanion/RepCompanion-1)**

&nbsp;

(**Note:** Based on the time period in which you are attempting to access the deployed application, it may no longer be accessible.)
