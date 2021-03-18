# Django-ContactForm-with-Email-Backend

In this post I want to talk about how can we send emails using Django and Gmail, I read a lot of articles about this but none of them is working for me, this is my way of doing this

Setup Django 💚
first let's install django
 pip install django
start a django project
django-admin startproject send_gmail
start a django app
cd send_gmail
python manage.py  startapp send
add the app to settings.py installed app
# send_gmail/settings.py
INSTALLED_APPS = [
...
send,
]
migrate and create a super user
python manage.py  migrate
python manage.py createsuperuser
check this post if you want to know more about how to create a virtual environment , or how to install Django and start your project

The Gmail part ✉
now you need to create a Gmail account and then click on Manage your google account
manage account screen shot

now click on the Security tab

image account security

make sure to enable two steps verification

enter image description here

now click on App passwords

enter image description here

you have to type your password again

Confirm your password

click on select app choose *** other (Custome Name) *** and give a name to you app

Create a new app

the last step click on generate and Gmail will generate a key or an app password make sure to copy this key or save it in a text file

Create a new app

Edit your settings.py file
#gmail_send/settings.py
EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
EMAIL_HOST = 'smtp.gmail.com'
EMAIL_HOST_USER = 'yoorusername@gmail.com'
EMAIL_HOST_PASSWORD = 'key' #past the key or password app here
EMAIL_PORT = 587
EMAIL_USE_TLS = True
DEFAULT_FROM_EMAIL = 'default from email'
🎉🎉 now you are ready to send emails with Django and Gmail in production🎉🎉

For further exploration
you can use SendGrid, Mailgun, Sendinblue... for your apps too
don't forget to put your key in a .env file
