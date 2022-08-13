---
title: Introduction Job Board CRUD app
published: false
description: 
tags: 
# cover_image: https://direct_url_to_image.jpg
# Use a ratio of 100:42 for best results.
---

### Job Board Project
1. [Introduction Job Board CRUD app](#example)
2. [Job Board - Express Setup and UI](#example2)
3. [Handlebars in Express](#third-example)
4. [Working with forms](#fourth-example)


## 1. Job Board CRUD app

### Requirements

1.  Knowledge of HTML, CSS and JavaScript required
2.  Android device with Termux and Acode Installed
3.  Nodejs installed Termux

### Introduction

As we have evolved as a species one way or the other we have become dependent on software. My laptop failed as passion pursued I had to use my mobile phone as a Dev machine, the thing is real estate is smaller and without a budget to get a laptop as yet, business had to go on with my [hisense u963 phone](https://www.gsmchoice.com/en/catalogue/hisense/u963/). 

I have created a [tutorial](https://dev.to/brixmavu/setup-android-phone-for-web-dev-iae) about installing a terminal emulator [Termux](https://f-droid.org/en/packages/com.termux/) and a text editor [Acode](https://f-droid.org/packages/com.foxdebug.acode/) on an android device for Web Dev.

### Some use cases of developping on your phone or tablet

1. Learn new technology while commumiting to work or school.
2. SSH to your server if not close to your machine
3. A chance to learn coding if unemployed  
4. A chance to change career path
5. Check how users are interacting with your app

### Preparation Job-Board project

You need to have a [GitHub account](https://github.com/) if not create a account.

[Create a new repo on Github](https://docs.github.com/en/get-started/quickstart/create-a-repo) 

After creating our repo on Github, open Termux and create our project with express-generator.

### Express Generator Boilerplate

Install git in termux

`pkg install git`

Run [express-generator](https://expressjs.com/en/starter/generator.html) boilerplate to quick start project in Termux

`$ npx express-generator --git --view=hbs job-board`

- The `--git` add .gitignore file.
- The `--view=hbs` add handlebars templating engine on our project. You can use different template engine check the documentation.
- `job-board` creates our directory

![express-generator](./img/Screenshot_20220726-075716.png)

From terminal  enter job-board folder and install dependency if any error follow given instructions

Before installing any nodejs dependencies push code to github. 

1. Enter project folder

    `cd job-board`
2. Intialise folder for git usage

     `git init`
3. Add all repo contents with . to a que going GitHub

     `git add .`
4. Follow up with these commands
    ```
    git commit -m "first commit"
    git branch -M main
    git remote add origin https://github.com/YOUR-GITHUB-USERNAME//job-board.git
    git push -u origin main
    ```

## 2. Job Board - html and css UI

### Introduction to our webapp

Inside project add nodejs dependencies

`npm i`

### CRUD 

1. Create - post
2. Read - get
3. Update - put/patch
4. Delete - delete

Start server script `npm start`  and check your browser

![First web look](./img/Screenshot_20220726-154716.png)

### Frontend - HTML and CSS

For the purpose of this tutorial we will use Acode Editor.

From your editor open views folder and add viewport meta.

`<meta name="viewport" content="width=device-width, initial-scale=1">`

We going to use sticky footer using CSS grid from [mdn](https://raw.githubusercontent.com/mdn/css-examples/main/css-cookbook/sticky-footer--download.html)

- Copy html between `<body>` tag and go to views folder and paste contents inside index.html file overwrite anything inside file 
-  Copy all css inside `<style>` and go to public/stylesheet folder and paste styles inside style.css file overwrite anything inside file.

Result:

![mdn result](./img/Screenshot_20220726-154716.png)

### Job Board UI

Inside `<header>` tag add two buttons

```html
<button>Add Job</button>
<button>Edit Job</button>
```

Inside `<main>` tag add 

```html
<div class="search">
   <label for="site-search">Search for job:</label>
    <input type="search" id="site-search" name="q">
    <button>search</button>
</div>
                
<div class="job">
   <div class="title">
      <a href="#">Javascript Developer</a>
   </div> 
   <div class="detail">
      <span class="date">
         22July 2022
      </span>
      <span class="location"> 
        Capetown
      </span>
   </div>
 </div>
 ```
 
 Inside `<footer>` tag add software developer jobs
 
 ```html
    <footer class="page-footer">
      Software Developer Jobs
    </footer>
 ```
 In your stylesheet folder edit styles.css by adding the css below

```css
title{
  padding: .5rem ;
}

.job{
  border: 1px blue solid;
  padding: .4rem;
  margin : .5rem;
}
.detail{
  display: flex;
  justify-content: space-between;
  padding: .4rem;
}

label {
    display: block;
}

input,
label {
    margin: .4rem 0;
}

```

Result

![job-board-ui](./img/Screenshot_20220730-063733.png)

