## The Fundamentals of Responsive Web Design

**Firefox Dev Tools**

https://stackoverflow.com

### Pixels

Hardware Pixels, Device Independent Pixels (Also: density-independent pixels, dip, dip) , CSS Pixels 

![img](https://cdn-images-1.medium.com/max/1000/1*TfkU19ouc4m53B3M1m3SOw.png)

![img](https://cdn-images-1.medium.com/max/1000/1*-gky_4Zknt-33CJKvouRgg.png)

## Pixels

![img](https://cdn-images-1.medium.com/max/1000/1*gCvBvvs3uYcE-jOICV_3Tw.png)

 웹 사이트를 구성할 때 사용하는 `px` 사이즈에 1.25배가 된 상태로 반영되는 것을 확인할 수 있다.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

`initial-scale = 1.0`을 이용함에 따라, `CSS Pixel`과 `Device Pixel`이 `1 : 1` 비율이 됨을 명시한다.

모바일 기기가 도입되기 전, 컴퓨터 전용 화면으로 웹페이지가 설계되어 정적 디자인과 고정크기의 사진으로 웹 사이트를 디자인했다. 하지만 모바일이 도입된 후 디바이스가 다양해지면서 웹페이지 화면이 해당 디바이스에 알맞게 축소 혹은 확대되어야 하는 문제가 발생했다.

![img](https://media.vlpt.us/images/jayounglee92/post/6c40994d-fc7e-4321-947d-cc604fb8378b/image.png)

컴퓨터 화면으로 보이는 위 웹 사이트를, `viewport`를 적용하지 않은 채로 모바일에 랜더링 하면, 다음과 같은 결과가 출력된다.

![img](https://media.vlpt.us/images/jayounglee92/post/83d1b79d-f689-4831-b6c3-93f66d4530af/image.png)

위의 경우 웹 사이트 본래의 모양을 유지하기 위해서, 마치 `Zoom Out`을 해서, 글자와 사진 크기를 축소하고 웹 사이트와 똑같이 보여줄려고 하는 것 처럼 보이는 것을 확인할 수 있다. 하지만 위와 같이 랜더링 된다면, 글자가 너무 작아 모바일로 해당 웹 사이트를 접속했을 때 어떤 내용인지 파악할 수 없게 된다. 이를 방지하기 위해서 `viewport` meta 태그를 설정하면 다음과 같은 결과가 출력된다.

![img](https://media.vlpt.us/images/jayounglee92/post/153aaa73-7c3f-40fd-9fec-acb0a7e6141b/image.png)

### viewport 설정

`viewport`를 설정할 때는 다음과 같이 `meta` 태그를 작성한다.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

- `width=device-width`: 장치의 화면 너비에 따라 페이지를 설정한다.

- `initial-scale = 1.0`: 페이지가 랜더링 될 때 (로드될 때) `Zoom` 정도를 설정한다.

- 사용자는 데스크톱과 모바일 장치 모두에서 웹 사이트를 세로로 스크롤 하지만, 가로 스크롤은 사용하지 않는다. 이러한 이유를 고려했을 때 다음 세 가지 규칙을 잘 준수해서 웹 사이트를 구성하자!

  - 1. 큰 고정 너비 요소를 사용하지 않기

    - `viewport` 보다 넓은 크기의 사진을 사용하면, 가로로 스크롤이 발생할 수 있기 때문에, 이 내용을 `viewport` 너비에 맞게 잘 조정해야 한다.

  - 2. 내용을 잘 렌더링 하기 위해 특정 `viewport`에 의존하지 않도록 한다.

    - `CSS` 픽셀의 화면 크기와 너비는 장치마다 다르기 때문에, 내용을 잘 렌더링 하기 위해서는 특정 `viewport` 너비에 의존해서는 안 된다.

  - 3. `CSS` 미디어 쿼리를 사용하고 작고 큰 화면에 다른 스타일을  적용해야 한다.

    - 페이지 요소에 `CSS` 너비를 크게 설정하면 요소가 더 작은 장치의 `viewport`에 비해 많이 넓어질 수 있기 때문에 `width: 100%`와 같은 상대 너비 값을 사용하고, `CSS` 요소에 `px`과 같은 절댓값을 주면 작은 장치에서는 요소가 `viewport` 밖으로 벗어날 수 있기 때문에 주의하자!

https://www.paulund.co.uk/understanding-the-viewport-meta-tag

### Max Width & Min Width

https://webkul.github.io/coolhue/

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Max-Width -- Min-Width</title>
    <style>
      .box {
        background-image: linear-gradient(135deg, #abdcff 10%, #0396ff 100%);
		width: 600px;
        height: 300px;
      }
    </style>
  </head>
  <body>
    <div class="box"></div>
  </body>
</html>
```

위 코드에는 아직 `max-width & min-width`를 명시하지 않았다. 이 상태에서 `Responsive Mode`에서 화면 크기를 계속해서 줄여보자.

1. 정의한 `600px` 보다 작은 크기로 만들면, 수평으로 스크롤이 발생한 것을 확인할 수 있다.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Max-Width -- Min-Width</title>
    <style>
      .box {
        background-image: linear-gradient(135deg, #abdcff 10%, #0396ff 100%);
		max-width: 600px;
        height: 300px;
      }
    </style>
  </head>
  <body>
    <div class="box"></div>
  </body>
</html>
```

`max-width`로 `width` 프로퍼티를 변경하면, 수평으로 스크롤이 발생하지 않고, `width` 길이가 동적으로 줄어드는 것을 확인할 수 있다.

1. `max-width` 프로퍼티를 정의하게되면, `max-width`에 정의한 값을 넘어가지 않는다면, `box`는 어떤 값이든 다 될 수 있다 `(Below min-width)`.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Max-Width -- Min-Width</title>
    <style>
      .box {
        background-image: linear-gradient(135deg, #abdcff 10%, #0396ff 100%);
		min-width: 600px;
        height: 300px;
      }
    </style>
  </head>
  <body>
    <div class="box"></div>
  </body>
</html>
```

`min-width`로 `width` 프로퍼티를 변경하면, 똑같이 수평으로 스크롤이 발생하지 않는다 (`width`가 `min-width` 크기보다 작아지지 않는 한), `width` 길이가 동적으로 늘어나는 것을 확인할 수 있다.

1. `min-width` 프로퍼티를 정의하게 되면, `min-width`에 정의한 값보다 작지 않다면, `box`는 어떤 값이든 다 될 수 있다 `(Above min-width)`.
2. `min-width` 프로퍼티를 정의하게 되면, `min-width`에 정의한 값보다 작아진다면, 수평으로 스크롤이 발생한다.

`min-width or max-width`는 반응형 사이트를 만드는 데 사용하는 `media queries`에 자주 사용되기 때문에 잘 학습해두자!

### Viewport Units

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Viewport Units</title>
    <style>
        img {
            width: 50vw;
            height: 50vh;
        }
    </style>
  </head>
  <body>
    <!-- <img src="kitty cat.jpg" alt="cat" /> -->
    <img src="ducklings.jpg" alt="duck" />
  </body>
</html>

```

`img` 태그의 `width`를 `50vw`로 정의하고 개발자 도구의 반응형 탭을 확인하면, 사진의 크기가 눈에 보이는 화면의 가로 절반으로 잡혀있는 것을 확인할 수 있다.

`img`태그의 `height`를 `50vw`로 정의하고 개발자 도구의 반응형 탭을 확인하면, 사진의 크기가 눈에 보이는 화면의 세로 절반으로 잡혀있는 것을 확인할 수 있다.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Viewport Units</title>
    <style>
        img {
            width: 50vw;
            height: 50vh;
            /* contain */
            object-fit: cover;
            border: lightslategray solid 0.2rem;
        }
    </style>
  </head>
  <body>
    <!-- <img src="kitty cat.jpg" alt="cat" /> -->
    <img src="ducklings.jpg" alt="duck" />
  </body>
</html>
```

`object-fit: contain`을 테스트 할 때는 꼭 `border` 속성을 주고 테스트하자!

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Viewport Units</title>
    <style>
        img {
            width: 50vw;
            height: 50vh;
            /* contain */
            object-fit: cover;
            border: lightslategray solid 0.2rem;
        }
        
        img:last-of-type {
            width: 50vmin;
            /* width: 50vmax; */
        }
    </style>
  </head>
  <body>
    <img src="kitty cat.jpg" alt="cat" />
    <img src="ducklings.jpg" alt="duck" />
  </body>
</html>
```

`vmin`은 `width or height` 중 작은 크기의  `50%`의 크기를 갖는다.

`vmax`는 `width or height`중 큰 크기의 `50%`의 크기를 갖는다

`width: 900px`이고 `height: 600px`일 때,

-  `vmin`을 사용하면 둘 중 크기가 작은 `height: 600px`의 `50%`를 기준으로 잡는다. 

- `vmax`를 사용하면 둘 중 크기가 큰 `width: 900px`의 `50%`를 기준으로 잡는다. 

반응형 도구를 통해 크기를 줄일 때 `width`와 `height` 크기의 전환이 발생할 수 있다. 그 이유는 기준점이 달라질 수 있기 때문이다.

### Introduction to Media Queries

수많은 크기가 다른 장치가 존재한다. 그렇기 때문에 웹 사이트를 구현할 때도 이 모든 장치의 크기를 고려한 디자인을 해야 한다. 이런 고려를 `HTML & CSS`에서는 반응형 웹이라 칭한다. `Media Queries`는 이런 반응형 웹을 구현할 때 유용하게 사용할 수 있는 프로퍼티다.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" media="screen and (min-width: 400px)" href="over400.css" />
    <title>Introduction to Media Queries</title>
  </head>
  <body>
  </body>
</html>
```

첫번째 `media query` 적용 방법

```css
/* over400.css */
body {
	background-color: brown;
}
```

두번째 `media query` 적용 방법

```css
/* over400.css */
@media screen and (max-width: 400px) {
    body {
        background-color: olivedrab;
    }
}
```

### Media Queries Challenges

1. From `0 to 400px`, set the background color to lawn green
2. From `401 to 599px`, set the background color to blue violet
3. From `600 to wider` set the background color to dark red 

`You can use either min-width or max-width`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="./media.css" />
    <title>Document</title>
  </head>
  <body></body>
</html>

```

```css
/* 0 to 400px */
@media screen and (max-width: 400px) {
    body {
        background-color: lawngreen;
    }
}

/* 401px to 599px */
@media screen and (min-width: 401px) {
    body {
        background-color: blueviolet;
    }
}

/* 600px ~ Wider */
@media screen and (min-width: 600px) {
    body {
        background-color: darkred;
    }
}
```

### Weather App UI Part-1

https://fontawesome.com/

1. Get Font Awesome kit from Email
2. Set Font Awesome Account
3. Get Font Awesome Script

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <script
      src="https://kit.fontawesome.com/a3605d0287.js"
      crossorigin="anonymous"
    ></script>
    <link rel="stylesheet" href="./media.css" />
    <title>Media Queries - Weather UI</title>
  </head>
  <body>
    <section id="weather">
      <h1>Sydney, Australia</h1>
      <div class="weather__info__temp">
        <!-- Weather Information -->
        <div class="weather__info">
          <div class="weather__info--date">
            <p>Thursday</p>
            <p>Sunny</p>
            <div class="weather__info--date__icon__temp">
              <i class="fas fa-sun"></i>
              <p>24 <sup>&#8451;</sup></p>
            </div>
          </div>
          <div class="weather__info--data">
            <p>Percipitation: 10%</p>
            <p>Humidity: 5%</p>
            <p>Wind: 4 kpm NW</p>
          </div>
        </div>
      </div>
    </section>
  </body>
</html>
```

```css
/* Reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/******************* Utility Components *******************/
:root {
  font-size: 62.5%;
}

body {
  background-color: #0f9b8e;
  color: white;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}

/* Paragraphs */
p {
  font-size: 1.5rem;
  margin: 0.5rem 0;
}

/* Icons */
i {
  font-size: 5rem;
}

/* Superscript Elements */
sup {
  font-size: 0.8rem;
}

::selection {
  color: #fcc006;
  background-color: #ff7052;
}

/******************* Main Styling *******************/
/* Section ==> Container of them all */
/* No need to add whitespace cause it's not its child  */
section#weather {
  margin: 2rem auto 0;
}

/* Main Heading */
h1 {
  text-align: center;
  font-size: 6rem;
  letter-spacing: 0.4rem;
  font-weight: 300;
}

/* Weather Info -- Temp Container */
div.weather__info__temp {
  padding: 4rem;
}

/* Weather Info */
div.weather__info {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  margin: 5rem 0;
}
```

### Weather App UI Part-2

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <script
      src="https://kit.fontawesome.com/fbadad80a0.js"
      crossorigin="anonymous"
    ></script>
    <link rel="stylesheet" href="./media.css" />

    <title>Media Queries Part -2: Weather App UI</title>
  </head>
  <body>
    <section id="weather">
      <h1>Sydney, Australia</h1>
      <div class="weather__info__temp">
        <!-- Weather Information -->
        <div class="weather__info">
          <div class="weather__info--date">
            <p>Thursday, Apr 30</p>
            <p>Sunny</p>
            <div class="weather__info--date__icon__temp">
              <i class="fas fa-sun"></i>
              <!-- <p>24 <sup>&#8457;</sup></p> -->
              <p>24 <sup>&#8451;</sup></p>
            </div>
          </div>
          <div class="weather__info--data">
            <p>Percipitation: 10%</p>
            <p>Humidity: 5%</p>
            <p>Wind: 4 kpm NW</p>
          </div>
        </div>

        <!-- Weather Temps -->
        <div class="weather__temp">
          <div class="weather__temp--monday">
            <p>Monday</p>
            <i class="fas fa-cloud-sun"></i>
            <p>23 <sup>&#8451;</sup></p>
            <p>18 <sup>&#8451;</sup></p>
          </div>
          <div class="weather__temp--tuesday">
            <p>Tuesday</p>
            <i class="fas fa-sun"></i>
            <p>26 <sup>&#8451;</sup></p>
            <p>21 <sup>&#8451;</sup></p>
          </div>
          <div class="weather__temp--wednesday">
            <p>Wednesday</p>
            <i class="fas fa-wind"></i>
            <p>20 <sup>&#8451;</sup></p>
            <p>16 <sup>&#8451;</sup></p>
          </div>
          <div class="weather__temp--thursday">
            <p>Thursday</p>
            <i class="fas fa-cloud-sun-rain"></i>
            <p>18 <sup>&#8451;</sup></p>
            <p>16 <sup>&#8451;</sup></p>
          </div>
          <div class="weather__temp--friday">
            <p>Friday</p>
            <i class="fas fa-cloud-showers-heavy"></i>
            <p>15 <sup>&#8451;</sup></p>
            <p>11 <sup>&#8451;</sup></p>
          </div>
          <div class="weather__temp--saturday">
            <p>Saturday</p>
            <i class="fas fa-cloud-sun"></i>
            <p>14 <sup>&#8451;</sup></p>
            <p>10 <sup>&#8451;</sup></p>
          </div>
          <div class="weather__temp--sunday">
            <p>Sunday</p>
            <i class="fas fa-cloud-meatball"></i>
            <p>23 <sup>&#8451;</sup></p>
            <p>18 <sup>&#8451;</sup></p>
          </div>
        </div>
      </div>
    </section>
  </body>
</html>
```

```css
/* media.css */
/* Reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/******************* Utility Components *******************/
:root {
  font-size: 62.5%;
}

body {
  background-color: #0f9b8e;
  color: white;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}

/* Paragraphs */
p {
  font-size: 1.5rem;
  margin: 0.5rem 0;
}

/* Icons */
i {
  font-size: 5rem;
}

/* Superscript Elements */
sup {
  font-size: 0.8rem;
}

::selection {
  color: #fcc006;
  background-color: #ff7052;
}

/******************* Main Styling *******************/
/* Section ==> Container of them all */
/* No need to add whitespace cause it's not its child  */
section#weather {
  margin: 2rem auto 0;
}

/* Main Heading */
h1 {
  text-align: center;
  font-size: 6rem;
  letter-spacing: 0.4rem;
  font-weight: 300;
}

/* Weather Info -- Temp Container */
div.weather__info__temp {
  padding: 4rem;
}

/* Weather Info */
div.weather__info {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  margin: 5rem 0;
}

/* Weather Temp Container */
div.weather__temp {
  display: flex;
  justify-content: space-evenly;
}

/* You can also put media queries here */
```

### Weather App UI Part-3

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <script
      src="https://kit.fontawesome.com/fbadad80a0.js"
      crossorigin="anonymous"
    ></script>
    <link rel="stylesheet" href="./media.css" />

    <!-- 500px or smaller -->

    <link
      rel="stylesheet"
      media="screen and (max-width:500px)"
      href="z500px.css"
    />

    <!-- 600px or smaller -->

    <link
      rel="stylesheet"
      media="screen and (max-width:600px)"
      href="z600px.css"
    />

    <!-- 800px or smaller -->

    <link
      rel="stylesheet"
      media="screen and (max-width:800px)"
      href="z800px.css"
    />

    <!-- 900px or wider -->

    <link
      rel="stylesheet"
      media="screen and (min-width:900px)"
      href="z900px.css"
    />

    <title>Media Queries Part -2: Weather App UI</title>
  </head>
  <body>
    <section id="weather">
      <h1>Sydney, Australia</h1>
      <div class="weather__info__temp">
        <!-- Weather Information -->
        <div class="weather__info">
          <div class="weather__info--date">
            <p>Thursday, Apr 30</p>
            <p>Sunny</p>
            <div class="weather__info--date__icon__temp">
              <i class="fas fa-sun"></i>
              <!-- <p>24 <sup>&#8457;</sup></p> -->
              <p>24 <sup>&#8451;</sup></p>
            </div>
          </div>
          <div class="weather__info--data">
            <p>Percipitation: 10%</p>
            <p>Humidity: 5%</p>
            <p>Wind: 4 kpm NW</p>
          </div>
        </div>

        <!-- Weather Temps -->
        <div class="weather__temp">
          <div class="weather__temp--monday">
            <p>Monday</p>
            <i class="fas fa-cloud-sun"></i>
            <p>23 <sup>&#8451;</sup></p>
            <p>18 <sup>&#8451;</sup></p>
          </div>
          <div class="weather__temp--tuesday">
            <p>Tuesday</p>
            <i class="fas fa-sun"></i>
            <p>26 <sup>&#8451;</sup></p>
            <p>21 <sup>&#8451;</sup></p>
          </div>
          <div class="weather__temp--wednesday">
            <p>Wednesday</p>
            <i class="fas fa-wind"></i>
            <p>20 <sup>&#8451;</sup></p>
            <p>16 <sup>&#8451;</sup></p>
          </div>
          <div class="weather__temp--thursday">
            <p>Thursday</p>
            <i class="fas fa-cloud-sun-rain"></i>
            <p>18 <sup>&#8451;</sup></p>
            <p>16 <sup>&#8451;</sup></p>
          </div>
          <div class="weather__temp--friday">
            <p>Friday</p>
            <i class="fas fa-cloud-showers-heavy"></i>
            <p>15 <sup>&#8451;</sup></p>
            <p>11 <sup>&#8451;</sup></p>
          </div>
          <div class="weather__temp--saturday">
            <p>Saturday</p>
            <i class="fas fa-cloud-sun"></i>
            <p>14 <sup>&#8451;</sup></p>
            <p>10 <sup>&#8451;</sup></p>
          </div>
          <div class="weather__temp--sunday">
            <p>Sunday</p>
            <i class="fas fa-cloud-meatball"></i>
            <p>23 <sup>&#8451;</sup></p>
            <p>18 <sup>&#8451;</sup></p>
          </div>
        </div>
      </div>
    </section>
  </body>
</html>
```

```css
/* z900px.css */
section#weather {
	width: 90rem;
}
```

```css
/* z800px.css */
/* Weather Temp Container */
div.weather__temp {
	flex-direction: column;
}

/* Day Containers */
/* Immediate Children */
div.weather__temp > div {
	display: flex;
    justify-content: space-evenly;
    margin-bottom: 2rem;
}
```

```css
/* z.600px.css */
/* Main Heading */
h1 {
    padding: 0 2rem;
    font-size: 4rem;
    font-weight: 600;
}
```

```css
/* z.500px.css */
/* Weather Info -- Temp Container */
div.weather__info__temp {
    padding: 1rem;
}

/* Weather Info */
div.weather__info {
	font-size: 0.7rem;
    align-items: flex-end;
}

/* Main Heading */
h1 {
    font-size: 3rem !important;
    padding: 0 1rem;
}

/* Icon */
i {
    font-size: 2.5rem;
}
```

`!important` 

기존에 학습한 모든 `CSS Specificity`를 무시하고, `!important`를 선언한 속성에 가장 먼저 우선순위를 부여한다. 꼭 필요한 경우가 아니라면 되도록 사용하지 않는 것이 좋다. 그 이유는 `!important`는 스타일의 자연스러운 흐름을 방해하고, 간혹 까먹었을 때 문제 원인을 찾기가 쉽지 않다.

## Viewport Units Use Cases Part-1 - Font Size

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Font Size</title>
    <style>
      /* :root => html => replace px with rem */
      :root {
        font-size: 62.5%;
      }

      h1 {
        text-align: center;
        font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
        /* Dynamically Calculated */
        font-size: 3vw;

        /* Barebone Value is 14px - For Smaller Screen Sizes */
        font-size: calc(14px + 2vw);
        font-size: calc(1.4rem + 2vw);
      }

      /* For Larger Screen Sizes */
      @media screen and (min-width: 1500px) {
        h1 {
          font-size: 4.5rem;
        }
      }
    </style>
  </head>
  <body>
    <h1>Hello World</h1>
  </body>
</html>
```

## Viewport Units Use Cases Part-2 - Full Screen Sections

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Full Screen Section</title>
    <style>
      *,
      *::before,
      *::after {
        padding: 0;
        margin: 0;
      }

      body {
        font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
      }

      section {
        background-color: indigo;
        color: white;

        /* Full Screen */
        height: 100vh;

        /* Optional Styles */
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
      }

      /* Optional Styles */
      h1 {
        margin-bottom: 40px;
        font-size: 68px;
        font-weight: 300;
        letter-spacing: 4px;
      }

      p {
        font-size: 18px;
      }

      a {
        color: white;
        text-decoration: none;
        border: 1px solid white;
        border-radius: 5px;
        padding: 12px 24px;

        transition: all 0.35s ease-in-out;
      }

      a:hover {
        color: indigo;
        background-color: white;
      }
    </style>
  </head>
  <body>
    <section>
      <h1>Full Screen and Viewport Units</h1>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Placeat nemo
        tempore ratione quibusdam recusandae, commodi vel hic magnam. Provident
        quidem necessitatibus nesciunt cum. Impedit, doloribus! Voluptate sunt
        voluptatem molestias temporibus?
      </p>
      <a href="#">Sign Up</a>
    </section>
  </body>
</html>
```

## Viewport Units Use Cases Part-3 - Sticky Footer

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Viewport Units Use Cases Part - 3: Sticky Footer</title>
    <style>
      :root {
        font-size: 62.5%;
      }

      header {
        background-color: lightsteelblue;
        height: 7.5rem;
      }

      section {
        background-color: lightskyblue;
        /* Comment Out for the second solution to be visualized */
        height: 30rem;
      }

      footer {
        background-color: lightseagreen;
        height: 8.5rem;
      }

      header,
      section,
      footer {
        display: flex;
        justify-content: center;
        align-items: center;

        font-size: 2.5rem;
        color: white;
      }

      /* First Solution */
      section {
        height: calc(100vh - 7.5rem - 8.5rem);
      }

      /* Optional */
      * {
        padding: 0;
        margin: 0;
      }

      /* Second Solution ==> Recommended */
      body {
        min-height: 100vh;
        display: flex;
        flex-direction: column;
      }

      section {
        /* This will make the main element take the remaining space dynamically */
        flex-grow: 1;
      }
    </style>
  </head>
  <body>
    <header>Header</header>
    <section>Section</section>
    <footer>Footer</footer>
  </body>
</html>
```

## Viewport Units Use Cases Part - 4 - Margins & Paddings

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Viewport Units Use Cases Part - 4: Margins + Paddings</title>
    <style>
      header {
        font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
        height: 40vh;
        background-color: lightsalmon;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        /* padding: 80px; */
        /* padding: 10vh 5vw; */
        padding: calc(4px + 2vh) calc(4px + 2vw);
      }

      p {
        margin-bottom: 3vh;
      }
    </style>
  </head>
  <body>
    <header>
      <h1>Fitness Matters</h1>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Alias
        laboriosam incidunt debitis voluptatem pariatur labore ea corrupti non
        provident cupiditate molestiae, necessitatibus dolorum magni officia
        commodi, id, eligendi harum. Suscipit?
      </p>
    </header>
  </body>
</html>
```

## Viewport Units Use Cases Part - 5 -  The Top Border

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Viewport Units Use Cases Part - 5: The Top Border</title>
    <style>
      header {
        background-color: rgb(227, 232, 238);
        padding: 5vh 5vw;

        /* Top Border */
        border-top: 5px solid lightslategray;

        /* Making the border responsive ==> vw ==> [(Pixel value / Viewport Width) * 100] */
        /* 5px / 1500 * 100 = 0.3333*/
        border-top: 0.3333vw solid lightslategray;

        /* Taking it one step further ==> to make sure it does not get very small on mobile device */
        /* 2.8 / 1500 * 100 = 0.186 */
        border-top: calc(2px + 0.186vw) solid lightslategray;
      }

      a {
        text-decoration: none;
        color: #444;
        margin: 0 2vw;
      }
    </style>
  </head>
  <body>
    <header>
      <nav>
        <a href="#">Link 1</a>
        <a href="#">Link 2</a>
        <a href="#">Link 3</a>
        <a href="#">Link 4</a>
        <a href="#">Link 5</a>
      </nav>
    </header>
  </body>
</html>
```



























