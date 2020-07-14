
In this module, we'll explore how Internet works, learn the basics of HTML and CSS, and setup your own website on WordPress.

**Table of Contents:**

[TOC]

## What even is the Internet? 

The Internet is magic! Just kidding, it's really not. The Internet is made up of computers connected to other computers. Even though you often connect to the internet wirelessly, the internet is still a very physical thing. The information you send and receive travels through wires and fiber-optic cables in the ground and under the ocean. These networked computers talk to each other using protocols. Every computer has an address, known as an IP \(Internet Protocol\) address, to help direct traffic.

Another protocol that you use, even if you don't realize it, is the Hypertext Transfer Protocol, or HTTP. Your browser uses HTTP to render websites. When you type in `http://www.wlu.edu` your browser sends out a request to the computer that can serve up all the files at that particular address. The "server" returns the files and your browser renders them into a website. At its simplest, a website is just a folder full of text files and images.

Here are a few videos that might help:

* [What is the Internet? ](https://www.youtube.com/watch?v=Dxcc6ycZ73M)
* [The Internet: Wires, Cables, and Wi-fi](https://www.youtube.com/watch?v=ZhEf7e4kopM)


## HTML
HTML, or Hypertext Markup Language, is one of the basic building blocks of the web. HTML is a set of tags that add structure to documents.

When you write a document, you rely on style to indicate something about the text. You might put the title in a bigger font or break up paragraphs with tabs or new lines. Markup languages do this by adding tags around the content you wish to set apart. For example: `<title>The Lord of the Rings</title>` or `<p>This is a whole paragraph.</p>` Your human eyes and brain can infer things based on visual appear that computers need to be told explicitly. That's why we need semantic markup.

You can see the HTML for a basic website at the [W3 Schools HTML tutorial](http://www.w3schools.com/html/).

In fact, you can see the HTML for any page on the web by right clicking anywhere on the page and selecting "view page source."

HTML documents are just plain text documents. You can write and read HTML in a text editor like Notepad++ or Sublime. The magic happens when you open an HTML document in the browser.

## CSS
Our next building block of the web is CSS, or Cascading Style Sheets. HTML structures your webpage, but you need something else to add the pretty colors and images.

CSS has a different syntax than HTML. First you identify the HTML tag, then you declare the styles you wish to apply. `title {color: red;}`

See some basic CSS at the [W3 Schools CSS tutorial](http://www.w3schools.com/css/default.asp).

The beauty of CSS is that you can keep all your styles in one stylesheet which you link to all your HTML pages.



## Your domain 



## Activities 

### Activity 1: Install WordPress

1. Login to the Cpanel for your domain by adding `/cpanel` to the end of your URL. Use the username and password sent to you by Reclaim Hosting/Jason Mickel. 
2. You should see a Wordpress icon near the top of the page. Click on it to begin installing Wordpress.
3. Find the "install this application" button. 
4. Work through the installation. You can leave the default settings except for the following:  
   * Directory  - since you might want to use this domain for other things, let's put course materials in a subdirectory, such as ``http://www.mackenziekbrooks.info/dci102``. 
   * Change the administrator username and password to something you are likely to remember.
   * Customize the website title and tagline.

5. Press install to finish up.

6. You should now be able to access your wordpress admin interface by appending `/wp-admin`to your selected URL.

7. Add your website address to the class Box folder `DCI102-F19-data > Website Registry.boxnote`

### Activity 2: Customize WordPress

1. Change your theme by going to `Appearance > Themes`. Select an installed theme, or find a new one with the `Add New` button. Activate multiple themes to try them out!
2. Check your comment settings in `Settings > Discussion` to make sure your classmates will be able to comment on your posts. 
3. Set up your menu (remember we'll have 3 units with similar assignments) by going to `Appearance > Menus`. You will need to create a menu, add pages to it, and select a location for that menu. This is usually the most confusing part of Wordpress! 
4. Before you start adding content to your site, play around with as many of the settings and features as possible. What do all the bells and whistles do? Add your own images or colors. This is *your* site!

### Activity 3: HTML

* Open your favorite text editor and using the [W3 Schools](http://w3schools.com/) as a guide, write your own HTML document.
* Save the file as `index.html` in your Box folder. I'm not grading this, but it will help me troubleshoot if necessary.
* To view your page in the browswer, open `index.html` in your browser, usually with the key commands `Ctrl + o`
* You should include the basic set of tags: `<html> <head> <title> <body>`
* Add seven additional types of tags to the body of your HTML document, including a table, link, and image.
* Add an additional HTML page and link the two pages.

### Activity 4: CSS

Create a separate CSS document and save it as `style.css` in the same folder you created for Activity 1.

* Link the `style.css` file to your HTML document. Consult the [W3 Schools](http://w3schools.com/) to figure out how to do this.
* Add a background color.
* Change the border on your table. 
* Add style to your links when you hover over them. 

### Activity 5: Make it live

When you opened your HTML files in your browser, you were viewing your files locally. Only you could see them on your computer. Now it's time to upload them to your domain so other people can view them.

* Navigate to `http://yourdomain.wludci.info/cpanel` and login. 
* In CPanel, open up the File Manager.
* Navigate to the `public_html` folder. 
* Create a new folder titled `activities` or something similar. 
* Upload all your HTML and CSS files. 
* Navigate to your equivalent of `www.yourdomain.com/activities`. What do you see?  
* Add a link to this URL to our shared Box folder in the website registry. 

### Activity 6

* First, share with your partner one realization you had while learning HTML/CSS. It can be technical like "don't forget that slash" or conceptual "I realized I need to read directions more closely."
* Second, visit each other's new website. Right click/Ctrl + Click to ```view page source```. 
* Proof your partner's code. Check their syntax. 
* Work together to add the following to each of your websites: 
	* an ```iframe``` that embeds another website
	* two ```div``` tags with different background colors (hint, you'll need to use a class or id)
* Be sure to upload your changes to your website. 


## Readings

## Resources 
