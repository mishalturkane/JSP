# 🧩JSP Elements

* A  jsp page can contain various types of  jsp based programming elements.
* Each of these elements allow us to write java based statements in our page and are used to make our page dynamic.


# 🔖JSP Scripting Tags
* Jsp tags are special tags given by JSP which allow us to insert Java code within a Jsp page .

* Whenever the container translates a jsp page into a servlet then it places all the coding written within Jsp tags inside the methods :
                  jspInit( )
                  _jspService( )
                  jspDestroy( )
 # 1️⃣  Scriptlet Tag
**"Whatever can be done in a single method, can also be done in the scriptlet tag."**
> The scriplet tag allows us to embed java code within the jsp page i.e it makes our page dynamic.

> Whatever code we write inside a scriplet gets pasted within _jspService ( ) method by the container .
  
  Syntax:
  ```
    <%
    %>
  ```
Code : 
```
<!DOCTYPE html>
<html lang="en">
<head>
   
    <title>Tags in JSP </title>
    <style>
        h3{
            color: red;
        }
    </style>
</head>
<body>
    <%
           java.util.Date today=new java.util.Date();
           out.println("<h3>Current date and time"+today+"</h3>");
    %>
</body>
</html>
```
# 2️⃣ Declarative Tags
**"Whatever is written at the class level, all of that is included in declarative tags."**

> Declarative tags are similar to scriptlet tag because they also allow us to write pure Java code within their body.

> However whatever code we write in them gets pasted by the Container in the generated Servlet's class body, outside any method.

Syntax
```
<%!
%>
```
Code
```
<!DOCTYPE html>
<html lang="en">
<head>
   
    <title>Tags in JSP </title>
    <style>
        h3{
            color: red;
        }
    </style>
</head>
<body>
    <%!
          int count=0;
    %>
    <%
        out.println("<h3>Your Visited Number on this site:"+count+"</h3>");
        ++count;
    %>
</body>
</html>
```
