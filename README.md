ShoppingWebsite
======

You are here!! It means you might have visited **Game I Play and Shop**, if you didn't, check it out here [Game I Play and Shop](https://aditya2104.github.io/ShoppingWebsite/). 
- This repository is a submodule of UiPath Bot and it is a private repository.

Problem statment
=====
Amazon Affiliate/Influncer/Content-Creator (called as "user") curates products on Amazon and shares the details to their audience through a website. Curated products and their links neeed to be avalable to the audience as soon as possible to not loose any revenue. 

### Constrains 
1. User don't know HTML or any automation tech :worried:
2. Curated products neeed to be avalable online as soon as possible 

Solution 
=======
The website has two coponents 
1. Backend - Building HTML - Building HTML index.html using UiPath Bot.
2. Frontend - Website index.html and its dependencies deployment - Deployment using GitHub Actions.

### Out of Scope
- CSS styling is out of scope for this use case. This needs to be handled manually if there is a major change to DOM structure.
- Creation of custom link for the curated products - User needs to create custom link with affiliate Id and update the excel.

### Details
#### Backend - Building HTML - Building HTML index.html using UiPath Bot. 
- User updates an excle with information of the product identified, information includes:- (for now only below details are captured)
  - Product ID 
  - Product Name
  - Product Link
  - Product Image saved in a specific foler and file name captured in the excel
- HTML templates are developed to handle the dynamic and the static parts of HTML body. 
- UiPath Bot reads the excel
  - Bot generates the ```<div>``` part of the product links dymamically with last row of the excel as the first product link using the HTML templates.
  - Places the image path in the ```<img>``` part of the html.
  - Finally appends the closing tags of at the end of index.html ```</html>``` and ```</body>```.
- CSS styling of the web page is static. This is out of scope of UiPath Bot. Also this doesn't need to be updated everytime UiPath bot executes unless there is a major change in DOM. Changes to CSS need to be handled manually. 
- Product images are placed in "imgs" folder within the working folder by the user when updating the excel with curated product details.
#### Frontend - website index.html and its dependencies deployment - Deployment using GitHub Actions
- When the UiPath Bot complets the execution, it places the updated index.html in this repository locally. 
- The user pushes the changes to this repo using GitHub Desktop.
- As soon as there is merge on the main branch GitHub Actions kick in and deploy the new website. 
