# Python_Django
Restaurant website using Django Framework

Note :
- Programming language used -> Python, Django framework, html, css, javascript
- The statements inside the single asterisk(*) marks are the commands for exicuting specific tasks as mentioned
- The statements inside the Plus(+) are Folders
- The statements inside the modulus(%) are django app

- Some example of commands,
- C:\Users\JIGAR\Desktop\Python_Projects\Project_0\src>python manage.py runserver
- C:\Users\JIGAR\Desktop\Python_Projects\Project_0\src>python manage.py migrate
- C:\Users\JIGAR\Desktop\Python_Projects\Project_0\src>python manage.py makemigrations
		

some library + framework of django used -> paginator,taggit,summernote,boostrap4


1. Create virtual environmet using command -> *virtualenv -p python Project_0*
	Here, "Project_0" is Folders name which is our virtual environment for this project[Restraurent website]


2. Activate Virtual Environment ->  *.\Scripts\activate*
	Here, we must go Inside the folder which has been created using Virtual environment CMD 


3. For a better user experience/sorted things we can create main folder
	Here we have created main folder as a name of +src+
	In this folder[src] we are creating our +app's+ for django projects.


4. After successfully creating virtual environment we have to install django in that folder
	we can install django using -> *pip install django* 


5. After installing we must start our project using command -> *django-admin startproject <Project_name> .*
	Full stop at the end indicates that starting our project[creates project file] inside that directory which we currently have opend in cmd 
	Here can put any suitable name for our root or main project folder

	This command will automatically brings manage.py file to run our server and db for database strorage
	!! db and manage.py !!

6. For checking that our project run perferctly we have to run our django project in browser ,
	for this we must have our virtual invironment activated,
	for rnning our project we must go inside main folder where we have our two files(db, manage.py) 
	we can run django project using command -> *python manage.py runserver*
	after running our server copy the http url to browser


7. For creating different app for the project we use -> *python startapp <app_name>*
	e.g. create our meals app with the help of -> *python startapp meals*

	whenever we create app using -> *python manage.py startapp blog*,
 	we have to add that app in to main project setting.py file inside of INSTALLED APP
 	eg. In this project we have created % meals,reservation,blog,aboutus,etc. % 
 	then repeat migrations
  
	After Creating new Models in side app Goto -> +admin of that app+
	import classes form module -> from .models import Class_1, Class_2
    	Enable(i.e Registering Model) ->  admin.site.register{class_1},
					  admin.site.register{class_2}, etc.


8. After running server we can create SuperUser -> *python manage.py createsuperuser*
	Here we have,
		admin
		1234


9. Django’s handling of database schema : 
	migrate, which is responsible for applying and unapplying migrations.
	makemigrations, which is responsible for creating new migrations based on the changes you have made to your models.
	

10. Some Example from code,
meals > Models
	create class for Meals 
		add attribute variables such as name, price etc.

		define neccesory function like(for get name Of Meals)
		def __str__(self):
        		return self.name
		

11. If in admin site we get plurals of all name like about_uss, Why Choose uss Chefss,
    insted of about us, Why Choose Us , Chef then we must fix this things with the help,
    class Meta and def __str__ INSIDE of that class(Here class = about us, Why Choose Us,Chef)

eg. class AboutUs(models.Model):
    title = models.CharField(max_length=50)
    content = models.TextField()
    image = models.ImageField(upload_to='about_us/')

    class Meta:
        verbose_name = 'about us'
        verbose_name_plural = 'about us'
    
    def __str__(self):
        return selft.title


12. create new app, add classes in models
	register models classes to admin.py 
	create/work on views.py
	CREATE urls.py (import views, assign appname="xyz", urlpatterns )
	Check view of every app 
	for view we must import class from models of that app
	then we should take request using def dunction by passing parameter as request


13. For view we must import class from models of that app
then we should take request using def dunction by passing parameter as request
