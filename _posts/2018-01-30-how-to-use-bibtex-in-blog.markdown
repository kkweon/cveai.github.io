---
layout: post
title: 블로그에서 bibtex 사용하는 법
date: 2018-01-30T09:12:38
author: 권경모
categories: 기타
tags: bibtex tex jekyll scholar
toc: true
---

## Citation 하는 방법


### Bibtex 등록하기
`_bibliography/references.bib` 파일을 작성합니다.

해당 파일을 열어 보면 제가 작성한 파일이 보입니다.

{% highlight bibtex %}
---
---

@Book{sutton,
  Title =        {Reinforcement Learning : An Introduction},
  Annote =       {SIGNATUR = 748.571},
  Author =       {Richard S. Sutton and Andrew G. Barto},
  Keywords =     {NEURAL NETWORKS},
  Publisher =    {MIT Press},
  Year =         2017,
  Url =          {http://incompleteideas.net/book/bookdraft2017nov5.pdf},
  Place =        {Favoritenstrasse 9/4th Floor/1863}
}

@Unpublished{jekyll-scholar,
  author =       {Sylvester Keil},
  title =        {Jekyll-Scholar},
  note =         {Jekyll-Scholar is for all the academic bloggers out there. It
                  is a set of extensions to Jekyll, the awesome, blog aware,
                  static site generator; it formats your bibliographies and
                  reading lists for the web and gives your blog posts citation
                  super-powers. },
  url =          {https://github.com/inukshuk/jekyll-scholar}
}
{% endhighlight %}



### 실제 본문에서 Cite 하기

`sutton` 이라는 키가 등록되어있음으로 앞으로 `{% raw %}{% cite sutton %}{% endraw %}`를 사용해 citation이 가능합니다 {% cite jekyll-scholar %}. 또한, 일부분 페이지(이 예시에서는 pp. 1-2)를 cite 할때는 `{% raw %}{% cite jekyll-scholar -l 1-2 %}{% endraw %}` 를 사용합니다 {% cite jekyll-scholar -l 1-2 %}


응용을 하면 Sutton 께서는 다음과 같이 말했습니다.

> Beyond the agent and the environment, one can identify four main subelements of a reinforcement learning system: a policy, a reward signal, a value function, and, optionally, a model of the environment {% cite sutton -l 5 %}


### 마지막 레퍼런스 추가하기

레퍼런스는 항상 가장 마지막에 와야 합니다.


{% highlight html %}
{% raw %}
## References

{% bibliography --cited %}
{% endraw %}
{% endhighlight %}



## 자세한 정보
[jekyll-scholar](https://github.com/inukshuk/jekyll-scholar)를 읽어보시면 알 수 있습니다. {% cite jekyll-scholar %}

## References

{% bibliography --cited %}
