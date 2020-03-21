---
layout: post
title:  "What I Learnt Today - 2 Lines of Code to Transform Matplotlib Charts"
date:   2020-03-21 08:30:00
categories: update python charting matplotlib seaborn
---
Simply adding 2 lines of code to your notebook will change basic MatplotLib Charts from this:

![Matplotlib Chart](/assets/images/matplotlib.png)

to this:

![Matplotlib Chart](/assets/images/seaborn.png)

And that's done by adding these 2 lines:

{% highlight ruby %}
import seaborn as sns
sns.set()
{% endhighlight %}
