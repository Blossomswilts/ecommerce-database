# Employee Database
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

## Description
Using node.js, sequelize, and mysql2, this application allows the user to create, read, delete and update various products, categories tags and more. This application is useful for anyone who wants to keep track of their inventory, and be able to update it as needed. This is viewed through insomnia for the purpose of this assignment, but can be used in any application that can connect to a database.

## Table of Contents
* [Installation](#installation)
* [Usage](#usage)
* [Contribution](#contribution)
* [Screenshots](#screenshots)
* [Code Block](#codeblock)
* [License](#license)
* [Questions](#questions)


## Installation
To have this application on your own system, `git clone` the repository and set it up in your local system. Ex (Vs Code).
You will need to run `npm install` which will install the necessary package dependencies;
* Once all the dependencies are installed, you will need to run the schema.sql file in mysql to create the database. 
* You will also need to run the seed.sql file in mysql to populate the database with some data as a starting point.

## Usage
In order to run the program, after obtaining all of the dependencies you will need to run;
* run schema through mysql to create the database.
* `npm run seed` : this will populate the database with the data from the seed.sql file.
* `npm start` : this will begin the program in your terminal, in which you will be able to navigate through the prompts to create, read, update, and delete from the E-COMMERCE database.
* Application link to github repository: [E-Commerce DB](https://github.com/Blossomswilts/ecommerce-database)

## Contribution
If you would like to contribute to this project, and improve it in your own way(s), please do the following:
- `Fork` the repository on GitHub
- `Clone` the project onto your own machine (such as VsCode)
- `Commit` your changes to a branch you have created
- `Push` your changes back up through your fork
- Submit a `pull request` so that my team and I can review your changes.

As a side note, when making changes, always merge or pull from the latest version to ensure you are working on the most up to date version of the application. 

## Screenshots
This is the program interface using Insomnia to view the database where you can CREATE, READ, UPDATE, and DELETE from the database.

![insomnia scs](https://github.com/Blossomswilts/ecommerce-database/assets/117021869/0cf52a97-e104-49c3-bf30-05446bc5ddde)



Video Walk-Through: [E-Commerce Backend](https://drive.google.com/file/d/1HCPji53Wouz112UCKCHJIAUxt6owgwZO/view)

## CodeBlock
This is an optional asynchronous try catch block that could be used to replace the .then and .catch blocks in the routes. 
```javascript
//ORIGINAL CODE:
router.post("/", (req, res) => {
  Category.create({
    category_name: req.body.category_name,
  })
    .then((dbCategoryData) => res.json(dbCategoryData))
    .catch((err) => {
      console.log(err);
      res.status(400).json({ message: "No category found!" });
    });
});

//TRY CATCH VERSION:
router.post("/", async (req, res) => {
  try {
    const dbCategoryData = await Category.create({
      category_name: req.body.category_name,
    });
    res.json(dbCategoryData);
  } catch (err) {
    console.log(err);
    res.status(400).json({ message: "No category found!"});
  }
});
```

## License
[MIT](https://choosealicense.com/licenses/mit/)

## Questions
If you have any questions, or would like to show off some of your work, don't hesitate to message me through any of the following contacts!

GitHub: [Blossomswilts](https://github.com/Blossomswilts)
(ctrl+click to follow link, where you can see this user's repositories and profile)
    

Email: michael.r.tranquillo@gmail.com
(ctrl+click to send email to this address with your default email client or copy and paste address into your email client)