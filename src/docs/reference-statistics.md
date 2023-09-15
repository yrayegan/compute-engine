---
title: Statistics
permalink: /compute-engine/reference/statistics/
layout: single
date: Last Modified
sidebar:
  - nav: 'universal'
toc: true
render_math_in_document: true
---

For the following functions, when the input is a _list_, it can 
take the following forms:
- Multiple arguments, e.g. `["Mean", 1, 2, 3]`
- A list of numbers, e.g. `["Mean", ["List", 1, 2, 3]]`
- A matrix, e.g. `["Mean", ["List", ["List", 1, 2], ["List", 3, 4]]]`
- A range, e.g. `["Mean", ["Range", 1, 10]]`
- A linear space: `["Mean", ["Linspace", 1, 5, 10]]`

## Functions

{% defs "Function" "Description" %}

{% def "Mean" %}

<div class="signature">["<strong>Mean</strong>", <i>list</i>]</div>

Evaluate to the **arithmetic mean** of a list of numbers.

The arithmetic mean is the average of the list of numbers. The mean is
calculated by dividing the sum of the numbers by the number of numbers in the
list.

The formula for the mean of a list of numbers is \\( \bar{x} = \frac{1}{n}
\sum\_{i=1}^n x_i\\), where \\(n\\) is the number of numbers in the list, and
\\(x_i\\) is the \\(i\\)-th number in the list.

```mathjson
["Mean", ["List", 7, 8, 3.1, 12, 77]]
// 21.02
```

{% enddef %}

{% def "Median" %}

<div class="signature">["<strong>Median</strong>", <i>list</i>]</div>

Evaluate to the **median** of a list of numbers.

The median is the value separating the higher half from the lower half of a data
sample. For a list of numbers sorted in ascending order, the median is the
middle value of the list. If the list has an odd number of elements, the median
is the middle element. If the list has an even number of elements, the median is
the average of the two middle elements.

```mathjson
["Median", ["List", 1, 2, 3, 4, 5]]
// 3
```

{% enddef %}

{% def "Mode" %}

<div class="signature">["<strong>Mode</strong>", <i>list</i>]</div>

Evaluate to the **mode** of a list of numbers.

The mode is the value that appears most often in a list of numbers. A list of
numbers can have more than one mode. If there are two modes, the list is called
**bimodal**. For example \\( \lbrack 2, 5, 5, 3, 2\rbrack\\). If there are three
modes, the list is called **trimodal**. If there are more than three modes, the
list is called **multimodal**.

{% enddef %}

{% def "Variance" %}

<div class="signature">["<strong>Variance</strong>", <i>list</i>]</div>

Evaluate to the **variance** of a list of numbers.

The variance is a measure of the amount of variation or dispersion of a set of
values. A low variance indicates that the values tend to be close to the mean of
the set, while a high variance indicates that the values are spread out over a
wider range.

The formula for the variance of a list of numbers is

\\[\frac{1}{n} \sum_{i=1}^n(x_i - \mu)^2\\]

where \\(\mu\\) is the mean of the list.

{% enddef %}

{% def "StandardDeviation" %}

<div class="signature">["<strong>StandardDeviation</strong>", <i>list</i>]</div>

Evaluate to the **standard deviation** of a list of numbers.

The standard deviation is a measure of the amount of variation or dispersion of
a set of values. A low standard deviation indicates that the values tend to be
close to the mean of the set, while a high standard deviation indicates that the
values are spread out over a wider range.

The formula for the standard deviation of a list of numbers is

\\[\sqrt{\frac{1}{n} \sum_{i=1}^n (x_i - \mu)^2}\\]

where \\(\mu\\) is the mean of the list.

{% enddef %}

{% def "Skewness" %}

<div class="signature">["<strong>Skewness</strong>", <i>list</i>]</div>

Evaluate to the **skewness** of a list of numbers.

The skewness is a measure of the asymmetry of the distribution of a real-valued
random variable about its mean. The skewness value can be positive or negative,
or undefined.

The formula for the skewness of a list of numbers is: \\[\frac{1}{n}
\sum_{i=1}^n \left(\frac{x_i - \mu}{\sigma}\right)^3\\]

where \\(\mu\\) is the mean of the list, and \\(\sigma\\) is the standard
deviation of the list.

{% enddef %}

{% def "Kurtosis" %}

<div class="signature">["<strong>Kurtosis</strong>", <i>list</i>]</div>

Evaluate to the **kurtosis** of a list of numbers.

The kurtosis is a measure of the "tailedness" of the distribution of a
real-valued random variable. The kurtosis value can be positive or negative, or
undefined.

The formula for the kurtosis of a list of numbers is

\\[ \frac{1}{n} \sum_{i=1}^n \left(\frac{x_i - \mu}{\sigma}\right)^4\\]

where \\(\mu\\) is the mean of the list, and \\(\sigma\\) is the standard
deviation of the list.

{% enddef %}

{% def "Quantile" %}

<div class="signature">["<strong>Quantile</strong>", <i>list</i>, <i>q:number</i>]</div>


Evaluate to the **quantile** of a list of numbers.

The quantile is a value that divides a list of numbers into equal-sized groups.
The quantile is a generalization of the median, which divides a list of numbers
into two equal-sized groups.

So, \\(\operatorname{median} = \operatorname{quantile}(0.5)\\).

{% enddef %}

{% def "Quartiles" %}

<div class="signature">["<strong>Quartiles</strong>", <i>list</i>]</div>

Evaluate to the **quartiles** of a list of numbers.

The quartiles are the three points that divide a list of numbers into four equal
groups, each group comprising a quarter of the list.

{% enddef %}

{% def "InterquartileRange" %}

<div class="signature">["<strong>InterquartileRange</strong>", <i>list</i>]</div>

Evaluate to the **interquartile range** (IRQ) of a list of numbers.

The interquartile range is the difference between the third quartile and the
first quartile.

{% enddef %}

{% def "Sum" %}

<div class="signature">["<strong>Sum</strong>", <i>list</i>]</div>

Evaluate to the sum of a list of numbers.

{% enddef %}

{% def "Product" %}

<div class="signature">["<strong>Product</strong>", <i>list</i>]</div>

Evaluate to the product of a list of numbers.

{% enddef %}

{% def "Erf" %}

<div class="signature">["<strong>Erf</strong>", <i>z:complex</i>]</div>


Evaluate to the **error function** of a complex number.

The error function is an odd function ( \\( \operatorname{erf} -z = -
\operatorname{erf} z\\) ) that is used in statistics to calculate probabilities
of normally distributed events.

The formula for the error function of a complex number is:

\\[ \operatorname{erf} z = \frac{2}{\sqrt{\pi}} \int_0^z e^{-t^2} dt\\]

where \\(z\\) is a complex number.

{% enddef %}

{% def "Erfc" %}

<div class="signature">["<strong>Erfc</strong>", <i>z:complex</i>]</div>

Evaluate to the **complementary error function** of a complex number.

It is defined as:

\\[ \operatorname{erfc} z = 1 - \operatorname{erf} z \\]

{% enddef %}

{% enddefs %}