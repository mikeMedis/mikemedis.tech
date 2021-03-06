---
layout: post
title: Open TODO API
thumbnail-path: "img/opentodoapi.png"
short-description: A tracking API TODO list that can authenticate and updated users, lists, and items from the command line.

---

{:.center}
![]({{ site.baseurl }}/img/opentodoapi.png)
A tracking API TODO list that can authenticate and updated users, lists, and items from the command line.

{:.center}
* [See code on Github](https://github.com/mikeMedis/open-to-do-api){:target="_blank"}

## Explanation
Open TODO API is a CLI (command-line interface) application, where users could make lists and items on a todo list from the command line.

## Problem
The amount of time developers and engineers spend working in the terminal, most are looking for time savers at every corner. With users moving text editing to VIM to save time only after tremendous dues are paid learning a new way of interacting with a computer. Engineers and developers alike need a do list that we can use and never have to leave the command line.

## Solution

Using Rails authentication and serializers, this application can be used by using simple ```curl``` request from the terminal and making the life of a developer/engineer much happier and much more efficient. Users were authorized using Serializer methods in the Rails framework.

Authentication of users is by email address and password

``` ruby
class ApiController < ApplicationController

  skip_before_action :verify_authenticity_token

  private

  def authenticated?
    authenticate_or_request_with_http_basic { |email, password| User.where( email: email, password: password).present? }
  end

end
```

## Conclusion

This application had several different parts which made it challenging and fun to work on. I especially enjoyed learning how to interact with data in a very interesting and exciting way(regarding the command line). Having a way to interact with the command line to build my own API makes my development that much more efficient this project was as rewarding as I have ever felt.
