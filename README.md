**pip install django-material-admin**

1. Add **material.admin** and **material.admin.default** to your INSTALLED_APPS setting instead of **django.contrib.admin**::
 - required

.. code-block:: python

    INSTALLED_APPS = (
        'material',
        'material.admin',

        'django.contrib.auth',
        ...
    )


2. Include the material templates URLconf in your project **urls.py** like this:
 - required
.. code-block:: python

    from django.contrib import admin
    from django.urls import path

    urlpatterns = [
        path('admin/', admin.site.urls),
    ]