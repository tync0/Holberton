**HTML**
The body tag of all of your webpages (including index.html and tweets.html) must contain exactly three direct sub-tags in that order: header, main and footer.
The header tag must contain an unordered list (the ul and li tags) of links (the a tag) to each of your webpages. As you may have understood, this will serve as a navigation for your website.
The footer tag must contain one paragraph with the sentence Made by Tuncay Isgəndərli for a href="https://apply.holbertonschool.com" target="_blank"Holberton School/a.
The main tag must contain two direct sub-tags in that order: article and aside.
article contains the content of your webpage: texts, links, images, tweets, … This is the part of index.html and tweets.html that you have already written, and you must now write it as you like for the other pages.
aside contains a single paragraph, just reading for now "placeholder to add comment thread later".

**CSS**
Both container tags, body and main must be told that they are containers to flexible boxes: you need to apply the display: flex property to both of them.
However, body contains a column of three boxes (header, main and footer), therefore you must apply the flex-direction: column property to body; whereas main contains a row of 2 boxes (article and aside), so you must apply the flex-direction: row property to main.
Ensure the main tag keeps an automatic height and width, by applying the flex: auto property to it.
To wrap up the layout, you want to be sure that your content (article) takes ⅔ of the width of the page, and your aside takes ⅓; you can assign to them the number of boxes they should fill in. This is done by applying the property flex: 2 to article (using up 2 boxes), and flex: 1 to aside (using up 1 box).
Finally, you want to be sure that the user can scroll within your article and your aside. You can do this by applying the overflow-y: auto CSS property to both of them.

**JS**
Before anything, start by copy-pasting this into your behavior.js file:

document.addEventListener("DOMContentLoaded", function(event) {

});
For this part of the project, all of your JavaScript code must be written between those two lines. Any code outside of these two lines would execute before the HTML page finished loading, so the result could be very random!

To test that your file is properly taken into account by your webpage, write alert('Hello!'); between the two lines in behavior.js. Refresh the webpage; a dialog box should greet you! Think about removing this line before carrying on, so that your users don't get greeted at each refresh!

Setting up your live JavaScript console in the browser
Every modern browser has a JavaScript console, which allows you to execute pieces of JavaScript code live as your webpage is up. Search online where yours is in your browser (for some browsers, it may require to change your settings first).

Once you've found it, type alert('Hello!'); in it. The dialogue box should show up. Make sure the console remains open for the rest of the project, as the JavaScript console will also tell you if there are code errors in your .js file.

Inserting a large image in the document
Well, you know how to do that! Find a large image online (at least 800 pixels wide), and use its URL to insert it inside your document, wherever you want. You will notice that even if it is wider than your website, it won't overflow, and will resize nicely, because we set a CSS rule for you, to constrain its size.

Then, we want this image to be small at first; and for this too, we already set a CSS rule for you. Simply add this attribute to your img tag: class="small" in your HTML code. Refresh, and you see it's much smaller.

The whole point of this part of the project, is that you will use JavaScript to remove this "small" class (and therefore the image will grow) or putting it back (therefore it will get back to being small) when the user clicks.

Isolating the HTML element inside a variable
This challenge is all about "listening" to the event "user clicked on this image", and then changing the image's size when it happens; therefore, the first thing to do is to is to capture this image HTML element in a JavaScript variable that we'll be able to manipulate.

The smartest way to capture one particular HTML element with JavaScript is to give it a unique ID (it's like giving it a first name!), and catch it by giving JavaScript this ID. It's easy to do, you can simply add the attribute id="smart_thumbnail" to your img tag, and there it is, now identifiable!

Then, after refreshing your page, you can run this in your browser's JavaScript console, and you'll see that it indeed returns an element, which is your img element:

document.getElementById("smart_thumbnail");
You can copy-paste this line into your behavior.js file; but you also have to capture the result in a variable called thumbnailElement, so that we can manipulate it more easily later in our JavaScript code. All together, it will look like this:

var thumbnailElement = document.getElementById("smart_thumbnail");
Catching the click event
Add these lines next in your JavaScript file:

thumbnailElement.addEventListener("click", function() {
  // write here
});
We did mention before that you could get code to execute on user events; well, code that you write instead of // write here will execute whenever the user clicks on your image.

As code that happens when the user clicks on the image, write alert("I saw you click!");. Refresh the webpage, then scroll down in your content, and see the dialog box pop up each time you click!

That's great because it means you're catching the click event properly! But a dialog box is not what we want to do, so you should remove your alert statement before carrying on. But note that the rest of your code in this part of the project will be executed when the click is captured, and therefore you will all have to write it there.

Make the image big!
To make the image bigger or smaller, you have to change its class. In your JavaScript console, run this code:

var thumbnailElement = document.getElementById("smart_thumbnail");
thumbnailElement.className;
This displays what the class currently is; it should be "small", unless you changed it since.

To make it big, you should remove the class, by running this:

thumbnailElement.className = "";
To make it small again, you can put it back:

thumbnailElement.className = "small";
See how it changes from small to big? You should put the line that makes it big in your JavaScript file so that it executes when the user clicks.

One more thing…
After clicking on the image, now that your image is big, your user can… well, do nothing more! Wouldn't it be cool if the image went back to being small when she clicks again?

This will be an extra challenge for you, if you have some time left after the project!

To make it work, you will need to execute some code if the image is big or else some other code if not. To that end, you can use what are called an if statement and an else statement, about which you can learn more here. The if statement to check if the image is big should look like this (pay attention to the double-equal sign):

if (thumbnailElement.className == "") {
	// write here the code that will execute if the image is big
}
Once you like what you have, feel free to move on to the next part of the project.