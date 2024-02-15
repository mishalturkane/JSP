Author : https://mishalturkane.github.io/
# Introduction To JSP 📝
The term JSP stands for Java Server Pages and it is a dynamic web page generation technology given by sun microsystems in the year 1999. 
The main aim of providing JSP was to simplify the development of the Java-based web application and remove the drawbacks of servlets. 

However in today’s web development scenario both servlets and JSP have their own importance and should be cordially used in any industry standards-based web application.

# DRAWBACKS OF SERVLET! 
>In **servlets** , a programmer has to extend specific servlet class (HttpServlet or GenericServlet) .


>Programmer has to provide complete and exact prototype of the method he has to override which are doGet() and doPost() .

>We have to create the mapping of servlet inside web.xml.

>In a servlet we embed HTML inside java code i.e all the HTML part is mentioned within the println( ) method which is very difficult since we have to follow all strict rules of java.

>Any change in the servlet requires recompilation and redeployment of the application by restarting the server


# ADVANTAGES  OF  JSP!
>JSP  are very small in size as compared to a servlet.

>They use some special tags to embed java inside the HTML part and because of this they are much easier to handle compared to a servlet . 

>A JSP page gets automatically compiled by the container so we don’t have to compile it like a servlet.

>Moreover they do not require web.xml for themselves i.e. no mapping is needed .

>Also any change made in a jsp page does not require any recompilation or restarting the server. It is handled automatically by the container.

# Servlet Code for Printing Date and Time in Java

```
import javax.servlet.http.*;
import javax.servlet.*;
import java.io.*;
import java.util.Date;
public class MyClientInfoServlet extends HttpServlet
{
protected void doGet(HttpServletRequest req,HttpServletResponse resp) throws ServletException,IOException
   {
 	resp.setContentType("text/html");
	PrintWriter pw=resp.getWriter();

	pw.println("<html>");
	pw.println("<head><title>Client Details</title>  <style> h2{color: red;} </style> </head>");

	pw.println("<body>");
	pw.println("<p>Current data and time:</p>");

	
        Date today = new Date();
        
        
	pw.println("<h2>" + today + "</h2>");

	pw.println("</body>");
	pw.println("</html>");

	pw.close();
    }
}
```
# JSP  FOR  DATE TIME
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
# Directory - Structure 
![image](https://github.com/mishalturkane/JSP/assets/95625543/dac81033-8771-438f-865d-32df5c53a15b)

# Life Cycle of JSP Page
**A JSP page is converted into a Servlet in order to service requests.**

**The translation of a JSP page to a Servlet is called Lifecycle of JSP.**

**JSP Lifecycle is exactly same as the Servlet Lifecycle, with one additional first step, which is, translation of JSP code to Servlet code.**

# Following are the JSP Lifecycle steps:

>Translation of JSP to Servlet code.

>Compilation of Servlet to bytecode.

>Loading Servlet class.

>Instantiating the servlet .

>Initialization by calling jspInit() method

>Request Processing by calling _jspService() method

>Destroying by calling jspDestroy() method
# Phases
1.Translation Phase:  -When first request  of a jsp page comes then  the container translates .jsp page into .java file 
			Ex : showdate.jsp to showdate_jsp.java .
   
2.Compilation Phase : Immediately after translation the compilation of  servlet to produce .class file is done by the container .

3.Loading Phase: As soon as the compilation is done , the .class file is loaded in server’s memory

4.Instantiation Phase : Then the object of servlet is created 


5.Initialization Phase  : Now the container calls the jspInit() method to initialize the servlet instance

6.Request processing Phase : A new thread is then created, which invokes the_jspService() method, with  request (HttpServletRequest) and response (HttpServletRespnse) objects as parameters.
**Now for every next request only the 6th step is executed . However if the jsp page is edited then again all the previous steps are repeated**


7.Destruction Phase: This phase comes when the container decides it no longer needs the servlet instance to service requests. It then calls jspdestroy() method and the servlet is ready for a garbage collection


#How A JSP Page Is Processed By Container 
![image](https://github.com/mishalturkane/JSP/assets/95625543/e14b3015-db10-47a1-8d70-c47e6cb36072)
![image](https://github.com/mishalturkane/JSP/assets/95625543/41cbfcff-7f89-4b34-8249-750ef92e3c67)

