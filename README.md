# TMWebService

           TMWebService Framework
           ======================
-------------------------------------
For configure of our Framework.
Download the TMWebService.jar file and 
keep it into ..\WEB-INF\lib folder

Download web.xml and keep into
..\WEB-INF folder.
-----------------------------------
in ..\WEB-INF\classes folder
make a configuration file
named as ServiceConfiguration.conf
Content of these file should be 
in this form.
{
packages:["package 1","package 2",..,"package n"]
}
write name of those package where your service
class reside.

If your service is in the form jar file.
then keep this jar file into myLib folder(Compulsarily)
-----------------------------------
-----------------------------------
A zip file is provide which is our sample 
web application. Download it. and unzip into 
webapps folder of tomcat.
and Check our Framework.

======================================
Dependency jar File:(should be in lib folder)
1)gson-2.8.2.jar
2)itext jar files	

======================================
interface :com.thinking.machines.interfaces.WebServiceInterface;
Service Class:com.thinking.machines.servlets.TMService;
===========================
package name
com.thinking.machines.servlets.*;
com.thinking.machines.annotations.*;
com.thinking.machines.interfaces.*;

All the annotations are under this package
com.thinking.machines.annotations.*;

--------------------------------------
For getting the report of service.
type in address bar ../service/tm-report/report 
Report will save in ../WEB-INF/report folder
Report File Name:Service.pdf
--------------------------------------
----------------------------------------------------
If there is any kind of error comes while running
our framework. A pdf file will gets generate in the
specific folder ..\WEB-INF\report\error.pdf
in this error.pdf file you will get the appropriate 
reason why is there any error.and how to resolve it.
-----------------------------------------------------
Point To remember while using our TMWebService Framework
--------------------------------------------------------
1)GET type request not allowed in our framework
  (Strickly use POST TYPE request)
2)Service should have only one parameter.(If there is 
   need we can inject dependency like ServlectContext,
   HttpServletRequest,HttpServletResponse);
3)Following are the annotation are used neccessary
  * @Path(value) along with service Class and Method
  * @ResponseType("value") along with service Method
     in these case value is "text/html" or "json" or 
     "application/pdf" or "none"
  * @Secured("className along with package name")
     here only name of those class which implements
     WebServiceInterface. and define 2 method which 
     is declared in WebServiceInterface

  The above three annotation is mandatory.
  while rest is optional
  
  * @Forward("path")
    if you want to forward request after processing 
    of the service then use Forward annotation with
    proper path.Our Framework will forward request 
    after the processing of these service
    Note: when use Forward annotation Value of 
    ResponseType Annotation should be "none"
    
  * @Upload 
    if you want to download file.use this.
    if there is a service which has Upload annotation.
    our framework will receive file and provide
    file Array to the service


===================================================
