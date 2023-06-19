# Asp.Net-Core-Full-coarse-Code
in this repository you can download the complete code of the Asp.net core 7 and also a project in asp.net core 


# MCV Part 2 ViewComponents start 
@*
    For more information on enabling MVC for empty projects, visit https://go.microsoft.com/fwlink/?LinkID=397860
*@
@{
    string title = "Wellcome to the Asp.net Again ";

}

<!DocType html>
<head>
    <title>@title</title>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
    <meta name="Author" content="W3docs">
    <link rel="stylesheet" type="text/css" href="~/style.css">
</head>
<body>
    <h1>Component views in ASp.Net Core </h1>
    <p>Today we start from the Component Views and so on this is the
        notes that takes some additional and theory information . </p>
        <p>in the shared folder we make a new item of razor layout vieew with the name of _Layout View . fter this define some content like make a navbar and links for the home and other pages 
            after this the render body div . we make this view for all views we can make the ViewStart file and tell the defualt layourt for the views  Run the aplication now </p>
            <p>for both of the pages like home and the about is need some of the common things we need to make the partial views for this but in this lecture i write some additional logic for this and make the component view </p>
            <p>Make new folder in the project and named as ViewComponent in this folder make a simple c# class name GridViewComponent (anything you want)  . now we inherit this class in inherit from the ViewComponent
                class an its in the mvc . every view componet have must the InvokeAsync method which is called automatically when the viewcomponent is called in the 
                any view   . return type of this is Task IViewComponentResult> /IViewComponentResult  . then return View . in the shared folder we make new folder calld components its ixed  then another folder 
            same as Viewcomponent class like in our example Grid . in the grid ad new view razor view empty add and select the razor view empty names Default.cshtml .
            its presentation logic for the view component</p>
            <p> in this we write some h1 tags . now we invoke the viewComponent in the indexView . we used the await component.InvokeAsync() method and
                pass the name of the view in our case Grid as parameters . now we invoked the viewComponent in the view . what if we changed the viewcomponent name  . like in the place of Defualt we write sample
                in this case we tell the return view method the view name like we pass the sample as the parameter . now the place of the heading we make a table in view component. 
            we also invoke this component in the about view we invoke this another way like we used the tagHelper </p>
            <h3>ViewComponent with viewData</h3>
            <p>its possible to pass data from viewcomponent class to viewcomponent view . i want to send the object in the view . i make a folder is Models and create the  Person.cs class 
                make the properties in this and make this class object in the view class and send the data by help of viewData or viewBag and then in the viewcomponent we
                access this and prints the data we also imports the models namespace in the _importsView file so its make accessable in any file 
                
            </p>
            <h3>ViewComponents as the stronglytyped viewComponents </h3>

            <p>As like partial view we can also make the strongly typed viewComponents inasp.net  . we bind the specific model class with this view component . and by the help of @Model 
                we can access the object that is passed from the viewComponent Class . </p>
                <h3>ViewComponent with parameters</h3>
                <p>like we wan to print the unique data every time when we invoke the viewcomponent its possible by the help of parametes . we pass the anoumimouse object in the viewcomponent
                    invokeAsync method then we see the unique Values every time .   </p>
                    <h3>ViewComponentResult </h3>
                    <p>SomeTimes We want to print the view on a click on a function or or need basis . its possible by returning the action method result
                        . we make a async request to the controller and the controller is return us the viewComponent as responce . and we render this responce in our page </p>


       <h1>The Dependency Injection </h1>
       <p>We writhe the bussines logic in the controller or in the view but thwre is an 
           other place to write the bussiness logic called the Services 
                  </p>
                  <h3>What is service</h3>
                  <p>The service is an abstraction layer bettween the prasantation layer and data layer</p>
                  <p>We make the new project by name the DEexample . then we edit the program.cs file  and after this </p>
                  <p class="bp">its good idea to make the service is seperate class  library becuase its good in the use of the other things .  </p>
                  <p>So  create the new project in the same namespace and then choose c# and in the third drop down list select the library  . select the class library simple .. 
                      name the class library like serviceLayer 
                      . the version yuo select must be same for the service and the project you make  . rrname the class like cities Service . This class includes the bussiness logic 
                  any middle wear logic are in the service  . make a string list and make a contsturctor. then make the mathod that  return the list of cities .  Then we make the new controller in the main project 
              MVC Empty controller . and create a view for this controller indx method . create the view bag title . create a shared folder in the views folder and add a new item  razor layout. 
          also make the wwwroot folder in the directory . we create some page content in the layout . make  a private readonly property of type citiesService class . we need to add the reference
          of the services in the web project to   access this service . right click on the project  then add then click project reference . alternative way is right click on dependencies 
      then add project dependencies then we select the path of the service and check the ckeck box . now we import the import the namespace in the home controller or in the imports 
  so we need to create the object of the cities service class . called instanciated the service . now we can class the methods or the variables of this class like getCities method calling 
. we send the cities list in the view and after this we are able to connect with the view in the view we make the strongly typed view . now we use this list to view the data in the page   </p>
<h2>Workflow of the services View or controller int asp.net core </h2>
<p>lets runn the applications add breakpoint in  the controller services and view as well . go to browser and making a request to refresh the page the controller is execute first then 
    the controll goes to the cities service and make objec of this then the controller methd is execute and controll goes into the service method and return the list of cities .
    then we will return the list in the view . and print the view in the web page . </p>





</body>

</html>

