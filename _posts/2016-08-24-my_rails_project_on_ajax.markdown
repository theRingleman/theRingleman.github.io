---
layout: post
title:  "My rails project... on AJAX :)"
date:   2016-08-24 00:00:44 +0000
---


So, this was a lot of fun, like a ton of fun for me. There were so many aha moments on this assessment that it seemed a little unreal to me. 

During the rails assessment I had a lot of issues with nested forms and creating new objects using nested forms. I definitely got a better grasp on that since last time, and in fact I completely refactored my code, added validations, and even routed the creating post using AJAX. It was a lot of fun!

## The best thing that I learned!
Would most definitely have to be how to properly use the javascript debugger! Did you know that the debugger acted like pry? I didn't, I didn't have a clue, and in fact, I was looking for something similar to pry since I started the Javascript section. What amazed me was the simple fact that once the debugger code runs, all you have to do is switch over to your console, and there is your code, all of your variables and data right at your fingertips. This made such a huge difference to me in terms of formating my return values, that it no longer felt like hacking away at my code. I was able to see what the AJAX, or really any data that was in my functions, that it was then easily used to finish off my code. Talk about a life saver, thank you Avi for showing that in your AJAX lectures, you really did make my life a whole lot easier.

## The wonderful world of rails.
ActiveModel::Serializer has to be one of the handiest tools that I have seen in a long time. It really takes the stress out of serializing your models. I was amazed to see how rails can generate api endpoints, and it made me wonder how many websites have internal api's? Does Wordpress utilize that kind of thing in their cms? (I know we dont talk about wordpress...) But really the possibiiities of user experience because of AJAX really is amazing. It is funny now, because anytime I go to a website, I look at how things are loaded, and go, "Hey, I can do that!". But I really do love how rails can render JSON objects just by simply stating in the controller `render json: @whatever`, and if you have your serializer set up right, there is nothing more that needs done. This can obviously be a whole other post of its own, but I am just excited by what I have learned.

## Open Source JuJu
This was a lot of fun for me because I got to actually contribute for the first time to an open source project. There were some links in the lesson repo, and they led to Learn's Github repo where there was supposed to be a video embedded for us to watch. It turns out that Github doesn't render iframe's while you are on your repo home page. So I opened an issue with on the repo and our lesson got updated. How cool! I know that this issue is minor, but it really got me thinking about the impact people could have if they weren't afraid to let developers know how their code is broken. From here on out every student that goes through the full stack track, has access to these helpful videos and wont have to try and struggle through eveything. It really is amazing how simple something like that is to overlook, and how much of a difference it can make for the next person.

## Conclusion
This is all that I have to say for right now, but if you would like to check out my [repo](http://www.github.com/theRingleman/rails_blog_project) and see my blog skeloton, please feel free! Thanks for reading!
