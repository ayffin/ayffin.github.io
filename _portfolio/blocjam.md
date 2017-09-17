---
layout: post
title: Bloc Jams AngularJS
thumbnail-path: "img/blocJams_mac.png"
short-description: Bloc Jams is a digital music player like Spotify.

---


![]({{ site.baseurl }}/img/tv.png)

## Explanation

**Bloc Jams** is an interactive music player similar to Spotify. It's a two part project. In the first part we explored HTML and CSS, including responsive web development. We then studied fundamental programming concepts using JavaScript and jQuery. The second part of the project was taking the Bloc Jams that was already created and refactoring it using AngularJS.

To view this project, visit this link: [github](https://github.com/ayffin/bloc-jams-angular)

---

## Challenges
- Create a responive website and animations that works on all devices.
- refactor my JavaScript and jQuery foundations work into AngularJS

- build Angular templates, controllers, services, directives, and filters
 - creating song rows with different states and allows the user to listen to each track
 - Make a fully functional ‘player bar’ that allows the user to alter the state of the song and is in sync with song rows.
 - Use an api to manipulate sound files
 - creating interactive seekBar.

---

## Solution

{:.center}
![]({{ site.baseurl }}/img/phone1.png)

- Responsive design was achieved through adding media queries in css.
In the first part of project we utilized JavaScript for animation and DOM Scripting for events and functionality. while latter we refactor that by using Jquery animations and events.
![]({{ site.baseurl }}/img/landing.png)

---

- In order to show single page,  we created different templates and to show these templates in the view, we used UI-Router to set our URL routes.
 when the collection page is loaded, the view is populated with albums available to listen to. In the first part we used for-loop to create copies of album while in the angular version we set up our controllers for the three states: Landing, Collection and Album in app.js, and used ng-repeat to populate out album collection.

 ---

{:.center}
![]({{ site.baseurl }}/img/album.png)

- Another challenge we encounter was to show different states  for song rows we had to set the different states for the number/play/pause button. In the first part For our player Bar we created a lot of functions which includes play/pause function also Mouseover and Mouse-leave event listeners function and we set up the click behavior as well.

<script src="https://gist.github.com/anonymous/c6b888e9401206099ceab52b348eb221.js"></script>


while in Angular we did it through AngularJs Build in directive **ng-mouseover**,**ng-mouseleave** and ngClick which were inserted in the html itself which made play logic quite simple as you can see in the code below.
<script src="https://gist.github.com/anonymous/2a8784d697fa66f6c48578934280c52e.js"></script>



 ---

 - For our player bar we created service that handles all our playing and with the help of the **Buzz library**, our songs will functionally play and pause.We created a custom directive for our seekbar and used the logic from our foundational Bloc Jams project to configure our seekbar functionality as well as the thumb on the seekbar using a click event and mousedown/mouseup.

---

## Conclusion
while creating Bloc jams I was able to see the benefits of using Angular.There were plenty of functional involved with vanilla javascript and jQuery but not so many in angular. It makes codes so much cleaner by building Single Page Applications and dividing up logic by Model, View and Controller.
