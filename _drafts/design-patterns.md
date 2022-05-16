---
layout: post
title:  Design Patters
date:   2022-05-16 17:53:47 +0300
---


Here some design patters quick description, notes and samples.<br>

### Singleton

props:<br>
 - easy to create and understand
 - handy to use

cons:
 - hard to mock in tests
 - components become tightly bound

{% highlight java %}
class SingletonSample {

  private static volatile SingletonSample instance; // don't forget to add volatile

  private SingletonSample() { // constructor MUST BE private to prevent direct class creation
  }


  public static getInstance() {
    if (instance == null) {
       syncronized(SingletonSample.class) { 
         if (instance == null) {
           instance = new SingletonSample();
         }
       }
    }
    retutn instance;
  }
}
{% endhighlight %}

