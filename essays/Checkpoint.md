---
layout: essay
type: essay
title: "Checkpoint Assignment #3"
# All dates must be YYYY-MM-DD format!
date: 2022-11-29
published: true
labels:
  - Assignment 3
  - MIS
---
#### 1. Show what each page will look like. The pages do not have to be "functional" but the design should be clear.

Click [here](https://youtu.be/NF6ctpJZDvI) to view a PowerPoint screencast presentation covering the design of each page on my site. 

###### Mapping the site path
![sitemap]

#### 2. Describe your design for your site’s shopping cart. That is, will it be a separate page that the user can view and edit, or will it be integrated into the product pages? If so, describe in detail how this will work on your site. Provide several examples of using the cart.

I plan to integreate my site's shooping cart into the home and product pages so that users can view it without leaving the page. The cart will be toggled in and out with a button, similarly to a side navigation bar, and will store the user's purchase information based on the data within the user's session. Once a user selects a quantity from a product, there will be an 'add to cart' button and once clicked, this button will create a new key-value pair in the user's session. The user can add to the cart at any time, but in order to proceed to the invoice, the user must be logged in. If not, they are directed to the login page. 

In the cart, the user has the choice to add or remove quantities of an item they already selected. The quantity that the user enters will be limited to the inventory available and if the user lowers the quantity they selected to 0, a message will appear saying something similar to 'Selecting 0 quantities will remove this item from your order when you proceed to checkout'.


#### 3. Explain specifically how you will use sessions to manage your shopping cart. In particular, what shopping cart data will be stored in the session, and what data format will be used (NOT what data type, but the format like with the data format used for your registration data). Use code examples showing what data structures (such as arrays and their objects) you will use to manage the shopping cart data and how they will be used in a session.

I will use sessions to manage the cart information by creating an array for each type of item and nesting objects within that array for each individual product. This way, I can store the name and price of each item to be displayed in the cart. The session information will be maintained on the server side, and every time a request for the cart is made, this information will be presented to the user on the client side. 

This is an example of how the purchase information is going to be added and stored in the session:
request.session\['Shoes'] = \[{"name": "HunterxHunter", "price": 200, "quantityPurchased": 1}];

Every time the user adds another product, an array.push is performed to add another object. If the user changes the quantity of an product they selected, that product's object will be called on and its quantityPurchased value will be changed.

#### 4. How will you avoid access to your application when the user has not logged in or registered? What are the particular security concerns you must address?

Using cookies, I will assess whether the user is logged in or not on the server side using an if-else statement similarly to the Cookies and Sessions lab. If the user is not logged in, they will be directed to the log in page and will not be able to proceed to the invoice. After a certain amount of time, the user will be logged out as a security measure. 

#### 5. Upon a successful login, how do you provide personalization in your UI? Explain how you did or will do this (paste code if necessary)

Upon successful login, the login button in the nav bar will turn into a button with the user's name. When they click on that button, they will have the choice to edit their account or log out. There will also be a personalized message on the Home page and on the Invoice. The shopping cart icon in the nav bar will also have a number of total items next to it. I will carry out all of this by using the user's cookie and session information.

#### 6. If you are working with partners, how will you split up the work in your team so that you are working in parallel as effectively as possible? That is, who is doing what and when?

I am not working with a partner.

#### 7. How are you approaching Assignment 3 differently than Assignment 2?

I will not be using Assignment 2's files and I plan to have my layout finished before my data validation. Since Assignment 3's data validation is the same as Assignment 2, I want to have my pages created and my paths mapped out before anything so that the nav bar and shopping cart design is consistent throughout. 
