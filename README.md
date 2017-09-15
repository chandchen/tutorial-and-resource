# Tutorials and Resources

#### Introduction:
> I am beginner in Django, here is about learning django framework resources, and some web development technology resources, just take down what I am learning during the process.

#### Walkthrough:

##### 1. About Python

[Python 3.6.2 documentation](https://docs.python.org/3.6/)

[PEP 8 -- Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008/)

[Python Social Auth documentation](https://python-social-auth.readthedocs.io/en/latest/index.html)

##### 2. About Django

[Django Documentation](https://docs.djangoproject.com/en/1.11/intro/)

[How to Extend Django User Model](https://simpleisbetterthancomplex.com/tutorial/2016/07/22/how-to-extend-django-user-model.html)

[venv](https://docs.python.org/3/library/venv.html#venv-def) — Creation of virtual environments

[Developing a Django app with zc.buildout](https://jacobian.org/writing/django-apps-with-buildout/)

[Directory Structure of a Buildout](http://www.buildout.org/en/latest/docs/dirstruct.html)

[Coverage.py](https://coverage.readthedocs.io/en/coverage-4.4.1/) — tool for measuring code coverage of Python programs.

[Practical Django Testing Examples: Views](https://django-testing-docs.readthedocs.io/en/latest/views.html)

[Introduction to Class-Based Views](https://hellowebbooks.com/news/introduction-to-class-based-views/)

##### 3. Git - Version control system

[Git Documentation](https://git-scm.com/doc)

[Become a git guru](https://www.atlassian.com/git/tutorials)

[Ignoring files - User Documentation](https://help.github.com/articles/ignoring-files/)

[Git - gitignore Documentation](https://git-scm.com/docs/gitignore)

[How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/)

##### 4. Celery - Celery is a task queue with batteries included.

[First Steps with Celery](http://docs.celeryproject.org/en/latest/getting-started/first-steps-with-celery.html#first-steps)

[Async Task - Celery Notes](http://python.jobbole.com/87086/)

[Asynchronous Tasks With Django and Celery](https://realpython.com/blog/python/asynchronous-tasks-with-django-and-celery/)

##### 5. API - Django REST Framework

[Django REST Framework](http://www.django-rest-framework.org/)

[REST APIs, Apps, and Django REST Framework](https://medium.com/@djstein/modern-django-part-2-rest-apis-apps-and-django-rest-framework-ea0cac5ab104)

[Django Rest Framework Serializers(CN)](https://zhujia.info/2017/07/03/DjangoRestFrameworkSerializerModels/)

##### 6. [FFmpeg - Audio/Video encoding](https://www.ffmpeg.org/ffmpeg.html#Simple-filtergraphs)

[FFmpeg Basic Usage](http://blog.csdn.net/doublefi123/article/details/24325159)

[Simplest Video Website: JavaEE+FFmpeg](http://blog.csdn.net/leixiaohua1020/article/details/43870599)

[A quick guide to using FFmpeg to convert media files](https://opensource.com/article/17/6/ffmpeg-convert-media-file-formats)

**ffmpy** [Python Package](https://pypi.python.org/pypi/ffmpy)  [documentation](https://ffmpy.readthedocs.io/en/latest/ffmpy.html)

ffmpy is a simplystic FFmpeg command line wrapper. It implements a Pythonic interface for FFmpeg command line compilation and uses Python subprocess module to execute compiled command line.

```
ff = FFmpeg(
        inputs={'input.ts': None},
        outputs={'output.mp4': '-c:a mp2 -c:v mpeg2video'}
)
ff.cmd
    'ffmpeg -i input.ts -c:a mp2 -c:v mpeg2video output.mp4'
ff.run()
```

##### 7. JavaScript - Frontend

[The Modern JavaScript Tutorial](https://javascript.info/)
