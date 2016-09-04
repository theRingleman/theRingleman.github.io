---
layout: post
title:  "My final project, and final learn blog post..."
date:   2016-09-04 04:20:46 +0000
---


Honestly, writing this is a little bittersweet. I have been telling my wife all day today that I am not going to know what to do with myself when I graduate. I guess go into the big bad world and try and find a big boy job. I am excited and nervous and sad all at the same time. I know that all my hard work is going to now pay off, but I have to say that even though I haven't been all that involved in the community, (thanks to my buddy learning to code with me locally) I am really going to miss it. 

Ok onto code talk, enough blubbering :)

## Code Pouch
Is the name of my final project. I wanted to create something similar to a bookmarking system. Only I wanted it to be searchable and easily categorized. As I have learned to code, I have collected a ton, and I mean a ton, of bookmarks. All on things that I know would be helpful someday, because let's face it, I can't remember everything. So in comes Code Pouch. I thought this would be a perfect way for me to maintain my coding resources. I also figured that if I let it onto the world, then other awesome people learning to code, or even crazy experienced coders could add to the app and let others benefit from their resources. Just ask Avi for some help with writing RSPEC and he will give you more books and articles than you could read in a month! Imagine awesome guys like him adding to the app. Everyone will benefit, all they have to do is search for RSPEC and every resource will pop right up!

## Custom API
This was intimidating to me. I was unsure how to go about adding Angular to Rails, let alone do all the ajax calls. In fact it took me most of one day to just get my angular templates rendering... Thanks to [this](https://github.com/pitr/angular-rails-templates) awesome repo, it finally made my life a little bit easier, and I was able to get them rendering. But I used ActiveModel::Serializer to serialize my models and serve them to the front end via JSON. That was exciting seeing that data being displayed, I know that Serializer makes it easy, but you have to enjoy the small successes in code, otherwise you will pull your hair out until you finish your project. Let's face it here, you will never completely finish your project, there is always something to do, so you will go bald before you finish your project :)

## Angular Resource
This little bit of code makes life easier! If you want an absolutely amazing walkthrough on how to use this guy go [here](https://www.sitepoint.com/creating-crud-app-minutes-angulars-resource/). The person who wrote this really knows how to make a wonderful tutorial and helped all the way through my app. ngResource handles all of the basic crud ajax calls, and if you follow that guide, it will keep your services down to a minimum. Just be aware that you have to manually include the file, it is not served up with just straight Angular.

## Future Plans
For my app I am going to be implementing a lot more features in the very near future. I want to include the disqus platform for comments. I really like the platform and it makes life easy! I am also going to add user authentication to it. Plus a ton of styling of course. I will get help on this because I am in no way a designer! But if you want to check out my project please go [here](https://www.github.com/theRingleman/code_pouch). Feel free to fork it and make any changes. All pull requests are welcome and greatly looked forward to!

Thanks again for reading, and thanks to Learn for turning me into a developer. I couldnl't be more thankful to this platform and everyone in it!
