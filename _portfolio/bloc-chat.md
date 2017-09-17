---
layout: post
title: Bloc Chat
thumbnail-path: "img/chat/com.png"
short-description: Bloc Chat is a simple Chat room which doesn't require registration to start chatting.

---

{:.center}
![]({{ site.baseurl }}/img/chat/com.png)

                        Bloc Chat Case Study

 Bloc Chat is a chat room app, so it requires the use of a firebase database to store users and messages.Users can create rooms and send messages. This is my second angular project and my first time using firebase.

----

 The first challenge was to create list of available chat rooms. It was solved by creating a Room factory in Angular that defines all Room-related API queries, next controller was created and Room service was injected and then using ng-repeat I was able to display chatrooms.  You will notice a list of chatrooms on the left hand margin of the screen, and the rest of the screen reserved for displaying the active room as well as message interactions.



---
{:.center}
![]({{ site.baseurl }}/img/chat/room2.png)

 Next challenge to allow visiting users to create room, which led to creation of an ‘Add Room’ button. which when clicked launches a Modal, where user can create room. using UI Bootstrap's service made it possible to create modal and with the help of $add() method on the $firebase array I was able to create rooms.

```
this.open = function() {
var modalInstance = $uibModal.open({
templateUrl: '/templates/modal.html',
controller: 'ModalInstanceCtrl as modalInstance'

});

modalInstance.result.then(function(room) {

Room.add(room);
console.log(Room.all);
});
```


 ---
 {:.center}
 ![]({{ site.baseurl }}/img/chat/blocChattab.png)

 Another dilemma that arose was ensuring that all messages retrieved from the database were shown in their own specific chat room.This was achieved through first creating active room and linking them to specific roomId, than creating a message factory service.



---
{:.center}
![]({{ site.baseurl }}/img/chat/user.png)
 The next challenge was to create user since with out user recipient of message won't know who the message are from, which led to creation of another modal which will be displayed right as application starts and unless user add their name they won't be able to access chatroom.


 ```
 (function() {
   function BlocChatCookies($cookies, $uibModal) {
     var currentUser = $cookies.get('blocChatCurrentUser');
     console.log(currentUser);
     if (!currentUser || currentUser === '') {
       $uibModal.open({

         templateUrl: '/templates/user.html',
         controller: 'UserInstanceCtrl as user'
       });

     }
   }
   angular
     .module('blocChat')
     .run(['$cookies', '$uibModal', BlocChatCookies]);
 })();
 ```




---


This was my second project with angular and I am starting to feel a little familiar with it, learning firebase database was also a good learning experience. I’m hoping it will be a gateway to learning more server side development skills, but for now, I’ll definitely be giving it another shot in the future. This app is far from finished, there is room for more functionality like registering user and showing conversations between two users, adding user profiles but due to time constraint I didn't had time to do that but I'm hoping in the future when I have more time I will be able to improve it more.


For questions or comments, please visit the [contact](/contact/) page
