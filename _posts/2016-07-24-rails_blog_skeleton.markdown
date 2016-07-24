---
layout: post
title:  "Rails Blog Skeleton"
date:   2016-07-24 21:38:18 +0000
---


I know that in the long run I wanted to create a portfolio site to show off all of my work that I have done with my bootcamp. But I have been waiting to really get the thing set up because I wanted to build it from scratch. I in no way wanted to use wordpress. After all this is supposed to be a portfolio and what better way to show off my skills than build it myself?

Also a friend of mine are trying to start a web design company so I decided that a blog skeleton would be the way to go! I created a simple outline of a blog with some tests, devise for my authentication as well and pundit for my authorization. And so far I am very happy with how the functionality of it all turned out.

I was most excited about this project because I wanted to start writing rspec tests. I mean I look at them every single day with our lessons and labs, and I figured that this was something that I needed to start writing. I asked Avi for some recomendations on resources to start writing tests and he recommended this excellent book. [Everyday Rails Testing with RSpec](https://leanpub.com/everydayrailsrspec). I am very happy that he told me about this wonderful resource! If you are looking for a good way to start writing tests, this is the way to go! I am not finished with the book yet but I know as I go along I will be adding more tests to this projects as I expand functionality, and this book will walk me through how to test it.

The other thing that I wanted to do differently was get rid of erb. I am sorry but it really is just ruby flavored php and I knew through my internship that there were much, much better options. I decided to use [Slim](http://slim-lang.com/) as my templating language of choice. 

```
<html> 
   <head> 
     <title>Enter Your Code Here</title> 
   <%= foo = [1,2,3] %>
   <body> 
     <%= foo.each do |bar| %> 
     <p>Or click Convert to test it out!</p> 
   </body> 
   </head> 
 </html>
```

vs.

```
doctype html
html
  head
    meta content=("text/html; charset=UTF-8") http-equiv="Content-Type" /
    title Enter Your Code Here
    = foo = [1,2,3]
  body
    = foo.each do |bar|
      p Or click Convert to test it out!

```

Much, much, much better! It has taken some getting used to, but it is so much prettier and easier to write. I know that erb does a good job and I am familiar with it but I just am not a fan of php and I think that writing a lot less code is a good thing. The other upside to using one of these preprocessors is that it forces you to write extremely clean html. You dont have a choice because if it isn't written right within slim, then your output will look wrong or just simply wont work.

Here is the link to my [Githup Repo](https://github.com/theRingleman/rails_blog_project) if you would like to check out the code. Just clone it, run bundle install, and rails s and you will be up and running! 

Thanks for reading!

