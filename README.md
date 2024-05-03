## Django rest framework setup

<br>

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


#### JWT tokens, user registration, and cookies setup


| Step | Description                                                                                                    | Command                                          |
|------|----------------------------------------------------------------------------------------------------------------|--------------------------------------------------|
| 1    | Install `dj-rest-auth` package for JWT token authentication                                                   | `pip3 install dj-rest-auth==2.1.9`              |
| 2    | Add `rest_framework.authtoken` and `dj_rest_auth` to `INSTALLED_APPS`                                         | Add the apps to `INSTALLED_APPS` in `settings.py`|
| 3    | Include `dj_rest_auth.urls` in the main URL patterns list                                                        | Add `path('dj-rest-auth/', include('dj_rest_auth.urls'))` to `urls.py`                                        |
| 4    | Migrate the database schema for `dj-rest-auth`                                                                  | `python3 manage.py migrate`                     |
| 5    | Install `dj-rest-auth` with social authentication support                                                       | `pip install 'dj-rest-auth[with_social]'`       |
| 6    | Add necessary apps for user registration to `INSTALLED_APPS`                                                     | Add apps to `INSTALLED_APPS` in `settings.py` including:<br>`'django.contrib.sites',`<br>`'allauth',`<br>`'allauth.account',`<br>`'allauth.socialaccount',`<br>`'dj_rest_auth.registration'`|
| 7    | Set the `SITE_ID` to 1                                                                                         | Set `SITE_ID = 1` in `settings.py`              |
| 8    | Include `dj_rest_auth.registration.urls` in the main URL patterns list                                         | Add `path('dj-rest-auth/registration/', include('dj_rest_auth.registration.urls'))` to `urls.py`           |
| 9    | Install `djangorestframework-simplejwt` package for JWT token support                                           | `pip install djangorestframework-simplejwt`     |
| 10   | Configure DRF authentication settings based on environment (development or production)                         | Update `REST_FRAMEWORK` settings in `settings.py` as follows:<br>```python
'REST_FRAMEWORK': {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework.authentication.SessionAuthentication' if 'DEV' in os.environ else 'dj_rest_auth.jwt_auth.JWTCookieAuthentication',
    ],
    'DEFAULT_PAGINATION_CLASS': 'rest_framework.pagination.PageNumberPagination',
    'PAGE_SIZE': 10,
    'DATETIME_FORMAT': '%d %b %Y',
}```|
| 11   | Enable token authentication in DRF by setting `REST_USE_JWT` to `True`                                          | Set `REST_USE_JWT = True` in `settings.py`      |
| 12   | Ensure JWT tokens are sent only over HTTPS by setting `JWT_AUTH_SECURE` to `True`                               | Set `JWT_AUTH_SECURE = True` in `settings.py`   |
| 13   | Specify the name of the authentication cookie by setting `JWT_AUTH_COOKIE`                                      | Set `JWT_AUTH_COOKIE = 'my-app-auth'` in `settings.py`|
| 14   | Specify the name of the refresh token cookie by setting `JWT_AUTH_REFRESH_COOKIE`                                | Set `JWT_AUTH_REFRESH_COOKIE = 'my-refresh-token'` in `settings.py`|

