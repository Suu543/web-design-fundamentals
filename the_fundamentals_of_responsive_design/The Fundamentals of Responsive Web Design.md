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

































