# JTG       
### [Jennings Tactical Guns](https://jtg-django.herokuapp.com/)

We supply the tools, parts, and knowledge to have a custom firearm built to fit your needs.

The website can be viewed [here.](https://jtg-django.herokuapp.com/)

# Table of Contents:

1. [User Experience](#UX)
2. [Design](#Design)
3. [Wireframes](#Wireframes)
4. [Features](#Features)
5. [Technologies Used](#Tech)
6. [Testing](#Testing)
7. [Deployment](#Deployment)
8. [Credits](#Credits)
9. [Disclaimer](#Disclaimer)

# <a name="UX"></a>User Experience

### Project Goals

The goal of this project is to promote a private business that is offering custom firearms, weapons safety classes, and ammunition. The project will provide a platform for the customers to search, preview and purchase the products offered by JTG.  Users can create an account, sign in and out, add items to their cart, make payments, prefill shipping and billing information and view their past orders on My Profile page.  All these functions are available to non-registered users as well, except the non-registered will be required to fill out the contact form from scratch.

The website is easy to navigate with basic menu options and shopping cart preview available at all times. 

### User Stories

>As a user I want to be able to navigate the site easily and be able to preview products offered before making a choice.

>As a user I want to be able to select the product, add it to my shopping cart, and modify it if needed. 

>As a user I want to view, select, order, and make a payment for my order all on one platform without having to leave the website.

>As a user I want to save my contact information so I don't have to re-enter it every time I make a purchase on this website.

>As a user I want to view products by category.

>As a user I want to be able to view my past purchases from this website.

>As a user I want to be able to shop from my phone.

>As the shop owner, I want to be able to add, edit or remove products I offer on my website.

>As the shop owner I want payments to be handled automatically without manual interference. 

# Design

### Overview

The overall design reflects the main theme of the shop. The background images are selected to showcase the custom firearms available to be built. The background images are also fixed on the screen as the user scrolls through the content of the page until he reaches the next section of the website which is separated by a different color background. The color scheme selected flows well with the background images and the website looks styled.

### Fonts

The font used across the whole website is [Google Roboto.](https://fonts.google.com/specimen/Roboto?preview.text_type=custom)

### Icons

The icons used across the website come from [Font Awesome.](https://fontawesome.com/)

### Images

The images used as a background and in the gallery section are showcasing the custom firearms that can be built by JTG.

# Wireframes

I used Balsamiq to create the wireframes and they can be found as follows:

* [Desktop and Tablet](https://github.com/aavasylenko/jtg-django/blob/master/New%20Wireframe%201.png)
* [Mobile](https://github.com/aavasylenko/jtg-django/blob/master/New%20Wireframe%202.png)


### Database Design

* The development database is [sqlite3](https://www.sqlite.org/) which is built-in Django.
* The production database is [PostgresSQL](https://www.postgresql.org/) and is hosted by Heroku.

### Data Models


**The Category Model:**

Name  | Database Name | Type
----- | ------------- | ----
Category | category | CharField
Name | name | CharField
Friendly Name | friendly_name | CharField

**The Product Model:**

Name  | Database Name | Type
----- | ------------- | ----
Category | category | CharField
Sku   | sku | CharField
Name | name | CharField
Description | description | CharField
Price | price | DecimalField
Is Available | is_available | BooleanField
Image URL | image_url | URLField
Image | image | ImageField

**The Order Model:**

Name | Database Name | Type
---- | ------------- | ----
Order Number | order_number | CharField
User Profile | user_profile | ForeignKey
Full Name | full_name | CharField
Email | email | EmailField
Phone Number | phone_number | CharField
Country | country | CountryField
Postal Code | postal_code | CharField
State | state | USStateField
City | city | CharField
Street Address 1 | street_address1 | CharField
Street Address 2 | street_address2 | CharField
Date | date | DateField
Delivery Cost | delivery_cost | DecimalField
Order Total | order_total | DecimalField
Grand Total | grand_total | DecimalField
Original Bag | original_bag | TextField
Stripe PID | stripe_pid | CharField

**The Order Line Item Model:**

Name | Database Name | Type
---- | ------------- | ----
Order | order | ForeignKey
Product | product | ForeignKey
Quantity | quantity | IntegerField
Lineitem Total | lineitem_total | DecimalField

**The User Profile Model:**

Name | Database Name | Type
---- | ------------- | ----
user | user | OneToOneField
Default Name | default_name | CharField
Default Phone Number | default_phone_number | CharField
Default Street Address 1 | default_street_address1 | CharField
Default Street Address 2 | default_street_address2 | CharField
Default City | default_city | CharField
Default State | default_state | USStateField
Default Postal Code | default_postal_code | CharField
Default Country | default_country | CountryField

# Features

### Existing Features

* Users can sign in, sign out or register and save their contact information on file for faster checkout. 

* Registered users can update their information and view their past purchases on "My Profile" page.

* Users can shop by category or all categories. The search bar is available in every category and will search for products within all categories no matter what the user is currently viewing.

* If an item is out of stock, the "Add to bag" button is disabled.

* Pop-up messages in the top right corner will disappear automatically after a few seconds for the user's convenience to continue exploring the website.

* Users can update the quantity of a certain product right on their Shopping Bag page.

* For a checkout registered users can use the prefilled contact form including their name.

* Users can make a payment without having to leave the website because it's using Stripe API.

* Shop owner can Add/Edit/Remove any product directly from the Shop page or the individual product page.

* Before deleting a product, the shop owner will be asked to confirm this intent via Bootstrap modal.

* "Request a quote" button will trigger the user's email to open and compose an email with a prefilled title.

* Gallery Carousel updated automatically or a user can click through the pictures himself.

* Sort By Price option is available in all categories.

### Features left to implement

* Cancel the order before it ships.

* Re-order the same items that were purchased before.

* Product recommendations based on the user's search history.

* Ability to leave a review for a product.


# <a name="Tech"></a>Technologies Used

Languages

* [HTML](https://www.w3schools.com/default.asp)
* [CSS](https://www.w3schools.com/css/default.asp)
* [JavaScript](https://www.javascript.com)
* [Python](https://www.python.org)

Tools & Libraries

* [jQuery](https://jquery.com)
* [Django](https://www.djangoproject.com)
* [Git](https://git-scm.com) 
* [Bootstrap](https://getbootstrap.com)
* [Font-Awewsome](https://fontawesome.com)
* [Gunicorn](https://gunicorn.org)
* [PIP](https://pypi.org/project/pip/)
* [Psycopg2](https://pypi.org/project/psycopg2/)
* [Stripe](https://stripe.com/)
* [GitPod](https://www.gitpod.io)
* [Heroku](https://www.heroku.com)

Databases

* [PostgresSQL - production](https://www.postgresql.org)
* [SQLite3 - development](https://www.sqlite.org/)

# Testing

All the existing features have been tested on Desktop, Mobile, and Tablet screens. 

## Responsiveness
The website was tested to all default device sizes provided by Chrome Developer Tools:

  - 360 x 640 Galaxy S5
  - 375 x 667 iPhone 6/7/8
  - 375 x 812 iPhone X
  - 411 x 731 Pixel 2
  - 411 x 823 Pixel 2 XL
  - 414 x 736 iPhone 6/7/8 Plus
  - 768 x 1024 iPad
  - 1024 x 1366 iPad Pro

## Code Validators
The following validators were used to test the code quality:
- [WC3 Markup Validator](https://validator.w3.org/nu/?doc=https%3A%2F%2Fjtg-django.herokuapp.com%2F) - the only errors returned is a "duplicate ID" error, which is expected because it's used for the Desktop navbar as well as Mobile navbar which is written in a different part of the code.

- [W3C Jigsaw CSS Validator](https://jigsaw.w3.org/css-validator/) - no errors were returned for my ```style.css``` file.

## Manual Testing

### Registration 
 1. Go to Sign In page.
 2. Click "Sign Up".
 3. Fill out your information.
 4. Verify that you received the email to confirm your registration.
 5. Use these credentials to sign in.

### Profile

1. After signing into your account go to "My Profile" page.
2. Update your information and verify the changes by clicking "Update Information"
3. Verify that you can now see "Sign Out" option when you are on "My Profile" page instead of "Sign In/My Profile"
4. Verify you can see your past purchases on this page (if any).

### Search Bar

1. Click on Shop -> Ammo.
2. Verify that the products you see on the page are only under the Ammo category.
3. Type in the search bar "aero".
4. Verify that you are now seeing all related products from the "Guns & Parts" category as well.
5. Type in "something" in the search bar.
6. Verify that "No Results Found" message appears.

### Sorting

1. Go to Shop -> All.
2. Click on "Sort by Price" icon next to the search bar. 
3. Verify that products are now sorted by price.
4. Conduct the same on each category.
5. Verify that only the relevant products are showing and now are sorted by price.

### Buttons

1. On Shop page find a product that is currently out of stock.
2. Try to hover over or click on the Add to Bag button.
3. Verify that the cursor changes as well as the button is non-clickable.

### Quantity

1. Open a product individual page by clicking on the product image or name.
2. Update the quantity to the desired number and click "Adde to Bag"
3. Click on Shopping Bag icon and verify that the product in your desired quantity appears in the shopping bag.
4. Updated the quantity again in the shopping bag and click "Update"
5. Verify that the quantity has been updated.

### Shopping Bag

1. Add a product into your shopping bag. 
2. Verify that this shopping bag is always visible in the menu bar with the total price of the items in your bag.
3. Remove any products from your bag.
4. Verify that the shopping bag icon disappeared from the menu bar.


### Checkout

1. Add a product into your shopping bag. 
2. Go to your Shopping Bag and click on "Secure Checkout"
3. Fill out the form and for Credit Card use the following:
    Card number: 4242 4242 4242 4242
    Expiration date: 04/24
    CVC: 242
    ZIP: 42424
4. Verify that your order has been placed successfully and the confirmation email has been received.

## User Stories Testing
   
>As a user I want to be able to navigate the site easily and be able to preview products offered before making a choice.

This user was able to achieve his goal by going to the JTG website and clicking Shop -> All.

>As a user I want to be able to select the product, add it to my shopping cart, and modify it if needed. 

This user was able to achieve his goal by Add to Bag button, go to his SHopping Cart and update the quantity of the product, and clicking Update.

>As a user I want to view, select, order, and make a payment for my order all on one platform without having to leave the website.

This user was able to achieve his goal by using Stripe which is built into the website.

>As a user I want to save my contact information so I don't have to re-enter it every time I make a purchase on this website.

This user was able to achieve his goal by registering on the website, clicking on My Profile and updating his contact information, and clicking Update. The next time this user was checking out his information was already prefilled for him at the checkout.

>As a user I want to view products by category.

This user was able to achieve his goal by clicking Shop -> Ammo, then switching it to "Guns & Parts"

>As a user I want to be able to view my past purchases from this website.

This user was able to achieve his goal by registering on the website, clicking on My Profile, and viewing his past purchases.

>As a user I want to be able to shop from my phone.

This user was able to achieve his goal by opening to JTG website on his mobile device.

>As the shop owner, I want to be able to add, edit or remove products I offer on my website.

The shop owner was able to achieve his goal by signing into his admin account and seeing the options to add/edit/remove the product on the Shop page. He was also able to do it by opening an individual product page.

>As the shop owner I want payments to be handled automatically without manual interference. 

The shop owner was able to achieve his goal with this website by connecting his Stripe account.

# Deployment

### Tools required to be installed
- Python 3 
- Git
- Heroku CLI
- Stripe Account

### Cloning and setting up locally instructions:
#### 1. Clone website
1. Go to [GitHub](https://github.com/aavasylenko)
2. Click Repositories.
3. Locate jtg-django.
4. Open [JTG](https://github.com/aavasylenko/jtg-django)
5. Click "Download".
6. Or clone directly from the terminal using: ```got clone https://github.com/aavasylenko/jtg-django.git```

#### 2. Install Requirements.
1. Install the libraries/dependencies from requirements.txt by typing ```pip3 install -r requirements.txt``` in the terminal command field.

#### 3. Set up the database keys
1. Create a python file called ```env.py```.
2. Inside the env.py file add the following code:
 on the top line ```import os```.
 Then below add these lines:
 
 
```os.environ.setdefault("SECRET_KEY", "your_django_secret_key")```

```os.environ.setdefault("STRIPE_PUBLIC_KEY", "your_stripe_public_key")```

```os.environ.setdefault("STRIPE_SECRET_KEY", "your_stripe_secret_key")```

```os.environ.setdefault("STRIPE_WH_SECRET", "your_stripe_wh_secret")```

```os.environ.setdefault("EMAIL_HOST_USER", "your_email_host_user")```

```os.environ.setdefault("EMAIL_HOST_PASS", "your_email_host_pass")```

#### 5. Run the Project locally
 - Migrate models into your database by entering into your terminal ```python3 manage.py migrate```
 - Create your Superuser ```python3 manage.py createsuperuser```
 - Run the app by entering ```python3 manage.py runserver```


#### 6. Before committing and pushing your code to GitHub:
- Make sure to create ```.gitignore``` file.
- Type ```env.py``` inside your ```.gitignore``` file. This is done to prevent publishing your passwords or secret keys to a public website.


### Deploy on Heroku
#### 1. Set up Heroku
1. Create an account on [Heroku](https://dashboard.heroku.com/login).
2. Click "Create new app".
3. Give it a unique name and choose your region.
4. Find your App name on the dashboard.
6. Click Settings, then Config Vars, and fill in the variables from your ```env.py``` file


| Key        | Value           | 
|:------------- |:-------------| 
|  DATABASE_URL  | <your_database_url> | 
|  SECRET_KEY  | <your_secret_key> | 
|  STRIPE_PUBLIC_KEY  | <your_stripe_publice_key> | 
|  STRIPE_SECRET  | <your_stripe_secret_key> |
|  STRIPE_WH_SECRET  | <your_stripe_wh_secret> |
|  EMAIL_HOST_USER  | <your_email_host_user> |
|  EMAIL_HOST_PASS  | <your_email_host_pass> |


#### Prepare your code:
1. In your IDE create a ```Procfile```. It does not have an extension and make sure you capitalize the first letter ```P```. You can do this with the following command: ```echo web: gunicorn jtg_django.wsgi:application > Procfile```
2. Perform the following command in your terminal: ```pip3 freeze > requirements.txt```


#### 3. Deploy to Heroku
1. In your Terminal type ```heroku login -i```.
2. Log into your Heroku account using your credentials.
3. Add your files to staging by running ```git add -A```
4. Commit your code: ```git commit -m "your_message_here"
5. Set up your Heroku remote by running ```heroku git:remote -a <the_app_name_you_created>```
6. Then ```git push heroku master```.  
7. Start running your app using this command in your terminal ```heroku ps:scale web=1```
8. Open the Heroku website.
9. Navigate to your app, and click Open App.

#### Alternative method to push to Heroku directly from GitHub
1. Push all your code to a GitHub repository.
2. On the Heroku website under "Deploy" tab navigate to "App connected to GitHub"
3. Connect your GitHub account and find your GitHub repository name.
4. You can set Automatic Deploys from your chosen branch or navigate to "Manual Deploy" and click on "Deploy Branch"
5. Wait until the app is deployed and click "Open App". 

## Credits

This code was fully inspired by CodeInstitute's Django project. The project has inspired me to create even more useful functionality than I would want to use myself.

### Content
- All the content is attributed to Jennings Tactical Guns, LLC.

### Media
- The photos used in this site were obtained directly from Jennings Tactical Guns, LLC shop owner. 

### Acknowledgements

- I received inspiration for this project from CodeInstitute.

# Disclaimer

The content on this site is not for commercial use.
