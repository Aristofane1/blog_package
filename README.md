## Package Description

Django easy blog post is a package that allows you to create blog posts
with a text editor to customize the content of your
 publication.

## Quick Start
1- Add __post__ in your INSTALLED_APPS and update settings

    INSTALLED_APPS = [
    ...
    'ckeditor',
    'ckeditor_uploader',
    'post',
    ]
    
    CKEDITOR_UPLOAD_PATH = "uploads/"
2- update your project url 

    from django.conf.urls.static import static
    from . import settings
    ...
    urlpatterns = [
    ...
    path('ckeditor', include('ckeditor_uploader.urls')),
    ...
    ]+static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)

    

3- Migrate your project

    python manage.py migrations post
    python manage.py migrate

4 Create super user, run your app and go to admin to create your blog post

5- Use __post_list__ tag to get all posts list on your template

    {% load post_tags %}
    {% for post in ''|post_list %}
     ...
    {% endfor %}

