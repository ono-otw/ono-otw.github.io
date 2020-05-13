## Table of contents
* [Overview](#overview)
* [Goals](#goals)
* [User Guide](#user-guide)
* [Developer Guide](#developer-guide)
* [Development History](#project-development-history)
* [Developers](#developers)
* [Running Deployment](http://ono-otw.meteorapp.com/)

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
This where you can see the profile of the deliverer or customer. It shows the user's favorites, and past orders/delivery. A functional rating system is yet to be implemented. 
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

The "Cart" button at the bottom brings up your current cart. 
<img src="/Images/Menu-Mockup-3.png">

Below is a gif that shows the capabilites listed above:
<img src="/Images/Menu-Mockup-gif.gif">


###  Cart Page 
This is how the cart page will look like upon checking out.
<img src="/Images/Cart.png">

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


### Admin Page 
This is the admin page where admins and/or moderators can approve restaurants to be added to the list. Restaurants can also be deleted if necessary. 
<img src="/Images/ono otw_admin.png">

Clicking the "view" button brings up a preview of the restaurant:
<img src="/Images/ono otw_admin-1.png">

Admins and/or moderators are also allowed to edit restaurant fields:
<img src="/Images/ono otw_admin-2.png">

Admins are also able to add a restaurant:
<img src="/Images/Add-Restaurant.png">

### Tracking (Mock-Up)
Allows you to track your order and communicate with the deliverer.
<img src="/Images/tracking.png">

### Developer Guide
1. Install meteor
2. Download a copy of ono-otw. You can download either using Github Desktop (recommended) or by extracting the .zip. 
3. cd into the /app directory and install the required libraries with:
 `meteor npm install `
4. Once the libraries are installed, the application can be ran by using: `meteor npm run start`
 
 Upon running the app the first time, it will create some default users and data. Here is the output. 
   ````
W20200512-19:30:40.756(-10)? (STDERR) Note: you are using a pure-JavaScript implementation of bcrypt.
W20200512-19:30:41.196(-10)? (STDERR) While this implementation will work correctly, it is known to be
W20200512-19:30:41.198(-10)? (STDERR) approximately three times slower than the native implementation.
W20200512-19:30:41.200(-10)? (STDERR) In order to use the native implementation instead, run
W20200512-19:30:41.206(-10)? (STDERR)
W20200512-19:30:41.213(-10)? (STDERR)   meteor npm install --save bcrypt
W20200512-19:30:41.223(-10)? (STDERR)
W20200512-19:30:41.225(-10)? (STDERR) in the root directory of your application.
I20200512-19:30:42.337(-10)? Creating the default user(s)
I20200512-19:30:42.339(-10)?   Creating user admin@foo.com.
I20200512-19:30:42.342(-10)?   Creating user john@foo.com.
I20200512-19:30:42.551(-10)? Creating testing cart data.
I20200512-19:30:42.554(-10)?   Adding: Milk Tea (john@foo.com)
I20200512-19:30:42.556(-10)?   Adding: Mocha Frappe (john@foo.com)
I20200512-19:30:42.558(-10)?   Adding: Mocha Frappe (admin@foo.com)
I20200512-19:30:42.559(-10)?   Adding: Earl Grey Tea (admin@foo.com)
I20200512-19:30:42.593(-10)?   Adding: Milk Tea (test@foo.com)
I20200512-19:30:42.596(-10)?   Adding: Milk Tea (mocha@foo.com)
I20200512-19:30:42.597(-10)?   Adding: Milk Tea (hello@foo.com)
I20200512-19:30:42.598(-10)? Creating default profile data.
I20200512-19:30:42.599(-10)?   Adding: Profile Admin for (admin@foo.com)
I20200512-19:30:42.600(-10)?   Adding: Profile John for (john@foo.com)
I20200512-19:30:42.604(-10)? Creating default restaruant data.
I20200512-19:30:42.606(-10)?  Adding: Restaurant listing: Starbucks for starbucks@foo.com
I20200512-19:30:42.607(-10)?  Adding: Restaurant listing: Raising Canes for raisingcanes@foo.com
I20200512-19:30:42.608(-10)?  Adding: Restaurant listing: Bale for bale@foo.com
I20200512-19:30:42.609(-10)?  Adding: Restaurant listing: Jersey Mikes for jerseymikes@foo.com
I20200512-19:30:42.610(-10)?  Adding: Restaurant listing: Jamba Juice for jambajuice@foo.com
I20200512-19:30:42.715(-10)?  Adding: Restaurant listing: Panda Express for pandaexpress@foo.com
I20200512-19:30:42.718(-10)?  Adding: Restaurant listing: Dunkin Donuts for dunkindonuts@foo.com
I20200512-19:30:42.720(-10)?  Adding: Restaurant listing: Shaka Shaka for shakashaka@foo.com
I20200512-19:30:42.721(-10)?  Adding: Restaurant listing: Subway for subway@foo.com
I20200512-19:30:42.736(-10)?  Adding: Pending orders: Bread,Earl Grey Tea for admin@foo.com
I20200512-19:30:42.738(-10)?  Adding: Pending orders: Chicken for john@foo.com
I20200512-19:30:42.739(-10)?  Adding Menu Item: White Mocha for starbucks@foo.com
I20200512-19:30:42.786(-10)?  Adding Menu Item: Flat White for starbucks@foo.com
I20200512-19:30:42.788(-10)?  Adding Menu Item: Americano for starbucks@foo.com
I20200512-19:30:42.789(-10)?  Adding Menu Item: Cappuccino for starbucks@foo.com
I20200512-19:30:42.790(-10)?  Adding Menu Item: Earl Grey Tea for starbucks@foo.com
I20200512-19:30:42.791(-10)?  Adding Menu Item: Matcha Green Tea Latte for starbucks@foo.com
I20200512-19:30:42.793(-10)?  Adding Menu Item: Chicken Fingers for raisingcanes@foo.com
I20200512-19:30:42.794(-10)?  Adding Menu Item: Pho for bale@foo.com
I20200512-19:30:42.797(-10)?  Adding Menu Item: Char Siu Fried Rice for bale@foo.com
I20200512-19:30:42.799(-10)?  Adding Menu Item: Jersey Shore's Favorite for jerseymikes@foo.com
I20200512-19:30:42.801(-10)?  Adding Menu Item: Mike's Famous Philly for jerseymikes@foo.com
I20200512-19:30:42.909(-10)?  Adding Menu Item: BBQ Beef for jerseymikes@foo.com
I20200512-19:30:42.920(-10)?  Adding Menu Item: Jersey Shore's Favorite for jerseymikes@foo.com
I20200512-19:30:42.922(-10)?  Adding Menu Item: Club Supreme for jerseymikes@foo.com
I20200512-19:30:42.924(-10)?  Adding Menu Item: Turkey and Provolone for jerseymikes@foo.com
I20200512-19:30:42.926(-10)?  Adding Menu Item: Brownie for jerseymikes@foo.com
I20200512-19:30:42.928(-10)?  Adding Menu Item: Cookie for jerseymikes@foo.com
I20200512-19:30:42.929(-10)?  Adding Menu Item: Giant Drink and Chips for jerseymikes@foo.com
I20200512-19:30:42.932(-10)?  Adding Menu Item: Pureleaf Tea & Chips for jerseymikes@foo.com
I20200512-19:30:42.934(-10)?  Adding Menu Item: Avocado Smoothie for shakashaka@foo.com
I20200512-19:30:42.936(-10)?  Adding Menu Item: Banana Smoothie for shakashaka@foo.com
I20200512-19:30:42.938(-10)?  Adding Menu Item: Grape Smoothie for shakashaka@foo.com
I20200512-19:30:42.939(-10)?  Adding Menu Item: Green Tea for shakashaka@foo.com
I20200512-19:30:42.943(-10)?  Adding Menu Item: Black Lemon Tea for shakashaka@foo.com
I20200512-19:30:42.945(-10)?  Adding Menu Item: Green Lemon Tea for shakashaka@foo.com
I20200512-19:30:42.946(-10)?  Adding Menu Item: Bubble Black Milk Tea for shakashaka@foo.com
I20200512-19:30:42.948(-10)?  Adding Menu Item: Taro Black Milk Tea for shakashaka@foo.com
I20200512-19:30:42.950(-10)?  Adding Menu Item: Orange C-Booster for jambajuice@foo.com
I20200512-19:30:42.954(-10)?  Adding Menu Item: Apple 'N Greens for jambajuice@foo.com
I20200512-19:30:42.956(-10)?  Adding Menu Item: Strawberry Wild for jambajuice@foo.com
I20200512-19:30:42.957(-10)?  Adding Menu Item: Matcha Green Tea for jambajuice@foo.com
I20200512-19:30:42.958(-10)?  Adding Menu Item: Orange Chicken for pandaexpress@foo.com
I20200512-19:30:42.960(-10)?  Adding Menu Item: Kung Pao Chicken for pandaexpress@foo.com
I20200512-19:30:42.963(-10)?  Adding Menu Item: Teriyaki Chicken for pandaexpress@foo.com
I20200512-19:30:42.965(-10)?  Adding Menu Item: Beef Broccoli for pandaexpress@foo.com
I20200512-19:30:42.967(-10)?  Adding Menu Item: Black Pepper Angus Steak for pandaexpress@foo.com
I20200512-19:30:42.969(-10)?  Adding Menu Item: SweetFire Chicken for pandaexpress@foo.com
I20200512-19:30:42.970(-10)?  Adding Menu Item: Firecracker Shrimp for pandaexpress@foo.com
I20200512-19:30:42.973(-10)?  Adding Menu Item: Mushroom Chicken for pandaexpress@foo.com
I20200512-19:30:43.083(-10)?  Adding Menu Item: Honey Walnut Shrimp for pandaexpress@foo.com
I20200512-19:30:43.086(-10)?  Adding Menu Item: Chicken Egg Roll for pandaexpress@foo.com
I20200512-19:30:43.088(-10)?  Adding Menu Item: Iced Coffee for dunkindonuts@foo.com
I20200512-19:30:43.089(-10)?  Adding Menu Item: Iced Macchiato for dunkindonuts@foo.com
I20200512-19:30:43.091(-10)?  Adding Menu Item: Black Forest Ham for subway@foo.com
I20200512-19:30:43.093(-10)?  Adding Menu Item: Chicken and Bacon Ranch Melt for subway@foo.com
I20200512-19:30:43.095(-10)?  Adding Menu Item: Meatball Marinara for subway@foo.com
I20200512-19:30:43.099(-10)?  Adding Menu Item: Spicy Italian for subway@foo.com
I20200512-19:30:43.100(-10)?  Adding Menu Item: Sweet Onion Chicken Teriyaki for subway@foo.com
I20200512-19:30:43.103(-10)?  Adding Menu Item: Black Forest Ham Salad for subway@foo.com
I20200512-19:30:43.105(-10)?  Adding Menu Item: Meatball Marinara Salad for subway@foo.com
I20200512-19:30:43.108(-10)?  Adding Menu Item: Veggie Delite Salad for subway@foo.com
I20200512-19:30:43.110(-10)? Creating past order data.
I20200512-19:30:43.111(-10)?  Adding: Past orders: Bale for admin@foo.com
I20200512-19:30:43.112(-10)?  Adding: Past orders: Pieology for john@foo.com
I20200512-19:30:43.114(-10)? Creating past delivery data.
I20200512-19:30:43.117(-10)?  Adding: Past orders: Raising Cane's for admin@foo.com
I20200512-19:30:43.119(-10)?  Adding: Past orders: Starbucks for john@foo.com
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
Running deployment on Galaxy: [OOTW](http://ono-otw.meteorapp.com/)

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

**To see our current progress for M3, please click [here](https://github.com/ono-otw/ono-otw/projects/4)**


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







