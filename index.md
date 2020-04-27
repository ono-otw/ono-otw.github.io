## Table of contents
* [Overview](#overview)
* [Goals](#goals)
* [User Guide](#user-guide)
* [Developer Guide](#developer-guide)
* [Development History](#project-development-history)
* [Developers](#developers)

## Overview

Ono On-The-Way is a web application that UH Manoa students can use when they do not want interrupt their work to go out for on-campus food. Students are able to register with the site as either a deliverer or a buyer. Buyers can request for food, and deliverers can fulfill the orders. The application is built using:
- [Meteor](https://www.meteor.com/) for Javascript-based implementation of client and server code.
- [React](https://reactjs.org/) for component-based UI implementation and routing.
- [Semantic UI React](https://react.semantic-ui.com/) CSS Framework for UI design.
- [Uniforms](https://uniforms.tools/) for React and Semantic UI-based form design and display.

## Goals 

Our goals for Ono On-The-Way is:
- To provide a directory of restaurants and vendors in or around the vicinity of the UH campus.
- Provide a facet for food to be delivered at a specific location on campus.
- Allows deliverers a list of orders to choose from, depending on location.

## User Guide
This section provides a walkthrough of our interface and its current capabilities. The screenshots show the current state of the project. Capabilities not yet implemented are either noted with the screenshot or denoted by the words "Mock Up" by the title. 

### Landing Page

This is the first page that students see upon visiting the site.

You can find our landing page [here](http://ono-otw.meteorapp.com/).
<img src="/Images/ono otw_landing.jpg">

### Sign up and sign in
This is where students can sign in or sign up.

<img src="/Images/Register-Mock%20Up.png">
<img src="/Images/Signin-Mock%20Up.png">

###  Profile Page
This where you can see the profile of the deliverer or customer. A functional rating system is yet to be implemented. 
<img src="/Images/Profile-Mockup.gif">

You can edit your profile below. Your venmo will only be shown upon delivery/ordering to the customer/deliver.
<img src="/Images/Edit-Profile.png">

###  Restaurants Page 
This where you can see the list of current restaurants to order from. A functional favorite system is yet to be implemented. 
<img src="/Images/Restaurants-Mockup.png">

###  Menu Page 
This is how the menu will look like. Starbucks was used as an example but all other restaurants will follow a similar layout.
<img src="/Images/Menu-Mockup.png">

Upon clicking the menu item, this box will pop up which allows you to customize your order. 
*Note: At the moment the ability to add to the cart and customize the order is yet to be implemented.*
<img src="/Images/Menu-Mockup-2.png">

###  Cart Page (Mock-Up)
This is how the cart page will look like upon checking out.
<img src="/Images/Cart-Mockup.png">

### Admin Page 
This is the admin page where admins and/or moderators can approve restaurants to be added to the list. 
<img src="/Images/ono otw_admin.png">

### Tracking (Mock-Up)
Allows you to track your order and communicate with the deliverer.
<img src="/Images/tracking.png">

## Project Development History
Running deployment on Galaxy: [OOTW](http://ono-otw.meteorapp.com/)

To track our progress via Milestones:
- [Milestone 1](https://github.com/ono-otw/ono-otw/projects/3)
- [Milestone 2](https://github.com/ono-otw/ono-otw/projects/2)
- [Milestone 3](https://github.com/ono-otw/ono-otw/projects/4)

### Developer Guide
1. Install meteor
2. Download a copy of ono-otw. You can download either using Github Desktop (recommended) or by extracting the .zip. 
3. cd into the /app directory and install the required libraries with:
 `meteor npm install `
4. Once the libraries are installed, the application can be ran by using: `meteor npm run start`
 
 Upon running the app the first time, it will create some default users and data. Here is the output. 
   ````
    W20200406-18:15:16.881(-10)? (STDERR) Note: you are using a pure-JavaScript implementation of
 bcrypt.
    W20200406-18:15:16.954(-10)? (STDERR) While this implementation will work correctly, it is known to be
    W20200406-18:15:16.955(-10)? (STDERR) approximately three times slower than the native implementation.
    W20200406-18:15:16.956(-10)? (STDERR) In order to use the native implementation instead, run
    W20200406-18:15:16.958(-10)? (STDERR)
    W20200406-18:15:16.958(-10)? (STDERR)   meteor npm install --save bcrypt
    W20200406-18:15:16.959(-10)? (STDERR)
    W20200406-18:15:16.961(-10)? (STDERR) in the root directory of your application.
    I20200406-18:15:17.241(-10)? Creating the default user(s)
    I20200406-18:15:17.243(-10)?   Creating user admin@foo.com.
    I20200406-18:15:17.559(-10)?   Creating user john@foo.com.
    I20200406-18:15:17.840(-10)? Creating default contacts.
    I20200406-18:15:17.842(-10)?   Adding: Johnson (admin@foo.com)
    I20200406-18:15:17.860(-10)?   Adding: Casanova (john@foo.com) 
    I20200406-18:15:17.864(-10)?   Adding: Binsted (john@foo.com)
  ````
_Note:_ You can modify the default users in `/config/settings.development.json`. To modify default restaurants and menu items, you can go to `app/private` directory and select the edit the respective .json files (eg. defaultRestaruants, defaultMenu, etc...)

**Note regarding bycript warning.** Upon running the application, you may stumble across this error:
````
Note: you are using a pure-JavaScript implementation of bcrypt.
While this implementation will work correctly, it is known to be
approximately three times slower than the native implementation.
In order to use the native implementation instead, run

  meteor npm install --save bcrypt

in the root directory of your application.
````

Some operating systems, especially Windows has trouble installing bcrypt. It is only used in Meteor for password checking. During initial stages of development and mock-up, you can safely ignore this message.
  
Head on over to `http://localhost:3000` to see the application. 
 
To adhere to common coding standards, you an evoke the command `meteor npm run lint` to run ESLint.


### Milestone 1: Mockup and Deployment
- Implemented landing page
- Created Ono-on the way logo
- Created various mock ups 
- Deployed to Galaxy

<img src="/Images/M1_Done.png">

**To see which issues have been finished during M1, please click: [Milestone 1](https://github.com/ono-otw/ono-otw/projects/3)**

### Milestone 2: Data model development
The goal of Milestone 2 is to integrate other pages of the application such as ability for the customer to order and a deliver to accept the order. This involves the implemetation of our data model, which will include multiple schemas to ensure the data entered is is valid. 

The progress on these tasks can be seen [here](https://github.com/ono-otw/ono-otw/projects/2).


### Milestone 3: Final touches



## Extra enhancements
After implementing the basic functionality, some additional features may include:
- Expanding to not just food (eg. Art supplies from UH Manoa Bookstore)
- Expansion to mobile application 
- Login using UH Central Authentication Service to ensure that all users who sign in are UH Students

## Developers
Here are the people who worked on this project:

Andre Ruiz: Find his Github <a href = "https://ruizaj.github.io/">here.</a> 

Jennifer Hsu: Find her Github <a href = "http://jhsup.github.io/">here.</a> 

Jin Yan Wu: Find her Github <a href = "https://wjinyan.github.io/">here.</a> 

Timoteo Sumalinog: Find his Github <a href = "https://timoteosumalinogiii.github.io/">here.</a> 







