## Table of contents
* [Overview](#overview)
* [Goals](#goals)
* [User Guide](#user-guide)
* [Developer Guide](#developer-guide)
* [Development History](#project-development-history)
* [Community Feedback](#community-feedback)
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
<img src="/Images/Landing-gif.gif">

### Nav Bar
Users are able to toggle between "Consumer" and "Deliverer". It changes the associated options for each.
<img src="/Images/NavBar-gif.gif">

### Sign up and sign in
This is where students can sign in or sign up.

<img src="/Images/Register-Mock%20Up.png">
<img src="/Images/Signin-Mock%20Up.png">

###  Profile Page
This where you can see the profile of the deliverer or customer. It shows the user's favorites, and past orders/delivery.
<img src="/Images/Profile-Mockup.gif">

You can edit your profile below. Your venmo will only be shown upon delivery/ordering to the customer/deliver.
<img src="/Images/Edit-Profile.png">

###  Restaurants Page 
This where you can see the list of current restaurants to order from. As shown below, you can favorite a restaurant and search for it by name. Upon clicking the result, it redirects you to its respective menu items.
<img src="/Images/RestaurantsGif.gif">

###  Menu Page 
This is how the menu will look like. Panda Express was used as an example but all other restaurants will follow a similar layout. You can filter through the food categories by clicking its respective tabs.
<img src="/Images/Menu-Mockup.png">

Upon clicking the menu item, this box will pop up which allows you to customize your order. 
<img src="/Images/Menu-Mockup-2.png">

If you are not logged in, this error shows up:
<img src="/Images/Menu-Mockup-4.png">

The "Cart" button at the bottom brings up your current cart. 
<img src="/Images/Menu-Mockup-3.png">

Below is a gif that shows the capabilites listed above:
<img src="/Images/Menu-Mockup-gif.gif">

###  Cart Page 
This is how the cart page will look like upon checking out. If users allow us to use their location, it will autofill it. 
<img src="/Images/Cart.png">

However, if they chose not to turn on location, they are able to edit the field themselves.
<img src="/Images/Cart-2.png">

Trying to order without inputting their location results in an error.
<img src="/Images/Cart-3.png">

If your cart is empty, this shows:
<img src="/Images/Cart-empty.png">

###  Accept Order 
Students who are looking for orders to accept can accept them here.
<img src="/Images/Accept-Order.png">

If there are no pending orders, this displays:
<img src="/Images/Accept-Order-2.png">

### Deliver Order
Upon accepting the order, students are provided with more information about it such the total cost and the customer's venmo:
<img src="/Images/Deliver-Order.png">

If they haven't accepted any orders yet, this shows:
<img src="/Images/Deliver-Order-2.png">

### Tracking
For deliverers, they are able to check the location they need to head to. 
<img src="/Images/tracking.png">

### Rating
After your order is delivered, you are prompted to rate the service:
<img src="/Images/Rating.png">


### Admin Page 
This is the admin page where admins and/or moderators can approve restaurants to be added to the list. Restaurants can also be deleted if necessary. 
<img src="/Images/ono otw_admin.png">

Clicking the "view" button brings up a preview of the restaurant:
<img src="/Images/ono otw_admin-1.png">

Admins and/or moderators are also allowed to edit restaurant fields:
<img src="/Images/ono otw_admin-2.png">

Admins are also able to add a restaurant:
<img src="/Images/Add-Restaurant.png">


### Developer Guide
1. Install meteor
2. Download a copy of ono-otw. You can download either using Github Desktop (recommended) or by extracting the .zip. 
3. cd into the /app directory and install the required libraries with:
 `meteor npm install `
4. Once the libraries are installed, the application can be ran by using: `meteor npm run start`
 
 Upon running the app the first time, it will create some default users and data. Here is the output. 
   ````
W20200513-23:20:54.963(-10)? (STDERR) Note: you are using a pure-JavaScript implementation of bcrypt.
W20200513-23:20:55.117(-10)? (STDERR) While this implementation will work correctly, it is known to be
W20200513-23:20:55.118(-10)? (STDERR) approximately three times slower than the native implementation.
W20200513-23:20:55.118(-10)? (STDERR) In order to use the native implementation instead, run
W20200513-23:20:55.119(-10)? (STDERR)
W20200513-23:20:55.119(-10)? (STDERR)   meteor npm install --save bcrypt
W20200513-23:20:55.120(-10)? (STDERR)
W20200513-23:20:55.122(-10)? (STDERR) in the root directory of your application.
I20200513-23:20:55.786(-10)? Creating the default user(s)
I20200513-23:20:55.790(-10)?   Creating user admin@foo.com.
I20200513-23:20:56.187(-10)?   Creating user john@foo.com.
I20200513-23:20:56.539(-10)? Creating testing cart data.
I20200513-23:20:56.543(-10)?   Adding: Milk Tea (john@foo.com)
I20200513-23:20:56.570(-10)?   Adding: Mocha Frappe (john@foo.com)
I20200513-23:20:56.576(-10)?   Adding: Mocha Frappe (admin@foo.com)
I20200513-23:20:56.581(-10)?   Adding: Earl Grey Tea (admin@foo.com)
I20200513-23:20:56.586(-10)?   Adding: Milk Tea (test@foo.com)
I20200513-23:20:56.591(-10)?   Adding: Milk Tea (mocha@foo.com)
I20200513-23:20:56.598(-10)?   Adding: Milk Tea (hello@foo.com)
I20200513-23:20:56.605(-10)? Creating default profile data.
I20200513-23:20:56.606(-10)?   Adding: Profile Admin for (admin@foo.com)
I20200513-23:20:56.622(-10)?   Adding: Profile John for (john@foo.com)
I20200513-23:20:56.630(-10)? Creating default restaruant data.
I20200513-23:20:56.631(-10)?  Adding: Restaurant listing: Starbucks for starbucks@foo.com
I20200513-23:20:56.647(-10)?  Adding: Restaurant listing: Raising Canes for raisingcanes@foo.com
I20200513-23:20:56.651(-10)?  Adding: Restaurant listing: Bale for bale@foo.com
I20200513-23:20:56.655(-10)?  Adding: Restaurant listing: Jersey Mikes for jerseymikes@foo.com
I20200513-23:20:56.661(-10)?  Adding: Restaurant listing: Jamba Juice for jambajuice@foo.com
I20200513-23:20:56.665(-10)?  Adding: Restaurant listing: Panda Express for pandaexpress@foo.com
I20200513-23:20:56.670(-10)?  Adding: Restaurant listing: Dunkin Donuts for dunkindonuts@foo.com
I20200513-23:20:56.676(-10)?  Adding: Restaurant listing: Shaka Shaka for shakashaka@foo.com
I20200513-23:20:56.682(-10)?  Adding: Restaurant listing: Subway for subway@foo.com
I20200513-23:20:56.799(-10)?  Adding: Pending orders: Bread,Earl Grey Tea for admin@foo.com
I20200513-23:20:56.802(-10)?  Adding: Pending orders: Chicken for john@foo.com
I20200513-23:20:56.833(-10)?  Adding Menu Item: White Mocha for starbucks@foo.com
I20200513-23:20:56.834(-10)?  Adding Menu Item: Flat White for starbucks@foo.com
I20200513-23:20:56.837(-10)?  Adding Menu Item: Americano for starbucks@foo.com
I20200513-23:20:56.839(-10)?  Adding Menu Item: Cappuccino for starbucks@foo.com
I20200513-23:20:56.840(-10)?  Adding Menu Item: Earl Grey Tea for starbucks@foo.com
I20200513-23:20:56.841(-10)?  Adding Menu Item: Matcha Green Tea Latte for starbucks@foo.com
I20200513-23:20:56.844(-10)?  Adding Menu Item: Chicken Fingers for raisingcanes@foo.com
I20200513-23:20:56.847(-10)?  Adding Menu Item: Pho for bale@foo.com
I20200513-23:20:56.848(-10)?  Adding Menu Item: Char Siu Fried Rice for bale@foo.com
I20200513-23:20:56.849(-10)?  Adding Menu Item: Jersey Shore's Favorite for jerseymikes@foo.com
I20200513-23:20:56.851(-10)?  Adding Menu Item: Mike's Famous Philly for jerseymikes@foo.com
I20200513-23:20:56.852(-10)?  Adding Menu Item: BBQ Beef for jerseymikes@foo.com
I20200513-23:20:56.854(-10)?  Adding Menu Item: Jersey Shore's Favorite for jerseymikes@foo.com
I20200513-23:20:56.858(-10)?  Adding Menu Item: Club Supreme for jerseymikes@foo.com
I20200513-23:20:56.859(-10)?  Adding Menu Item: Turkey and Provolone for jerseymikes@foo.com
I20200513-23:20:56.861(-10)?  Adding Menu Item: Brownie for jerseymikes@foo.com
I20200513-23:20:56.862(-10)?  Adding Menu Item: Cookie for jerseymikes@foo.com
I20200513-23:20:56.863(-10)?  Adding Menu Item: Giant Drink and Chips for jerseymikes@foo.com
I20200513-23:20:56.866(-10)?  Adding Menu Item: Pureleaf Tea & Chips for jerseymikes@foo.com
I20200513-23:20:56.869(-10)?  Adding Menu Item: Avocado Smoothie for shakashaka@foo.com
I20200513-23:20:56.903(-10)?  Adding Menu Item: Banana Smoothie for shakashaka@foo.com
I20200513-23:20:56.907(-10)?  Adding Menu Item: Grape Smoothie for shakashaka@foo.com
I20200513-23:20:56.908(-10)?  Adding Menu Item: Green Tea for shakashaka@foo.com
I20200513-23:20:56.909(-10)?  Adding Menu Item: Black Lemon Tea for shakashaka@foo.com
I20200513-23:20:56.910(-10)?  Adding Menu Item: Green Lemon Tea for shakashaka@foo.com
I20200513-23:20:56.912(-10)?  Adding Menu Item: Bubble Black Milk Tea for shakashaka@foo.com
I20200513-23:20:56.915(-10)?  Adding Menu Item: Taro Black Milk Tea for shakashaka@foo.com
I20200513-23:20:56.918(-10)?  Adding Menu Item: Orange C-Booster for jambajuice@foo.com
I20200513-23:20:56.919(-10)?  Adding Menu Item: Electric Berry Lemonade for jambajuice@foo.com
I20200513-23:20:56.921(-10)?  Adding Menu Item: Apple 'N Greens for jambajuice@foo.com
I20200513-23:20:56.922(-10)?  Adding Menu Item: Strawberry Wild for jambajuice@foo.com
I20200513-23:20:56.927(-10)?  Adding Menu Item: Matcha Green Tea for jambajuice@foo.com
I20200513-23:20:56.928(-10)?  Adding Menu Item: Acai Primo for jambajuice@foo.com
I20200513-23:20:56.930(-10)?  Adding Menu Item: Orange Chicken for pandaexpress@foo.com
I20200513-23:20:56.931(-10)?  Adding Menu Item: Kung Pao Chicken for pandaexpress@foo.com
I20200513-23:20:56.932(-10)?  Adding Menu Item: Teriyaki Chicken for pandaexpress@foo.com
I20200513-23:20:56.936(-10)?  Adding Menu Item: Beef Broccoli for pandaexpress@foo.com
I20200513-23:20:56.942(-10)?  Adding Menu Item: Black Pepper Angus Steak for pandaexpress@foo.com
I20200513-23:20:56.949(-10)?  Adding Menu Item: SweetFire Chicken for pandaexpress@foo.com
I20200513-23:20:56.957(-10)?  Adding Menu Item: Firecracker Shrimp for pandaexpress@foo.com
I20200513-23:20:56.965(-10)?  Adding Menu Item: Mushroom Chicken for pandaexpress@foo.com
I20200513-23:20:56.975(-10)?  Adding Menu Item: Honey Walnut Shrimp for pandaexpress@foo.com
I20200513-23:20:56.984(-10)?  Adding Menu Item: Chicken Egg Roll for pandaexpress@foo.com
I20200513-23:20:56.990(-10)?  Adding Menu Item: Iced Coffee for dunkindonuts@foo.com
I20200513-23:20:56.999(-10)?  Adding Menu Item: Iced Macchiato for dunkindonuts@foo.com
I20200513-23:20:57.010(-10)?  Adding Menu Item: Hot Coffee for dunkindonuts@foo.com
I20200513-23:20:57.019(-10)?  Adding Menu Item: Cold Brew for dunkindonuts@foo.com
I20200513-23:20:57.030(-10)?  Adding Menu Item: Americano for dunkindonuts@foo.com
I20200513-23:20:57.051(-10)?  Adding Menu Item: Latte for dunkindonuts@foo.com
I20200513-23:20:57.065(-10)?  Adding Menu Item: Macchiato for dunkindonuts@foo.com
I20200513-23:20:57.073(-10)?  Adding Menu Item: Espresso for dunkindonuts@foo.com
I20200513-23:20:57.085(-10)?  Adding Menu Item: Capuccino for dunkindonuts@foo.com
I20200513-23:20:57.093(-10)?  Adding Menu Item: Vanilla Chai for dunkindonuts@foo.com
I20200513-23:20:57.106(-10)?  Adding Menu Item: Iced Tea for dunkindonuts@foo.com
I20200513-23:20:57.122(-10)?  Adding Menu Item: Muffins for dunkindonuts@foo.com
I20200513-23:20:57.132(-10)?  Adding Menu Item: Bagel with Cream Cheese for dunkindonuts@foo.com
I20200513-23:20:57.143(-10)?  Adding Menu Item: Donuts for dunkindonuts@foo.com
I20200513-23:20:57.150(-10)?  Adding Menu Item: Beyond Sausage for dunkindonuts@foo.com
I20200513-23:20:57.155(-10)?  Adding Menu Item: Turkey Sausage for dunkindonuts@foo.com
I20200513-23:20:57.163(-10)?  Adding Menu Item: Egg & Cheese for dunkindonuts@foo.com
I20200513-23:20:57.168(-10)?  Adding Menu Item: Veggie Egg White for dunkindonuts@foo.com
I20200513-23:20:57.173(-10)?  Adding Menu Item: Black Forest Ham for subway@foo.com
I20200513-23:20:57.179(-10)?  Adding Menu Item: Chicken and Bacon Ranch Melt for subway@foo.com
I20200513-23:20:57.186(-10)?  Adding Menu Item: Meatball Marinara for subway@foo.com
I20200513-23:20:57.190(-10)?  Adding Menu Item: Spicy Italian for subway@foo.com
I20200513-23:20:57.196(-10)?  Adding Menu Item: Sweet Onion Chicken Teriyaki for subway@foo.com
I20200513-23:20:57.201(-10)?  Adding Menu Item: Black Forest Ham Salad for subway@foo.com
I20200513-23:20:57.205(-10)?  Adding Menu Item: Meatball Marinara Salad for subway@foo.com
I20200513-23:20:57.212(-10)?  Adding Menu Item: Veggie Delite Salad for subway@foo.com
I20200513-23:20:57.218(-10)? Creating past order data.
I20200513-23:20:57.219(-10)?  Adding: Past orders: Bale for admin@foo.com
I20200513-23:20:57.235(-10)?  Adding: Past orders: Pieology for john@foo.com
I20200513-23:20:57.240(-10)?  Adding: Past orders: Shaka Shaka for john@foo.com
I20200513-23:20:57.246(-10)? Creating past delivery data.
I20200513-23:20:57.247(-10)?  Adding: Past orders: Raising Cane's for admin@foo.com
I20200513-23:20:57.262(-10)?  Adding: Past orders: Starbucks for john@foo.com
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

## Project Development History

To track our progress via Milestones:
- [Milestone 1](https://github.com/ono-otw/ono-otw/projects/3)
- [Milestone 2](https://github.com/ono-otw/ono-otw/projects/2)
- [Milestone 3](https://github.com/ono-otw/ono-otw/projects/4)


### Milestone 1: Mockup and Deployment
- Implemented landing page
- Created Ono-on the way logo
- Created various mock ups 
- Deployed to Galaxy

<img src="/Images/M1_Done.png">

**To see which issues have been finished during M1, please click: [Milestone 1](https://github.com/ono-otw/ono-otw/projects/3)**

### Milestone 2: Data model development
The goal of Milestone 2 is to integrate other pages of the application such as ability for the customer to order and a deliver to accept the order. This involves the implemetation of our data model, which will include multiple schemas to ensure the data entered is is valid. 
- Implemented database for:
   - Profiles
   - Cart 
   - PendingOrders
   - Restaurants
- Added functionality: 
   - Edit Profile
   - Submitting your order sends it to the "Accept Order" page
   - Ability for Admin to delete restaurants
- Created layout for menu

<img src="/Images/M2_Done.png">

**To see which issues have been finished during M2, please click [here](https://github.com/ono-otw/ono-otw/projects/2).**


### Milestone 3: Final touches
The goal of Milestone 3 is to finish and finalize the fuctionality for students to accept/deliver food, and polish other aspects such as searching by category. If time permits, some extra enhancements would include the ability to see past/recent orders and/or deliveries, as well as a user's favorite place to eat. 

<img src="/Images/M3_Done.png">

**To see which issues have been finished during M3, please click [here](https://github.com/ono-otw/ono-otw/projects/4)**

## Community Feedback
**Luke M.**
- Homepage looks really nice, but the "Order Food" could be centered vertically. The Mobile part is also out of place. 
- It would be better to have a toggle for the courier and the customer in the Nav bar.
- The card should be clickable and not the name itself. The tags should also be inside the card
- User is able to submit an order without putting their location, even when the field is marked as required.

**Jason K.**
- Clean looking website. Flows well. 
- The landing page has a white word that lays on top of white background
-The animation for adding to cart is cool
- Large selection to choose from 
- Missing some food items.
- User is able to submit an order without putting their location, even when the field is marked as required

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







