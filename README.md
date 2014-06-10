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
| http://example.com/resources/<ID>            |  GET    | Get details of the item                       |
|                                              |  POST   | - usually not used -                          |
|                                              |  PUT    | replace the entire item                       |
|                                              |  PATCH  | update item partially                         |
|                                              |  DELETE | delete the item                               |

What does Rails 4 today?
------------------------

What does Rails 4 for you?
--------------------------

Installation & Usage Instructions
---------------------------------
