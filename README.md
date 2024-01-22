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

3. Include the material settings in your project **settings.py** like this:
 - required

.. code-block:: python
    _ = lambda x: x


    MATERIAL_ADMIN_SITE = {
        'HEADER':  _('CLK'),  # Admin site header
        'TITLE':  _('CLK'),  # Admin site title
        # 'FAVICON':  'path/to/favicon',  # Admin site favicon (path to static should be specified)
        'MAIN_BG_COLOR':  '#a6ce3a',  # Admin site main color, css color should be specified
        'MAIN_HOVER_COLOR':  '#93b732',  # Admin site main hover color, css color should be specified
        'PROFILE_PICTURE':  '/images/logo.svg',  # Admin site profile picture (path to static should be specified)
        'PROFILE_BG':  '/images/clkbg.png',  # Admin site profile background (path to static should be specified)
        'LOGIN_LOGO':  '/images/logo.svg',  # Admin site logo on login page (path to static should be specified)
        'LOGOUT_BG':  '/images/clkbg.png',  # Admin site background on login/logout pages (path to static should be specified)
        'SHOW_THEMES':  True,  #  Show default admin themes button
        'TRAY_REVERSE': True,  # Hide object-tools and additional-submit-line by default
        'NAVBAR_REVERSE': True,  # Hide side navbar by default
        'SHOW_COUNTS': True, # Show instances counts for each model
        'APP_ICONS': {  # Set icons for applications(lowercase), including 3rd party apps, {'application_name': 'material_icon_name', ...}
            'sites': 'send',
        },
        'MODEL_ICONS': {  # Set icons for models(lowercase), including 3rd party models, {'model_name': 'material_icon_name', ...}
            'site': 'contact_mail',
        }
    }