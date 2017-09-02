# Learning-resource

#### Introduction:
> Here is about learning django tutorial, and some web development technology resource, take down what I am learning during the process.

#### Walkthrough:

##### 1. About Django

[Django Documentation](https://docs.djangoproject.com/en/1.11/intro/)

[How to Extend Django User Model](https://simpleisbetterthancomplex.com/tutorial/2016/07/22/how-to-extend-django-user-model.html)

[venv](https://docs.python.org/3/library/venv.html#venv-def) — Creation of virtual environments

[Developing a Django app with zc.buildout](https://jacobian.org/writing/django-apps-with-buildout/)

[Become a git guru](https://www.atlassian.com/git/tutorials)

[How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/)

[Coverage.py](https://coverage.readthedocs.io/en/coverage-4.4.1/) — tool for measuring code coverage of Python programs.

##### 2. API

[Django REST Framework](http://www.django-rest-framework.org/)

[A quick guide to using FFmpeg to convert media files](https://opensource.com/article/17/6/ffmpeg-convert-media-file-formats)


##### 3. [FFmpeg](https://www.ffmpeg.org/ffmpeg.html#Simple-filtergraphs)

[FFmpeg Basic Usage](http://blog.csdn.net/doublefi123/article/details/24325159)

[Simplest Video Website: JavaEE+FFmpeg](http://blog.csdn.net/leixiaohua1020/article/details/43870599)

**ffmpy** [Python Package](https://pypi.python.org/pypi/ffmpy) [documentation](https://ffmpy.readthedocs.io/en/latest/ffmpy.html)

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
