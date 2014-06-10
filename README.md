rails-rest
==========

A Gem for creating more RESTful resources in rails

What's really RESTful?
----------------------

Unfortunately, there is no RFC document or other standardization for RESTful Interfaces. Yet, there are some common agreements on the methods and URL-schemes a RESTful Interface should provide. I am far from postulating the holy grail of REST, but I really like the following scheme, which is in broad use:

| URI                                          |  Method | Description                                   |
|----------------------------------------------|---------|-----------------------------------------------|
| http://example.com/resources                 |  GET    | List details of collection members            |
|                                              |  POST   | Add a new item to the collection              |
|                                              |  PUT    | Replace an entire collection with another one |
|                                              |  PATCH  | - not usually used -                          |
|                                              |  DELETE | Delete the entire collection                  |
| http://example.com/resources/ID              |  GET    | Get details of the item                       |
|                                              |  POST   | - usually not used -                          |
|                                              |  PUT    | replace the entire item                       |
|                                              |  PATCH  | update item partially                         |
|                                              |  DELETE | delete the item                               |

It has to be noted, that there are only two distinct URIs in use - one for referencing a particular item and one for referencing a complete collection of items. Yet all actions on that URIs are fully an unambiguously declared by the HTTP Method (== Verb) that is used for the request. 

What does Rails 4 today?
------------------------

The default behaviour of Rails 4, respectively ActionDispatch::Route, is to create the following routes for a default resource:

| URI                                          |  Method | Controller-Method-Mapping                     |
|----------------------------------------------|---------|-----------------------------------------------|
| http://example.com/resources                 |  GET    | #index                                        |
|                                              |  POST   | #create                                       |
|                                              |  PUT    | -                                             |
|                                              |  PATCH  | -                                             |
|                                              |  DELETE | -                                             |
| http://example.com/resources/ID              |  GET    | #show                                         |
|                                              |  POST   | -                                             |
|                                              |  PUT    | #update                                       |
|                                              |  PATCH  | #update                                       |
|                                              |  DELETE | #destroy                                      |

I am omitting the #new and #edit routes here, because they do not belong to the API-interface, but only to the web-interface part of rails.

What does rails-rest for you?
------------------------------

| URI                                          |  Method | Controller-Method-Mapping                     |
|----------------------------------------------|---------|-----------------------------------------------|
| http://example.com/resources                 |  GET    | #index                                        |
|                                              |  POST   | #create                                       |
|                                              |  PUT    | #replace_collection                           |
|                                              |  PATCH  | -                                             |
|                                              |  DELETE | #destroy_collection                           |
| http://example.com/resources/ID              |  GET    | #show                                         |
|                                              |  POST   | -                                             |
|                                              |  PUT    | #replace                                      |
|                                              |  PATCH  | #update                                       |
|                                              |  DELETE | #destroy                                      |

Installation & Usage Instructions
---------------------------------
