# KISS Web Tutorials - Part 1 - Hello World #

Web applications built with kiss web are controller-based. This means that when a page is retrieved from the web server, a controller object will be instantiated and one or more methods are executed, after which the controller decides what view to display. The view is then rendered to the web browser.

When you are have worked with controllers and views before, this may all look familiar, but we will give a simple example to show how it works.

Let's create a simple controller class Home:
```
class HomeController : Controller
{
        [UrlRoute("default.aspx", "master")]
        void index()
        {
            ViewData["msg"] = "Hello World!";
        }
}
```
when you type "http://www.yousite.com/default.aspx" in your browser, the index() method will be executed.

As you can see, **UrlRoute** defined on the index() method. This defines what url to user and what templates to render.

For the above example, templates:
```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<JC:Head runat="server" />
<body>
    $!msg
</body>
</html>
```
The final output will be:

---

`Hello World!`

code:http://kiss-project.googlecode.com/files/tutorial_1.zip