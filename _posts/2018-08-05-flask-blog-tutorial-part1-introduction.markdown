---
layout: post
title:  "Flask 블로그 1장 - Hello Flask"
date:   2018-08-05 19:51:12 +0900
categories: python flask
---

# 프로젝트 소개

이 시리즈는 Flask를 이용해서 아주 간단한 어플리케이션을 시작으로 기본적인 기능이 구현되어 있는 간단한 블로그를 완성해 나갈 예정입니다.

이를 통해 웹 어플리케이션이 어떤 방식으로 구현되는지 기본적인 내용을 파악할 수 있습니다.

본 시리즈는 [The Flask Mega-Tutorial Series](https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-i-hello-world)와 [Full feature flask plog tutorial series](https://www.youtube.com/watch?v=MwZwr5Tvyxo&list=PL-osiE80TeTs4UjLw5MM6OjgkjFeUxCYH)를 기본 골격으로 제작되었습니다.

## Flask

### Flask란 무엇인가

Flask는 마이크로 웹 프레임워크로 간결함을 추구하고 높은 자유도를 가지고 있습니다. 기본적인 구조가 명확해 단 몇줄의 코드만으로 웹 어플리케이션을 만들 수 있습니다.

### 선정 이유

여러 프레임 워크가 있지만 Flask를 선정한 이유는 어플리케이션을 구동하기 위해 필요한 코드가 Django에 비해 현저히 적고, Django의 프로젝트 개념과 같이 알고 있어야 하는 것들이 적어 처음 접하기 쉽다고 생각했습니다. 또한 자유도가 높고 기본적으로 제공되는 기능이 적기 때문에 웹 어플리케이션의 기초를 배우는데 적합하다 판단했습니다.

## 대상

본 시리즈는 Python에 대한 기초적인 부분은 다루지 않습니다. 따라서 문법과 같은 기초적인 내용에 대해서는 알고 있어야 합니다.

웹 어플리케이션인만큼 HTML과 CSS를 사용하긴 하지만 본 시리즈에서 중점적으로 다루는 부분은 아니라 몰라도 크게 지장은 없습니다. 하지만 기본적인 내용을 알고 있는 경우 더 쉽게 따라갈 수 있습니다.

## 최종 목표 소개

이 시리즈에서 다룰 블로그의 기능들은 다음과 같습니다.

### 로그인

![로그인]({{ "/assets/img/flask_blog_tutorials-chapter-1/login.gif" | absolute_url }})

### 회원 가입

![회원 가입]({{ "/assets/img/flask_blog_tutorials-chapter-1/registration.gif" | absolute_url }})

### 회원 정보 수정

![아바타 수정]({{ "/assets/img/flask_blog_tutorials-chapter-1/change_avatar.gif" | absolute_url }})

### 게시물 작성

![새 게시물]({{ "/assets/img/flask_blog_tutorials-chapter-1/new_post.gif" | absolute_url }})

### 게시물 수정, 삭제

![게시물 수정]({{ "/assets/img/flask_blog_tutorials-chapter-1/edit_post.gif" | absolute_url }})

![게시물 삭제]({{ "/assets/img/flask_blog_tutorials-chapter-1/delete_post.gif" | absolute_url }})

### 페이지 네비게이션

![게시물 삭제]({{ "/assets/img/flask_blog_tutorials-chapter-1/pagination.gif" | absolute_url }})

## 목차

1. 소개 (현재)
2. 템플릿
3. 부트 스트랩(Bootstrap)
4. 데이터 베이스
5. 폼
6. 사용자 인증
7. 단위 테스트
8. 구조 변경 #1 (패키지 구조)
9. 사용자 아바타
10. 게시물 기능
11. 구조 변경 #2 (어플리케이션 팩토리)
12. 페이지 네비게이션
13. 사용자 에러 페이지

# 개발환경 구축하기
## Python 설치

시스템에 Python이 설치되어 있지 않다면 [Python 공식 홈페이지](https://www.python.org)에서 설치할 수 있습니다.

Python이 정상적으로 설치되어 있으면 터미널에서 `python --version`을 입력합니다.

<figure>
  <figurecaption>터미널</figurecaption>
{% highlight powershell %}
PS> python --version
Python 3.7.0
{% endhighlight %}
</figure>

Python에서는 Flask와 같은 패키지들을 저장소에 모아 두어 간편하게 설치할 수 있는 시스템이 있습니다.
저장소 중 Python을 개발하는 단체에서 제공하는 패키지 저장소는 PYPI(Python Package Index)라는 이름으로 불립니다.
이 저장소에서 패키지를 설치하는 것은 `pip` 도구를 이용해 간편하게 수행할 수 있습니다.

`pip` 도구를 이용해 패키지를 설치하기 위해서는 터미널에서 다음과 같은 명령어를 사용합니다.

<figure>
  <figurecaption>터미널</figurecaption>
{% highlight powershell %}
pip install <패키지 이름>
{% endhighlight %}
</figure>

패키지 매니저를 이용해 파이썬 패키지를 설치하기전 `pip`를 업데이트 하겠습니다.
터미널에 다음과 같은 명령어를 입력합니다.

<figure>
  <figurecaption>터미널</figurecaption>
{% highlight powershell %}
PS> python -m pip install pip --upgrade
{% endhighlight %}
</figure>

시스템에 Flask를 설치하기 전에 가상환경을 구성하도록 하겠습니다.
가상 환경은 시스템에 설치되어있는 패키지와 격리된 가상의 환경을 만들어주는 역할을 하는데요.
이러한 가상환경을 구성하는 이유는 프로젝트 마다 필요한 패키지 버전이 다를 수 있는데, 이를 효과적으로 처리하기 위함입니다.

예를 들어 A라는  어플리케이션은 Flask 버전 0.11을 필요로 하고, B라는 어플리케이션은 Flask 버전을 0.12를 필요로 한다고 가정하겠습니다.
이 경우 B 어플리케이션의 종속성을 만족시키기 위해 시스템에 0.12를 설치하게 되면 A 어플리케이션의 종속성을 만족하지 못하게 됩니다.
그렇다고 어플리케이션을 수정할 때마다 매번 앱이 필요한 종속성을 만족시켜주기 위해 패키지를 재설치하게 된다면 설치하는데 시간도 많이 소요되고 불편하겠죠.

이러한 문제점을 해결하기 위해 가상 환경을 구축해서 프로젝트 별로 격리된 환경을 만들어 줍니다.

## virtualenv로 가상환경 구성

가상환경을 가능하게 해주는 도구는 `virtualenv`라고 하며, 이를 설치하기 위해 터미널에 다음과 같은 명령을 입력합니다.

<figure>
  <figurecaption>터미널</figurecaption>
{% highlight powershell %}
PS> pip install virtualenv
{% endhighlight %}
</figure>

`virtualenv`가 설치되었는지 확인하려면 터미널에 다음과 같은 명령을 입력합니다.

<figure>
  <figurecaption>터미널</figurecaption>
{% highlight powershell %}
PS> virtualenv --version
16.0.0
  {% endhighlight %}
</figure>

앞으로 사용할 프로젝트 폴더를 만듭니다. 여기서는 `flask_blog`라고 정하도록 하겠습니다.

프로젝트 폴더 하위에 가상 환경을 만듭니다.
가상 환경의 이름은 아무거나 상관 없지만 `env`, `venv`와 같은 이름을 주로 사용합니다.
여기서는 `venv`를 사용하도록 하겠습니다.

<figure>
  <figurecaption>터미널</figurecaption>
{% highlight powershell %}
PS flask_blog> virtualenv venv
Using base prefix 'c:\\program files\\python37'
New python executable in C:\Users\JUNMIN\documents\venv\Scripts\python.exe
Installing setuptools, pip, wheel...done.
{% endhighlight %}
</figure>

가상환경을 만들었으면 가상환경을 사용하기 위해 활성화 작업을 해야 합니다.

<figure>
  <figcaption>Windows</figcaption>
{% highlight powershell %}
PS flask_blog> ./venv/scripts/activate
{% endhighlight %}
</figure>

<figure>
  <figcaption>Linux</figcaption>
{% highlight powershell %}
flask_blog $ source ./venv/bin/activate
{% endhighlight %}
</figure>

가상 환경이 활성화 되면 터미널에 가상환경 이름이 표시됩니다.

<figure>
  <figcaption>Windows</figcaption>
{% highlight powershell %}
(venv) PS flask_blog>
{% endhighlight %}
</figure>

<figure>
  <figcaption>Linux</figcaption>
{% highlight bash %}
(venv) flask_blog $
{% endhighlight %}
</figure>

작업이 끝나고 가상환경에서 벗어나려면 간단하게

<figure>
  <figcaption>터미널</figcaption>
{% highlight powershell %}
PS > deactivate
{% endhighlight %}
</figure>

를 입력하면 됩니다.

## Flask 설치

먼저 가상 환경이 활성화 되어있는지 확인한 다음 `pip` 도구를 이용해 패키지를 설치합니다.

<figure>
  <figcaption>터미널</figcaption>
{% highlight powershell %}
(venv) PS > pip install flask
{% endhighlight %}
</figure>

정상적으로 설치되었는지 확인하기 위해서 `flask --version` 명령을 이용합니다.

<figure>
  <figcaption>터미널</figcaption>
{% highlight powershell %}
(venv) PS > flask --version
Flask 1.0.2
Python 3.7.0 (v3.7.0:1bf9cc5093, Jun 27 2018, 04:59:51) [MSC v.1914 64 bit (AMD64)]
{% endhighlight %}
</figure>

# 간단한 Flask 어플리케이션 만들기

프로젝트 디렉터리에 `app.py` 파일을 추가합니다.

<figure>
  <figcaption>디렉터리 구조</figcaption>
{% highlight powershell %}
flask_blog/
├── venv/
└── app.py
{% endhighlight %}
</figure>

간단한 Flask 어플리케이션은 [Flask 공식 홈페이지](http://flask.pocoo.org/)에 예제가 있습니다.
이 예제를 바탕으로 `app.py`를 작성하고 저장하겠습니다.

<figure>
  <figcaption>파일: ./app.py</figcaption>
{% highlight python linenos %}
from flask import Flask

app = Flask(__name__)

@app.route('/')
@app.route('/index')
def index():
    return 'Hello Flask!'
{% endhighlight %}
</figure>

위 코드는 `Flask` 클래스로부터 간단한 인스턴스를 만들어서 웹 서비스를 제공합니다.
여기서 `Flask` 클래스에 전달된 `__name__` 파라미터는 Flask 어플리케이션을 구분하기 위한 구분자로 사용되며 거의 모든 경우에 `__name__`를 전달해주면 완벽하게 동작합니다.

그 다음 함수에 `@app.route` 데코레이터가 달려있습니다.
이 데코레이터는 URL과 함수를 이어주는 역할을 하는데, 위의 경우에는 라우트가 `/`와 `/index`로 두 개 달려 있습니다.
따라서 웹 브라우저가 `/` 또는 `/index` 페이지를 요청하게 되면 어플리케이션에서 `index`함수를 호출하여 그 결과를 웹 브라우저에 전달하게 됩니다.

## Flask 서버 실행

Flask 서버를 실행하기 위해 필요한 환경 변수들을 설정합니다.
모든 작업은 가상 환경이 실행중인 상태에서 수행해야 합니다.

<figure>
  <figcaption>Windows</figcaption>
{% highlight powershell %}
(venv) PS> $env:FLASK_APP="app.py"
(venv) PS> $env:FLASK_DEBUG="True"
{% endhighlight %}
</figure>

`FLASK_APP`은 Flask 서버를 기동할 때, 실행할 어플리케이션을 지정해주는 역할을 합니다.
`FLASK_DEBUG`는 Flask 어플리케이션에 디버그 모드를 활성화 하여 문제가 발생한 경우 어떤 문제가 발생했는지 자세히 알려줍니다.
또한 어플리케이션 코드가 변경되었을 때, 자동으로 Flask 서버를 재시작하여 매번 서버를 재시작해야 하는 귀찮음을 덜어줍니다.
만약 자동으로 서버를 재시작하고 싶지 않은 경우에는 `flask run --no-restart` 스위치를 넣어주면 됩니다.

환경 변수 설정이 끝나면 다음과 같은 명령을 이용해 서버를 실행할 수 있습니다.

<figure>
  <figcaption>Windows</figcaption>
{% highlight powershell %}
(venv) PS> flask run
 * Serving Flask app "app.py" (lazy loading)
 * Environment: production
   WARNING: Do not use the development server in a production environment.
   Use a production WSGI server instead.
 * Debug mode: on
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 101-892-184
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
{% endhighlight %}
</figure>

`* Running on`메시지가 뜨면 웹 브라우저를 열고 주소창에 http://localhost:5000 을 입력한 다음 접속합니다.

![인덱스 페이지]({{ "/assets/img/flask_blog_tutorials-chapter-1/hello_flask.png" | absolute_url }})

## About 페이지 추가

간단한 어플리케이션에 about 페이지를 추가해보겠습니다.

<figure>
  <figcaption>파일: /app.py</figcaption>
{% highlight python linenos %}
from flask import Flask

app = Flask(__name__)

@app.route('/')
@app.route('/index')
def index():
    return 'Hello Flask!'

# 추가
@app.route('/about')
def about():
  return 'About 페이지'
{% endhighlight %}
</figure>

코드를 수정한 후, 저장을 하면 디버그 모드가 켜져 있기 때문에 터미널에 `* Detected change in 'flask_blog\'` 이런 문구가 나오면서 서버가 자동으로 재시작 됩니다. 따라서 코드를 수정한 다음 서버를 다시 실행할 필요가 없습니다.

추가한 About 페이지를 확인하기 위해서는 http://localhost:5000/about 을 접속합니다.

![어바웃 페이지]({{ "/assets/img/flask_blog_tutorials-chapter-1/about_page.png" | absolute_url }})

이를 통해 `@app.route` 데코레이터가 어떤식으로 동작하는지 대략적으로 파악할 수 있습니다. 웹 브라우저가 `/` 페이지를 요청하면 `@app.route('/')`가 달려있는 `index` 함수를 실행해서 그 결과를 전달해주고, `/about` 페이지를 요청하면 `@app.route('/about')`이 달려있는 `about` 함수의 결과를 전달합니다.

현재까지 작성된 전체 코드는 [Flask blog tutorial Chapter1](https://github.com/LazyRichard/flask_blog_tutorial/tree/Chapter_1)에서 확인할 수 있습니다.
