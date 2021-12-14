Django has emerged as a big favorite by a wide margin. Djangosites.org lists over 5,263 sites written in Django,
including famous success stories such as Instagram, Pinterest, and Disqus.


As the official description says, Django (https://djangoproject.com) is a high-level Python web framework that encourages rapid development and clean, pragmatic design.
In other words, it is a complete web framework with batteries included just like Python.

THE STORY OF DJANGO:
In the fall of 2003, two programmers, Adrian Holovaty and Simon Willison, working at the Lawrence Journal-World newspaper, were working on creating several local news websites in Kansas. These sites, including LJWorld.com, Lawrence.com, and KUsports.com, like most news sites were not just content-driven portals chock-full of text, photos, and videos, but they also constantly tried to serve the needs of the local Lawrence community with applications, such as a local business directory, events calendar, and classifieds.

HOW DJANGO WORKS: 

Ref: https://learning.oreilly.com/library/view/django-design-patterns/9781788831345/

To truly appreciate Django, you will need to peek under the hood and see the various moving parts inside. This can be both enlightening and overwhelming. If you are already familiar with the following information, you might want to skip this section:

The preceding diagram shows the simplified journey of a web request from a visitor's browser to your Django application and back. The numbered paths are as follows:

1. The browser sends the request (essentially, a string of bytes) to your web server.
2. Your web server (say, Nginx) hands over the request to a Web Server Gateway Interface (WSGI) server (say, uWSGI) or directly serves a file (say, a CSS file) from the filesystem.
3. Unlike a web server, WSGI servers can run Python applications. The request populates a Python dictionary called environ and, optionally, passes through several layers of middleware, ultimately reaching your Django application.
4. URLconf (URL configuration) module contained in the urls.py of your project selects a view to handle the request based on the requested URL. The request has turned into HttpRequest, a Python object.
5. The selected view typically does one or more of the following things:
    a. Talks to a database via the models

    b. Renders HTML or any other formatted response using templates

    c. Returns a plain text response (not shown)

    d. Raises an exception

6. The HttpResponse object gets rendered into a string, as it leaves the Django application.
7. A beautifully rendered web page is seen in your user's browser.

In the world of software, the term design pattern refers to a general repeatable solution to a commonly occurring problem in software design. It is a formalization of best practices that a developer can use. Like in the world of architecture, the pattern language has proven to be extremely helpful to communicate a certain way of solving a design problem to other programmers.

Is Django MVC?


Is Django MVC?
Model-View-Controller (MVC) is an architectural pattern invented by Xerox PARC in the 70s. Being the framework used to build user interfaces in Smalltalk, it gets an early mention in the GoF book.

Today, MVC is a very popular pattern in web application frameworks. A variant of the common question is whether Django is an MVC framework.

The answer is both yes and no. The MVC pattern advocates the decoupling of the presentation layer from the application logic. For instance, while designing an online game website API, you might present a game's high scores table as an HTML, XML, or comma-separated values (CSV) file. However, its underlying model class would be designed independently of how the data would be finally presented.

MVC is very rigid about what models, views, and controllers do. However, Django takes a much more practical view to web applications. Due to the nature of the HTTP protocol, each request for a web page is independent of any other request. Django's framework is designed like a pipeline to process each request and prepare a response.

Django calls this the Model-Template-View (MTV) architecture. There is a separation of concerns between the database interfacing classes (model), request-processing classes (view), and a templating language for the final presentation (template).

If you compare this with the classic MVC — a model is comparable to Django's Models; a view is usually Django's Templates, and the controller is the framework itself that processes an incoming HTTP request and routes it to the correct view function.

Python Zen and Django's design philosophy: Try entering import this in a Python prompt to view The Zen of Python.
https://docs.djangoproject.com/en/dev/misc/design-philosophies/


Application Design

- Gathering requirements
- Creating a concept document
- HTML mockups
- How to divide a project into apps
- Whether to write a new app or reuse an existing one
- Best practices before starting a project
- Why Python 3?
- Which Django version to use
- Starting the SuperBook project


How to Gather Requirements:

- Talk directly to the application owners even if they are not technically minded.
- Make sure you listen to their needs fully and note them.
- Don't use technical jargon such as models. Keep it simple and use end-user friendly terms such as a user profile.
- Set the right expectations. If something is not technically feasible or difficult, make sure you tell them right away.
- Sketch as much as possible. Humans are visual in nature. Websites more so. Use rough lines and stick figures. No need to be perfect.
- Break down process flows such as user signup. Any multistep functionality needs to be drawn as boxes connected by arrows.
- Next, work through the features list in the form of user stories or in any easily readable form.
- Play an active role in prioritizing the features into high, medium, or low buckets.
- Be very, very conservative in accepting new features.
- Post-meeting, share your notes with everyone to avoid misinterpretations.
--------------------------------------------------------------------------------
Here is a concept document for the SuperBook project:

Could you tell us briefly some of the features you noticed?

Sure, I think this is a pretty decent social network, where you can:

- Sign up with any username (no more, "enter your real name", silliness)
- Fans can follow people without having to add them as "friends"
- Make posts, comment on them, and re-share them
- Send a private post to another user

Everything is easy. It doesn't take a superhuman to figure it out.
----------------------------------------------------------------------------------------