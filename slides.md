---
theme: ./theme

# https://sli.dev/custom/highlighters.html
highlighter: shiki

# show line numbers in code blocks
lineNumbers: false

# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)

# persist drawings in exports and build
drawings:
  persist: false

# use UnoCSS
css: unocss

layout: intro
---

# Test Driven Development for Everyone

Daniel Raniz Raneland<br />
Coding Architect @ factor10

<ul class="list-none! columns-2">
  <li><mdi-email />raniz@factor10.com</li>
  <li><mdi-mastodon />raniz@mastodon.online</li>

  <li><mdi-firefox />raniz.blog</li>
  <li><mdi-linkedin />/in/raneland</li>
</ul>

---
layout: center
---

# What is Test Driven Development

<h3 v-click>Letting the tests <em>drive</em> the development</h3>

---

# About Raniz

<div class="absolute bottom-0 left-30% mx-auto w-300px">
  <img src="/images/raniz-silhouette.svg" />
</div>

<v-clicks>
  <div speech-bubble pright acenter class="absolute top-400px left-45px w-300px" style="--bbPadding: 0.5rem">
    <img src="/images/Lund_university_L_CMYK.svg" />
  </div>
  <div speech-bubble pbottom aright class="absolute top-240px left-100px">
    <img src="/images/sony-logo.svg" class="h-30px float-left"/><span class="ml-2 text-size-20px">東京</span>
  </div>
  <div speech-bubble pbottom aright class="absolute top-110px left-290px">
    <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" class="w-[120px] h-auto md:w-[118px]" viewBox="0 0 357 179" width="118" height="59"><path fill="currentColor" fill-rule="evenodd" d="M283.7.4 282 3.7a96.6 96.6 0 0 1-14 19.5c-5 5.6-9.5 10.4-17.6 18.5-5 5-11 11.2-13.4 13.8l-4.4 4.7v1.4c0 4 3.5 11.7 5.2 11.7.3 0 .8-.2 1.2-.5a52.6 52.6 0 0 0 13-10l2.2-2c2.7-2.6 2.7-2.6 1 2.5a310.7 310.7 0 0 0-3 9.5 672.4 672.4 0 0 0-9.8 36.2l-.5 2a43 43 0 0 0-.8 4.1 189.4 189.4 0 0 0-4 48.9c.6 4.3 1.2 6.5 3 10.2 3.4 6.7 5.9 5.8 5.9-2 0-8 1-21.3 2.5-31.2l1.7-10.1A384.7 384.7 0 0 1 266 72.2a427.5 427.5 0 0 1 10.2-24.6c1-2.5 5.9-12 7.4-14.8l2-3.7a25.2 25.2 0 0 1 1.6-2.6l.7-1.2c4-5.7 4.6-9.9 2.4-15l-.7-2c-2.3-6.2-4.8-9.5-5.8-7.9ZM321.3 13c-9.7 1.8-20.6 12.9-30.6 31a149.8 149.8 0 0 0-12 29.9 205.8 205.8 0 0 0-4.4 17.5l-.5 2.6a234.6 234.6 0 0 0-2.3 14.3 108.3 108.3 0 0 0 3 38.3c6.7 23.2 20 33.8 35.2 27.9 12.4-5 21-14.8 30.4-35.2a49.2 49.2 0 0 0 1.8-3.8 198.3 198.3 0 0 0 12.5-43 146.3 146.3 0 0 0 1.1-42.1 66 66 0 0 0-2.1-9.5 45 45 0 0 0-9.4-18.5 18.7 18.7 0 0 0-4.6-3.6l-1.8-1.3c-5.7-4.2-10.7-5.6-16.3-4.5Zm13.4 17.4c2.6.6 3.2.8 3.7 1.6.8 1 1 1.2 2.1 1.8 5.2 2.6 6.2 4.4 7 11.4 1.5 16.3-5.4 49.8-14.6 70.3l-1 2a118 118 0 0 1-13.4 23c-2.9 3.9-9 9-13.4 11.2-20.7 10.2-29.8-5-23.4-39a107.3 107.3 0 0 1 1.4-6.8 283.2 283.2 0 0 1 7.2-25.1 174.9 174.9 0 0 1 12.3-27c9.5-16.5 22.2-25.7 32-23.4ZM19.4 55c-7.2 1.4-11.7 7-12.6 15.8-.3 3.1 0 2.8-3.7 3H0v6.8h3.3l3.3.1v39H15v-19.2c0-10.6 0-19.3.2-19.5.1-.2 1.4-.3 4.7-.4h4.5v-6.7l-4.6-.1-4.7-.2c-.6-1 0-5 .9-7.1 1.9-4.2 7.3-6.3 11.2-4.4.5.3 1.1 0 1.1-.4l1.2-3.3c.7-1.6.8-2 .7-2.2a28 28 0 0 0-10.7-1.1Zm105.9 6.5a284.6 284.6 0 0 1-6.2 2.5c-.2.1-.3 1.4-.3 4.8 0 5.3.3 4.9-3 4.9h-2.5v6.4h2.7l2.7.1.1 14.7c.1 9.4.3 15 .4 15.5 2.7 8.6 8.8 11.6 20.1 9.7 4-.7 3.9-.6 3.4-2.9a61 61 0 0 1-.9-4.8c0-.2-.8 0-2.1.4-4.1 1.3-8.4.8-10.2-1.2-2.4-2.6-2.6-4.7-2.5-20V80.3h6.3l6.3-.1v-6.4h-6a77 77 0 0 1-6.3-.2c-.3-.1-.4-.9-.4-6.3 0-4.8 0-6.2-.3-6.1l-1.3.4ZM43.9 73c-4.1.6-9.3 2.5-11.3 4l-.6.5 1.7 3.4c1.2 2.2 1.8 3.3 2 3.2.2 0 1-.7 2-1.3a16.8 16.8 0 0 1 14.8-1.4c2.5 1.2 4 3.6 4.6 7.3.4 2.3.3 2.6-1 2.2-9-2.3-19.4 1.3-24 8.1a14.1 14.1 0 0 0 4 19.8c6 3.5 16.5 2 21.2-3.2.8-.8.8-.8 1.3.3 1.5 3 3.8 4.4 8.4 4.7l2 .2v-4.3l-1-.9a9 9 0 0 1-1.6-2.3l-.6-1.3-.2-11.9c-.2-16.3-.8-19-5-23-3.1-3-11.1-5-16.7-4.1Zm49.5 0a27.8 27.8 0 0 0-9.3 2.4 23 23 0 0 0-4.7 3.6c-10.4 10-9.4 30 2 38 7 4.7 18.3 5 27 .6 2.2-1.1 2.2-1 1-3.5l-1.5-3.2c-.7-1.4-.7-1.5-1.8-.8a17.4 17.4 0 0 1-16 2.7c-12.3-4.3-12.2-27 .1-32 4-1.6 11.5-.7 15 1.8 1 .7 1.2.6 3.3-2.3l2-2.7-1-.7a27.7 27.7 0 0 0-16-4Zm69.2 0c-8 1-13.2 5.3-16.6 13.3a35.6 35.6 0 0 0-.3 20.4c.5 2.2 3 6.5 5.2 8.6a21.5 21.5 0 0 0 28.9-.2c9.2-9.4 8.4-30.6-1.4-38.2a23 23 0 0 0-15.8-4Zm48.4 0c-3.7.7-7.3 3-9.3 6-1 1.6-1.1 1.4-1.1-2.2v-3h-8.3v46h8.3v-14.4c0-16 0-16 1.7-19.3 3-5.9 8.5-7.6 14.3-4.5.2 0 .5-.5 2.2-4.6l1.2-3.3c-.6-.5-7-1-9-.6Zm-42 7.3a9 9 0 0 1 4.2 2.5c5.6 5.8 5.6 21.4 0 27.7a11.2 11.2 0 0 1-18-2c-2.9-5.6-3-16.3-.1-22.1 2.7-5.4 8.4-7.9 13.9-6ZM53.8 96.7c4 .6 3.5-.1 3.5 6.3v5.3l-1.5 1.5c-8.3 8.2-21 4-17.3-5.9 1.9-5 8.8-8.2 15.3-7.2Z" clip-rule="evenodd"></path></svg>
  </div>
  <div speech-bubble pbottom aleft class="absolute top-130px left-520px">
    <span class="text-size-250%">&#x1F470;&#x200D;&#x2640;&#xFE0F; <!-- woman with veil --></span>
    <span class="text-size-175%">
      &#x1F467; <!-- girl -->
      &#x1F466; <!-- boy -->
    </span>
  </div>
  <div speech-bubble pbottom aleft class="absolute top-285px left-590px text-size-250%">
    &#x1F37A;
  </div>
  <div speech-bubble pleft acenter class="absolute bottom-15px right-100px h-80px" style="--bbPadding: 0.2rem">
    <img src="/images/triathlon.png" class="w-full h-full"/>
  </div>

</v-clicks>

---
layout: center
---

# Testing Temperature Check

---
layout: center
---

# TDD Distilled

<ol>
<li v-click>Write a test</li>
<li v-click style="color: red">Make it fail</li>
<li v-click style="color: green">Make it pass</li>
<li v-click>Refactor</li>
<li v-click>Repeat</li>
</ol>

---
layout: center
---

# Why Do Raniz practice TDD?

<div class="absolute left-10px bottom-10px text-center">
  <img src="/images/blog-benefits-of-tdd-qr.png" />
  raniz.blog
</div>

<ul>
<li v-click="1">Testable code leads to looser coupling - i.e. better maintainability</li>
<li v-click="2">Incremental problem solving</li>
<li v-click="3">Principles</li>
<li v-click="4">Tests
  <ul>
    <li v-click="5">Tests are meaningful</li>
    <li v-click="6">More tests => higher quality</li>
    <li v-click="7">Bugs are overlooked tests</li>
    <li v-click="8">Documentation</li>
    <li v-click="9">Confidence when refactoring</li>
  </ul>
</li>
<li v-click="10">Velocity</li>
</ul>

---
layout: center
---

# Some Guiding Principles

<v-clicks>

- Keep It Simple, Stupid
- You Aren't Going to Need It

</v-clicks>

---
layout: center
---

# Keep It Simple Stupid

By letting the tests incrementally drive the implementation it is easy to keep changes minimal between each iteration and therefore keep the code as simple as possible.

<p class="opacity-50%">
The safety-net built up by the tests means we can safely refactor until we are satisfied with the solution.
</p>

---
layout: center
---

# You Aren't Going to Need It

By not making more changes to the code than is necessary to pass all the tests,
we prevent ourselves from thinking ahead and creating complex, adaptable solutions that may never be needed

<p v-click class="opacity-50%"><em>If no test require the code - don't write it!</em></p>


---
transition: fade
---

# Why Do We Fail?


<v-clicks>

```java
class PersonTest {

  @Test
  public void testConstructor() {
    Person person = new Person("John O'Connor");
    assertNotNull(person);
  }
}
```

</v-clicks>
---

# Why Do We Fail?

```python
import unittest
from unittest.mock import MagicMock

def call_method(method, *args):
  method(*args)

class Tests(unittest.TestCase):

  def test_call_method(self):
    # Given a method to call
    mock = MagicMock()

    # when the call_method method is called
    call_method(mock, (1, 2, 3))

    # the mock is called with the expected arguments
    assert mock.called_with(1, 2, 3)

if __name__ == "__main__": 
    unittest.main()
```

---
layout: center
---

# What Should We Test?

<p v-click>Everything should be tested, but everything doesn't need a test case</p>

---

# What Should We Test?

```rust
fn circle_area(radius: f64) -> f64 {
    radius * radius * PI
}
```

---

# What Should We Test?

```rust
fn radius_from_diameter(diameter: f64) -> f64 {
    diameter / 2f64;
}

fn circle_area_diameter(diameter: f64) -> f64 {
    let radius = radius_from_diameter(diameter);
    radius * radius * PI
}
```

---

# What Should We Test?

```rust
fn determinant3(a: f64, b: f64, c: f64, d: f64, e: f64, f: f64, g: f64, h: f64, i: f64) -> f64 {
    a * e * i + b * f * g + c * d * h - a * f * h - b * d * i - c * e * g
}

fn radius_from_points(p1: Point, p2: Point, p3: Point) -> f64 {
    // Calculate the radius given 3 points on a circle
    let d = determinant3(p1.x, p1.y, 1.0,
                         p2.x, p2.y, 1.0,
                         p3.x, p3.y, 1.0);
    let d1 = determinant3(p1.x.powi(2) + p1.y.powi(2), p1.y, 1.0,
                          p2.x.powi(2) + p2.y.powi(2), p2.y, 1.0,
                          p3.x.powi(2) + p3.y.powi(2), p3.y, 1.0);
    let d2 = determinant3(p1.x, p1.x.powi(2) + p1.y.powi(2), 1.0,
                          p2.x, p2.x.powi(2) + p2.y.powi(2), 1.0,
                          p3.x, p3.x.powi(2) + p3.y.powi(2), 1.0);
    if d == 0.0 {
        panic!("The provided points are collinear");
    }
    let cx = -d1 / (2.0 * d);
    let cy = d2 / (2.0 * d);
    ((cx - p1.x).powi(2) + (cy - p1.y).powi(2)).sqrt()
}
```

---
layout: fact
---

# Live Demo

---
layout: fact
---

# Your Turn!

## https://github.com/tdd-starters/

<br/>

## https://raniz85.github.io/tdd-katas/

<!--
Tips:
- Försök tänka produktionskod
- Fuska lite om du inte vet vart du ska börja
-->

---
layout: fact
---

# Intermission

---
layout: center
---

# Intermission

<v-clicks>

- What is hard?
- How many has finished at least 1 part?

</v-clicks>

---
layout: center
---

# TDD For Cheaters

<ol>
<li v-click>Be too excited to remember to write the test first</li>
<li v-click>Write some code</li>
<li v-click>Remember that you should have started with the test</li>
<li v-click><em>Discard (or comment out) your code</em></li>
<li v-click>Write a test</li>
<li v-click style="color: red">Make sure it fails for the right reason</li>
<li v-click style="color: green">Make it pass</li>
<li v-click>Refactor</li>
<li v-click>Repeat (from 5)</li>
</ol>

<!--
Per kallar det Test Driven Uncommenting
-->

---
layout: center
---

# If You Finish Early

- FizzBuzz
- RPN Calculator
- https://sammancoaching.org/kata_descriptions/

---
layout: center
---

# The End...

<ul>
  <li v-click="1">How many finished the kata?</li>
  <li v-click="2">How many have strictly followed the TDD cycle?</li>
  <li v-click="3">What was the hardest?</li>
  <li v-click="4">Will you continue with TDD when you leave the room?
    <ul>
      <li v-click="5">Completely?</li>
      <li v-click="6">Now and then?</li>
    </ul>
  </li>
</ul>

---
layout: statement
---

# Testing is a Craft

<!--
practice makes perfect
-->

---
layout: statement
---

# Testing is Software Development

<!--
Precis som när man startar ett nytt projekt kräver test setup
-->

---
layout: image
image: /images/cost-over-time-1.png
---

<!--
Kostnaden för att lägga till nya features ökar exponentiellt med tiden
-->

---
layout: image
image: /images/cost-over-time-2.png
---

<!--
Med bra testtäckning ökar kostnaden mycket långsammare och mer asymptotiskt
Källa: Kent Beck
-->

---
layout: intro
---

<div class="columns-2">

# Thanks!

Daniel Raniz Raneland<br />
Coding Architect @ factor10

  <ul class="list-none!">
    <li><mdi-email />raniz@factor10.com</li>
    <li><mdi-mastodon />raniz@mastodon.online</li>
    <li><mdi-firefox />raniz.blog</li>
    <li><mdi-linkedin />/in/raneland</li>
  </ul>
  <div class="text-center">
    <img class="mx-auto" src="/images/linkedin-qr.png" />
    LinkedIn
  </div>
</div>
