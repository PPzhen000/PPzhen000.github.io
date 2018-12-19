---
layout: post
title:      "MyPocket with Rails/JS"
date:       2018-12-19 02:48:10 +0000
permalink:  mypocket_with_rails_js
---

This is a difficult project, however, I gained a good understanding of jquery and AJAX after finishing the project. I want to share a little getting-stuck moment I encounted while getting started on the project. 

In order to add JS to the the pre-existed rails project, the first step is of course to add  the jquery-rails gem to your Gemfile:

`gem 'jquery-rails'` 

run `bundle install`

But wait, before you run `bundle install` you may want to consider adding another gem that you will need for this project `gem 'active_model_serializers' ` and also getting rid of `gem 'turbolinks', '~> 5'`. 
According to this [documentation](https://github.com/turbolinks/turbolinks-classic#turbolinks ), 
>turbolinks makes certain links in your web application faster. Instead of letting the browser recompile the JavaScript and CSS between each page change, it keeps the current page instance alive and replaces only the body (or parts of) and the title in the head. 

As rails uses turbolinks and $(document).ready function() doesn't really work with Turbolinks.

So I got rid of the turbolinks gem and in my gem file and changed this two lines of code in the application.html.erb file, from:

```
<%= stylesheet_link_tag    'application', media: 'all', 'data-turbolinks-track': 'reload' %>
<%= javascript_include_tag 'application', 'data-turbolinks-track': 'reload' %>
```

to: 

```
<%= stylesheet_link_tag    'application', media: 'all'%>
<%= javascript_include_tag 'application'%>
``` 

And also, in  the app > assets > javascript > application.js file 

delete `//= require turbolinks `


There's another way around it already, a solution of this issue in this [railscast ](http://railscasts.com/episodes/390-turbolinks)

I didn't try that out though as I just used the first soluction I came accross. 



