[Code Institute Gitpod Full Template](https://github.com/Code-Institute-Org/gitpod-full-template)


| Step | Description                                                                  | Command                                          |
|------|------------------------------------------------------------------------------|--------------------------------------------------|
| 1    | Install Django version less than 4                                           | `pip3 install 'django<4'`                        |
| 2    | Create a Django project                                                      | `django-admin startproject project_name .`       |
| 3    | Install Cloudinary Storage                                                   | `pip install django-cloudinary-storage`          |
| 4    | Install Pillow                                                                | `pip install Pillow`                             |
| 5    | Set up Cloudinary API Key                                                    | Create an `env.py` file with Cloudinary API key  |
| 6    | Update Django Settings                                                       | Add Cloudinary to `INSTALLED_APPS`               |
|      |                                                                              | Configure Cloudinary storage settings           |
| 7    | Specify Allowed Hosts                                                        | Add allowed hosts to `settings.py`               |
| 8    | Create a Django App                                                          | `python3 manage.py startapp app_name`            |
| 9    | Freeze requirements into requirements.txt file                               | `pip freeze > requirements.txt`                  |
| 10   | Install Django REST Framework                                                | `pip install djangorestframework`                |
| 11   | Run the Django development server                                            | `python3 manage.py runserver`                    |
