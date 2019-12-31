# My README

## Description

bookmarks_final contains the author's final modules for his social website example which ran through Chapter 6, "Tracking User Actions".  I worked through the example using the files in this folder to verify that all the features work.  The only problem I found was with the images rankings page.  I'm not sure it listed every image and when I clicked on one image link, I got an error, so you may have to go back and work on this.

If I want to use any features from this project, I can refer to these files but then also look in ~/projects/django/django2_by_example/bookmarks where I have add comments to many of the modules.  Not that the files in that folder don't include every feature (I skipped a few) so not everything in that folder will work.

## Code

[Django-2-by-Example](https://github.com/PacktPublishing/Django-2-by-Example)
[Errata](https://github.com/Django-By-Example-ZH/Django-By-Example-ZH/issues/6)

## Virtual environment

    cd ~/projects/django/django2_by_example_solution/bookmarks_final
    workon django2_by_example

## Pip requirements

See requirements-to-freeze.txt.

## Development server

    cd ~/projects/django/django2_by_example_solution/bookmarks_final/bookmarks
    python manage.py runserver

## Ngrok server

This server is used in the bookmarklet chapter.  It creates a tunnel to expose your localhost to the Internet through both HTTP and HTTPS.

### Install Ngrok

    brew cask install ngrok

### Run Ngrok

    # Keep your Django development server running and start the Ngrok server.
    ngrok http 8000             # Ngrok URL -> https://e6cf301d.ngrok.io

    # Add the forwarding address to your ALLOWED_HOSTS setting.  For example,
    ALLOWED_HOSTS = [
        'mysite.com',
        'localhost',
        '127.0.0.1',
        'e6cf301d.ngrok.io'     # <- New Ngrok domain name
    ]

    # Test it's working by putting this HTTPS URL in your browser:
    https://e6cf301d.ngrok.io/account/login

    # Put the updated Ngrok domain name in the bookmarklet_launcher.js and js/bookmarklet.js files.  See loc. 3232.

## Run apps

    localhost:8000/blog
    localhost:8000/account

## Redis

If you don't start the Redis server, you'll see this error:

    redis.exceptions.ConnectionError: Error 61 connecting to localhost:6379.  Connection refused.

### Install Redis server

    brew install redis

### Run

    redis-server /usr/local/etc/redis.conf &

### Install Python [bindings](https://redis-py.readthedocs.io/

    pip install redis

## Images application

When you view the details for an image, e.g.  http://127.0.0.1:8000/images/detail/6/django-and-duke/, the image created by sorl-thumbnail, sorl thumbnail will create an image of the requested size and copy save a copy of that image in a media/cache subdirectory.
