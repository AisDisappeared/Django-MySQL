
# Connecting Django with MySQL

Hi guys , I'm Ali seyfi Python Backend Developer and in this repository we are going to connect the Django application to
the MySQL database .

I hope it will be useful for you !

&nbsp;

## At first ensure that you also have mysql server on your operating system

### If you don't , you can install it from MySQL official website

[Download MySQL](https://dev.mysql.com/)

&nbsp;

If you are using ubuntu , you can download and install it using the command below :

~~~bash
sudo apt install mysql-server
~~~

## 1 - Create New Database

So open your shell and command line and start the mysql server by running this command :

~~~bash
mysql -u username -p -h hostname
~~~

Also if you are on ubuntu , you can connect by using these commands :

~~~bash
sudo mysql
~~~

### or

~~~bash
mysql -u root -p 
~~~

#### For creating new database run this statement

~~~bash
CREATE DATABASE testdb;
~~~

&nbsp;

## 2 - Update the settings.py - Database section

Replace this configuration with the django default sqlite3 configs in settings file :

~~~python
DATABASES = {  
    'default': {  
        'ENGINE': 'django.db.backends.mysql',  
        'NAME': 'testdb',  
        'USER': 'root',  
        'PASSWORD': 'Your-System-Password',  
        'HOST': '127.0.0.1',  
        'PORT': '3306',  
        'OPTIONS': {  
            'init_command': "SET sql_mode='STRICT_TRANS_TABLES'"  
        }  
    }  
} 
~~~

### Note : Don't remember to replace the "testdb" with your database name and also "Your-System-Password" with your system password  

&nbsp;

## 3 - Install mysqlclient package

Install the mysqlclient module into your project by using the command below :

~~~bash
pip install mysqlclient  
~~~

&nbsp;

## 4 - Migrate

Now we are ready to migrate or create tables in the newly created database. In this final step, we will run the migrate command and it will create the exiting tables into new database .

~~~bash
python manage.py migrate  
~~~

# And That's All
