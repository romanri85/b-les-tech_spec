# b-les-tech_spec
Technical specification for b-les project

# 1. Project goals

Project goals are: to develop a website for the company which manufactures and sells(B2C -retail) interior doors in
Moscow, St. Petersburg and others cities in Russia.
The products of the company are: interior doors, door handles and other door hardware. The services of the company are:
delivery, installation, measurements, consulting, etc.
The visitor can read about the company, its product and services.

# 2. Website functionality

The website should have the following functionality:

1. "Main" page functionality.
2. "Catalog" page functionality.
3. "Where to buy" page functionality
4. Tag system for images.
5. "Doors in interior" page functionality
6. "About us" page functionality

## 2.1. "Main" page functionality

The main page should have the following blocks:

1. Navigation bar
2. Hero block with slider(6 slides - each slide represents a collection of the company, should have a reference to the
   collection page)
3. Top 10-12 most popular tags block
4. Collections list block
5. Our projects block
6. Our advantages block
7. Footer block

## 2.2 "Catalog" page functionality.

The visitor of the website can browse through products, using different filters: by price, by material, by color,
by collection, by design, whether the door has a glass or not. If "all" option of the filter is clicked other options
should be unchecked.
On hover on the name of the page in the navbar a new modal window should appear with the list of the collections, each
collection should have an image in this modal window. The visitor can click on the collection and go to the collection
page.
There are basic set of filters at the top of the page, the visitor can click on any of them and get the filtered
products.
After any of these sets of filters is applied, the relevant checkboxes are checked as well.
While browsing the products, the visitor can like them. Each product should have a number of likes the users Likes,
filters set-ups, products chosen by these set-ups
are saved into local storage of the browser.

### 2.2.1 Materials

There are 3 materials available: oak, beech and enamel.  
Some collections are available only in one material, some are available in two, or all(3) materials.
Therefore, some products can be available only in one material, some are available in two, or all(3) materials.

### 2.2.2 Collections

There are 6 collections of products available. Each product can be attached only to one collection. Each collection can
have one or more products. Each collection can be available in one or more materials. Each collection has a name and an
image(render).

### 2.2.3 Colors

Each material has its own color palette. Collections may be implemented in one, two or all(3) materials.
Thus, each product can have one, two or three color palettes, depending on what collection it belongs to.
Each color has a name and its own image(render).

### 2.2.4 Designs

Each collection can have only one design. Thus, each product can have only one design. Each design can have one or more
collections. Each design can have one or more products. There are three designs available: classic, modern and
neo-classic.

### 2.2.5 Glass

Each product can have a glass or not. In case the product has a glass, there can be one or more types of glass the user
can choose. The availability of the glass does not depend on the material, collection, color or design of the product.
Each glass has a name and an image(render). In case a product has several types of glass, there will be a picture for
each type of glass.

### 2.2.6 Products

Each product has a name, a description, a main image(render), a material, a collection, a color, a design. It may
have a glass or not. It may have several types of glass. It may have one or several additional images(photo pictures).

## 2.3. "Where to buy" page functionality

### 2.3.1. Cities at "Where to buy" page

When the visitor visits any page of the website, the system offers him to acknowledge his location with the help of
pop-up window. External SaaS gets user IP and defines his default location. If the visitor agrees, the system saves his
location into local storage of the browser if not: the user can choose the location from available choices(cities) where
the shops are located. The visitor can change his location at any time. There is an icon "My city" on the top of the
page. Each city which has a shop of the company should have an url with a Google map, where the shops are located.

### 2.3.3. Shops at "Where to buy" page

In each city where there shops of the company are located should be a list of the shops with their addresses,
phone numbers and working hours. There are 2 types of shops: mono-brand shop(only company's products are sold) and
multi-brand shop where products of other companies can also be sold. The type of shop should be visible in the info
block of the given shop. Each shop has an address, a phone number, a working hours, a type. Each shop has
The remaining working time of each shop should be displayed, it should be updated
every minute. This time is calculated dynamically at the client side according to the time zone of the city the user
chose as his local city. If no shop was chosen by the user, time zone defined by the user's IP is used.
If the user's IP is not defined, the time zone should be taken from the browser.

Route to the shop can be calculated by the user with the help of Google Maps. The user can choose the shop from the list
and click on the button "Calculate route". The route will be calculated and displayed on the map. In case the browser
of the user does not allow to define his location, the system should try to get this permission from the browser. If
the permission is not granted, the system should display a message "Please, allow to define your location to calculate
the route".

## 2.4. Tag system for images

Tags functionality is available on several pages of the website: "Product" page, "Doors in interior", "Our projects"
page.
Each tag has a name. Each tag can be attached to one or more images. Each image can have one or more tags. When the
visitor click to enlarge the image, the system should open the image in a separate modal window and display in this
window all tags attached to this image. The visitor can click on any tag, in this case he will be redirected to the
"Door in interior" page, where all images with this tag will be displayed.
Down below the image there should be a block with all images with this tag in masonry layout. The visitor can click on
any of these images, in this case the system should display the enlarged image with all tags attached to it.
Tags are created and attached to images by administrator of the website.

## 2.5. "Doors in interior" page functionality

### 2.5.1. Initial representation of "Doors in interior" page

When the user initially visits the page "Doors in interior", he can see the page in the mode "Doors in interior", where
he can see the images of doors in interior grouped on the page by default starting tag. Down the page there is a list of
all tags. The user can click on any tag and see the images of doors in interior grouped by this tag. There is also a
search field, where the user can search for images by tag name. On changing the search query, the system should display
below all the tag names, which contain the search query. The user can click on any tag name and see the images of the
given tag. The number of images found should also be displayed. If the user clicks on any image displayed on the page,
the system should display the enlarged image with all tags attached to this image. The user can click on any tag and see
the images of doors in interior grouped by this tag.
As images of doors in interior can be either in landscape or portrait orientation, the system should display them in
masonry layout. The system should display the images in the order they were added to the system.

### 2.5.2. "Doors in interior" page in the mode "Our projects"

The user can switch the page to the mode "Our projects". In this mode the system should display the list of all
projects.
Each project has a name,description, list of images, and a list of tags of the images attached to this project. The user
can click on any project and get to the page of the given project. The system should display the description of the
project and the images of the given project in the order they were added.
As images of doors in interior can be either in landscape or portrait orientation, the system should display them in
masonry layout. The system should display the images in the order they were added to the system.
If the user clicks on any image displayed on the page, the system should display the enlarged image with all tags
attached to this image. The user can click on any tag and see the images of doors in interior grouped by this tag.

## 2.6 "About company" block 

The system should open new modal window with following links:
- "About company" page
- "Promotions" page
- "Designers" page

### 2.6.1. "About company" page

This is a static page.
General information about the company is displayed on the page.
The content should be taken from the current website -https://b-les.com/about/ ,but the visualization should be simplified
 like at https://volhovec.ru/about/ . The is no need to display so much animations, effects, images at this page.

### 2.6.2. "Promotions" page

This is a static page with information about current promotions. 
The content can be displayed the same way as on the page "Promotions" of current website of the company https://b-les.com/akcii/

### 2.6.3. "Designers" page

This is a static page with information 
The content should be taken from the current website - https://b-les.com/dizajneram-i-arhitektoram/ ,but the visualization should be simplified
like at https://volhovec.ru/about/ . The is no need to display so much animations, effects, images at this page.


## 2.7. "Product" page functionality

Product page should display the main image of the product, the name of the product, the description of the product, the
filters that can be applied to the product, the price of the product, which can be changed dynamically, depending on the
filters that were applied to the product. On hover on the price the user should see the description what was included in
the price.
The main image of the product should have the same size as the main images of the product page of the current
website https://b-les.com/doors/interior-doors/kantri-g-1-belye/.
There are 5 types of filters: material, casing, model variants, color and glass.
After the image, filters and description of the product, there should be a block of images of the doors in interior
which
have product's name tag. As these images can have portrait or landscape orientation, the system should display them in
masonry layout. The system should display the images in the order they were added to the system.
The user can click on any image and see the enlarged image with all tags attached to this
image.
The user can click on any tag. In this case he will be redirected to the page "Doors in interior" in the mode "Doors
interior"
Down the product images block there should be a block of 10-12 tags which have the most number of intersections with the
product's name tag. This block is called "People also like with this door". The user can click on any tag. In this case
he will be redirected to the page "Doors in interior" in the mode "Doors in interior".
Any redirection from the product page should open the new tab in the browser. The user should be able to return to the
product page by returning to the previous tab.
The user can also change collection. This will lead to the page of the default product of the given collection.
The user can also change the product in the range of the given collection. This will lead to the page of the product
chosen by the user.

## 2.8. "Other items" functionality

"Other items" block of pages should include the following pages:

- "Door systems" page
- "Door hardware" page
- "Door installation and delivery" page

This pages should be visible in a modal window on hover on the "Other items" block in the navbar of the website.

### 2.8.1. "Door systems" page

The page should display several blocks(types) of doors:

1. Swing doors
2. Sliding doors

The functionality, types, names of door systems of the page is the same as
the https://volhovec.ru/catalog/systems/#block-3 , except that modal window
sliding from the right side of the screen is not needed.

### 2.8.2. "Door hardware" page functionality

The page should represent the door hardware in the same way as the page "catalog" represents doors.
Door hardware should be divided into several types:

1. Door handles
2. Door hinges

The page should have the following filters:

1. Hardware type
2. Color
3. Collection
4. Design
5. Price range

At the top of the page there should be a block with the most popular filter sets. The user can click on any filter set
and the system should apply this filter set to the page.

There are two types of door hardware, up to 20 colors, up to 10 collections, 3 design types.
Each type of door hardware can have several colors, several collections, several design types.
Each collection can have several colors, only 1 design type, only 1 type of door hardware.
Each design type can have several collections, several colors, several types of door hardware.
Each color can have several collections, several design types, several types of door hardware.
Each piece of door hardware can have only 1 collection, only 1 design type, only 1 type of hardware, several colors.

Each piece of door hardware displayed on the page should have the following information:

1. Name
2. Image
3. Price
4. Collection
5. Color

The user can click on any piece of door hardware and see the enlarged image with all tags attached to this image. The
user can click on any tag, thus he will be redirected to the page "Doors in interior" in the mode "Doors in interior".
This should open in a new tab in the browser. The user should be able to return to the page "Door hardware" by
returning to the previous tab.

### 2.8.3. "Door installation and delivery" page functionality

This is a static page. The page should display the information about the installation and delivery of doors.
The content should be taken from the current website of the company - https://b-les.com/ustanovka-i-zamer/

## 2.9 Types of users

In the MVP version of the website there will be 1 type of users: visitor.
In the future versions of the website we will add one more type of users: interior designers.

# 3. Technology stack

For project development we use:

* Backend:
  - Python 3.11
  - Django Rest Framework 3.14
  - PostgreSQL 13.3
* Frontend:
  - React
  - TypeScript

Payment system integration will be not implemented in MVP version of the project but will be implemented in the future.

File and images will be stored in S3-compatible storage.

# 4. Design requirements

High accessibility. White(or light) background.
2-3 types of fonts. Black, grey, white colors.

# 5. Localization

In the MVP version of the project we will implement only Russian localization. In the future we will add English
localization.

# 6. Prototypes

The following Figma files can be used as a rough prototypes for the design of the website, they help to understand the 
functionality of the website but they do not represent design of the website:

https://www.figma.com/file/ayok9hMQ2BAfLT87IXsSfr/Untitled?node-id=1%3A3&t=D9UD72dNjzsYcYsW-1

https://www.figma.com/file/qfrXwZMWr4yy6kqk0iC0UC/b-les-(Copy)?node-id=0%3A1&t=HJwn2l7HvopRbCjs-1


