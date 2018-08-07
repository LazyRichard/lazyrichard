---
layout: post
title:  "Flask 블로그 3장 - 부트스트랩"
date:   2018-08-07 14:34:00 +0900
categories: python flask
---

이전에 우리는 Flask의 템플릿 기능을 이용해 사용자에게 보여질 부분과 어플리케이션 코드를 분리했습니다.
또한 jinja2를 이용해 html의 내용을 동적으로 생성하도록 코드를 작성하여 여러 상황에 유연하게 대처할 수 있게 코드를 작성했습니다.

이번에는 어플리케이션의 디자인을 수정하도록 하겠습니다.
기능을 변경하는 것이 아닌 디자인을 변경하는 만큼 아래 코드를 복사 붙여 넣기 하는 것을 추천합니다.

# 부트 스트랩(Bootstrap)

부트스트랩은 웹을 개발하기 위한 프레임워크로 손쉽게 반응형 웹을 만들 수 있습니다.

먼저 `layout.html`에 홈페이지의 기본이 될 테마를 작성합니다.

<figure>
  <figcaption>파일: /templates/layout.html</figcaption>
{% highlight jinja linenos %}
{% raw %}
<!DOCTYPE HTML>
<html lang="kr">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <meta name="description" content="">
    <meta name="author" content="">
    <link rel="icon" href="../../../../favicon.ico">

    {% if title %}
      <title>Flask 블로그 - {{ title }}</title>
    {% else %}
      <title>Flask 블로그</title>
    {% endif %}

    <!-- Bootstrap core CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css"
          integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO" crossorigin="anonymous">

    <!-- Font awesome CSS -->
    <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.2.0/css/all.css"
          integrity="sha384-hWVjflwFxL6sNzntih27bfxkr27PmbbK/iSvJ+a4+0owXq79v+lsFkW54bOGbiDQ" crossorigin="anonymous">

    <!-- Custom styles for this template -->
    <link rel="stylesheet" href="{{ url_for('static', filename='layout.css') }}">
    {% block stylesheet %}{% endblock %}
  </head>

  <body>
    <header class="site-header">
      <nav class="navbar navbar-expand-md fixed-top navbar-dark bg-dark mb-4">
        <a class="navbar-brand" href="{{ url_for('index') }}">Flask 블로그</a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarCollapse" aria-controls="navbarCollapse" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarCollapse">
          <ul class="navbar-nav mr-auto">
            <li class="nav-item active">
              <a class="nav-link" href="{{ url_for('index') }}">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="{{ url_for('about') }}">About</a>
            </li>
          </ul>

          <!-- Navbar right side -->
          <div class="navbar-nav mt-mb-0">
            <a class="nav-item nav-link" href="{#{ url_for('login') }#}">Login</a>
            <a class="nav-item nav-link" href="{#{ url_for('registration') }#}">Register</a>
          </div>
        </div>
      </nav>
    </header>

    <main role="main">
    <!-- Main content block -->
    {% block content %}{% endblock %}
    </main>

    <!-- Bootstrap core JavaScript
    ================================================== -->
    <!-- Placed at the end of the document so the pages load faster -->
    <script src="https://code.jquery.com/jquery-3.3.1.min.js"
    		integrity="sha256-FgpCb/KJQlLNfOu91ta32o/NMZxltwRo8QtmkMRdAu8=" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js"
            integrity="sha384-ZMP7rVo3mIykV+2+9J3UJ46jBk0WLaUAdn689aCwoqbBJiSnjAK/l8WvCWPIPm49" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js"
            integrity="sha384-ChfqqxuZUCnJSK3+MXmPNIyE6ZbWh2IMqE241rYiqJxyMiZ6OW/JmZQ5stwEULTy" crossorigin="anonymous"></script>
    
    <!-- Font awesome -->
    <script defer src="https://use.fontawesome.com/releases/v5.2.0/js/all.js"
            integrity="sha384-4oV5EgaV02iISL2ban6c/RmotsABqE4yZxZLcYMAdG7FAPsyHYAPpywE9PJo+Khy" crossorigin="anonymous"></script>
    
    <!-- Custom scripts -->
    {% block scripts %}{% endblock %}
  </body>
</html>
{% endraw %}
{% endhighlight %}
</figure>

웹 사이트가 제대로 보이기 위해서는 다음과 같은 스타일 시트 파일이 필요합니다.

<figure>
  <figcaption>파일: /static/layout.css</figcaption>
{% highlight css linenos %}
{% raw %}
html {
  position: relative;
  min-height: 100%;
}

body {
  padding-top: 56px;
}
{% endraw %}
{% endhighlight %}
</figure>

그 다음은 메인 페이지를 수정하도록 하겠습니다.

<figure>
  <figcaption>파일: /templates/index.html</figcaption>
{% highlight jinja linenos %}
{% raw %}
{% extends 'layout.html' %}

{% block content %}
<div class="container">
  <div class="row">
    <div class="col-md-8">
      {% for post in posts %}
      <article>
        <hr>
        <div class="row">
          <div class="col">
            <a class="h1" href="#">{{ post.title }}</a>
            <p class="text-justify">{{ post.content }}</p>
          </div>
          <div class="col-md-2 d-flex flex-column">
            <img class="rounded-circle mx-auto" src="#" data-src="holder.js/64x64" width="64px" height="64px">
            <p class="text-muted text-center">{{ post.author.username }}</p>
          </div>
        </div>
        <small class="text-muted">{{ post.date_posted.strftime('%Y-%m-%d') }}</small>
      </article>
      {% endfor %}
    </div>
    
    <aside class="col-md-4 my-3">
      <h2>사이드 바</h2>
      <ul class="list-group">
        <li class="list-group-item">사이드바 아이템1</li>
        <li class="list-group-item">사이드바 아이템2</li>
        <li class="list-group-item">사이드바 아이템3</li>
        <li class="list-group-item">사이드바 아이템4</li>
      </ul>
    </aside>
  </div>
</div>
{% endblock %}

{% block scripts %}
  <script src=https://cdnjs.cloudflare.com/ajax/libs/holder/2.9.4/holder.min.js></script>
{% endblock %}
{% endraw %}
{% endhighlight %}
</figure>

마지막으로 About 페이지를 수정합니다.

<figure>
  <figcaption>파일: /templates/about.html</figcaption>
{% highlight jinja linenos %}
{% raw %}
{% extends 'layout.html' %}

{% block content %}
<div class="container">
    <h1>About 페이지</h1>
</div>
{% endblock %}
{% endraw %}
{% endhighlight %}
</figure>

파일을 다 만들고 난 다음 디렉터리 구조는 다음과 같습니다.

<figure>
  <figcaption>디렉터리 구조</figcaption>
{% highlight bash %}
flask_blog/
├── templates/
│   ├── about.html
│   ├── index.html
│   └── layout.html
├── static/
│   └── layout.css
├── venv/
└── app.py
{% endhighlight %}
</figure>

* 메인 페이지

![부트스트랩이 적용된 메인 페이지]({{ "/assets/img/flask_blog_tutorials-chapter-3/bootstrap_index.png" | absolute_url }})

* About 페이지

![부트스트랩이 적용된 About 페이지]({{ "/assets/img/flask_blog_tutorials-chapter-3/bootstrap_about.png" | absolute_url }})

현재까지 작성된 전체 코드는 [Flask blog tutorial Chapter3](https://github.com/LazyRichard/flask_blog_tutorial/tree/Chapter_3)에서 확인할 수 있습니다.
