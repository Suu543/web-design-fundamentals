# The Fundamentals of UI Design

1. The White Space UI Design Fundamental
2. The Alignment UI Design Fundamental
3. UI Design Fundamentals Challenge 1
4. The Contrast & Scale UI Design Fundamentals
5. The Typography UI Design Fundamentals
6. The Color UI Design Fundamental
7. UI Design Fundamentals Challenge 2
8. The Visual Hierarchy UI Design Fundamental
9. UI Design Fundamentals Final Challenge

## 1. The White Space UI Design Fundamental

`White Space`는 요소 사이에 이용할 수 있는 공간을 의미한다.

`Heading`, `Title`, and `Paragraph`으로 구성된 세 개의 카드가 있다.

![img](https://cdn-images-1.medium.com/max/1000/1*ItLQcFBe3Az04tEaTpa5ng.png)

위 카드 디자인의 문제점은, 카드 내부의 요소에 간격이 존재하지 않는 점이다.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
	<style>
        /* Reset => Universal Selector */
        * {
          margin: 0;
          padding: 0;
        }

        body {
          font-family: Arial, Helvetica, sans-serif;
        }

        /* Sports */
        #sports {
          background-color: #f8f8f8;

          display: flex;

          justify-content: space-evenly; /* main axis */
          align-items: center; /* cross axis */
        }

        /* Shared styles for sections */
        .sport {
          width: 320px;
          background-image: linear-gradient(135deg, #90f7ec 10%, #32ccbc 100%);
        }
    </style>
    <title>White Space</title>
  </head>
  <body>
    <main id="sports">
      <!-- Football -->
      <section class="sport football">
        <h2>Football</h2>
        <p>
          This is an important text about football Lorem ipsum, dolor sit amet
          consectetur adipisicing elit. Vitae porro in pariatur possimus
          dolores, incidunt architecto laudantium soluta sunt sint maxime
          delectus recusandae suscipit, labore velit unde quaerat assumenda
          tempora?
        </p>
      </section>

      <!-- basketball -->
      <section class="sport basketball">
        <h2>Basketball</h2>
        <p>
          This is an important text about basketball Lorem ipsum, dolor sit amet
          consectetur adipisicing elit. Vitae porro in pariatur possimus
          dolores, incidunt architecto laudantium soluta sunt sint maxime
          delectus recusandae suscipit, labore velit unde quaerat assumenda
          tempora?
        </p>
      </section>

      <!-- Golf -->
      <section class="sport golf">
        <h2>Golf</h2>
        <p>
          This is an important text about golf Lorem ipsum, dolor sit amet
          consectetur adipisicing elit. Vitae porro in pariatur possimus
          dolores, incidunt architecto laudantium soluta sunt sint maxime
          delectus recusandae suscipit, labore velit unde quaerat assumenda
          tempora?
        </p>
      </section>
    </main>
  </body>
</html>
```

### Improvements

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
	<style>
        /* Reset => Universal Selector */
        * {
          margin: 0;
          padding: 0;
        }

        body {
          font-family: Arial, Helvetica, sans-serif;
        }

        /* Sports */
        #sports {
          background-color: #f8f8f8;

          display: flex;

          justify-content: space-evenly; /* main axis */
          align-items: center; /* cross axis */
        }

        /* Shared styles for sections */
        .sport {
          width: 320px;
          background-image: linear-gradient(135deg, #90f7ec 10%, #32ccbc 100%);
        }

        /* Improvements */
        #sports {
          padding: 35px;
        }

        .basketball {
          padding: 27px;
        }

        .basketball h2 {
          margin-bottom: 10px;
        }

        .basketball p {
          line-height: 1.6;
          /* line-height: 25px; */
        }  
        
        /* Improvements */
        #sports {
            padding: 35px;
        }
        
        .basketball {
        	padding: 35px;
        }
        
        .basketball h2 {
            margin-bottom: 10px;
        }
        
        .basketball p {
            /* line-height: 25px; */
            line-height: 1.6;
        }
        
    </style>
    <title>White Space</title>
  </head>
  <body>
    <main id="sports">
      <!-- Football -->
      <section class="sport football">
        <h2>Football</h2>
        <p>
          This is an important text about football Lorem ipsum, dolor sit amet
          consectetur adipisicing elit. Vitae porro in pariatur possimus
          dolores, incidunt architecto laudantium soluta sunt sint maxime
          delectus recusandae suscipit, labore velit unde quaerat assumenda
          tempora?
        </p>
      </section>

      <!-- basketball -->
      <section class="sport basketball">
        <h2>Basketball</h2>
        <p>
          This is an important text about basketball Lorem ipsum, dolor sit amet
          consectetur adipisicing elit. Vitae porro in pariatur possimus
          dolores, incidunt architecto laudantium soluta sunt sint maxime
          delectus recusandae suscipit, labore velit unde quaerat assumenda
          tempora?
        </p>
      </section>

      <!-- Golf -->
      <section class="sport golf">
        <h2>Golf</h2>
        <p>
          This is an important text about golf Lorem ipsum, dolor sit amet
          consectetur adipisicing elit. Vitae porro in pariatur possimus
          dolores, incidunt architecto laudantium soluta sunt sint maxime
          delectus recusandae suscipit, labore velit unde quaerat assumenda
          tempora?
        </p>
      </section>
    </main>
  </body>
</html>
```

## 2. The Alignment UI Design Fundamental

![img](https://cdn-images-1.medium.com/max/1000/1*SaHBFatBAuxBjqGA6y3VFg.png)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <style>
        /* Reset */
        * {
          margin: 0;
          padding: 0;
        }

        body {
          font-family: Arial, Helvetica, sans-serif;
          background-color: #444e5c;
          border-left: 17px solid rgba(0, 0, 0, 0.2);
          height: 100vh;
          padding: 30px;
        }

        /* Main Styling */

        /* Container */
        .container {
          width: 80%;
          margin: 0 auto;
        }

        /* Links */
        a {
          color: white;
          text-decoration: none;
        }

        /* Logo */
        a.logo {
          display: block;
          padding-top: 16px;
          font-weight: bold;
          text-transform: uppercase;
          font-size: 12px;
        }

        /* Heading */
        h1 {
          margin: 64px 0 30px 30px;
          color: white;
        }

        /* Paragraph */
        p {
          color: #b2cef2;
          line-height: 20px;
          font-size: 16px;
        }

        /* CTA => (Call TO Action) Button */
        a.cta {
          display: inline-block;
          background: #5099ff;
          padding: 14px 28px;
          font-weight: bold;
          border-radius: 30px;
          transform: translateX(50%);
          margin-top: 32px;
        }

        /* Show Column: */

        .container {
          border-left: 1px solid rgba(255, 255, 255, 0);
        }
    </style>
    <title>Alignment</title>
  </head>
  <body>
    <header class="container">
      <a href="#" class="logo">Company Logo</a>

      <h1>Some Heading</h1>

      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua.
      </p>

      <a href="#" class="cta">Sign Up</a>
    </header>
  </body>
</html>
```

![img](https://cdn-images-1.medium.com/max/1000/1*lYkLf9EV2kfcSgtcyyCUJA.png)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <style>
        /* Reset */
        * {
          margin: 0;
          padding: 0;
        }

        body {
          font-family: Arial, Helvetica, sans-serif;
          background-color: #444e5c;
          border-left: 17px solid rgba(0, 0, 0, 0.2);
          height: 100vh;
          padding: 30px;
        }

        /* Main Styling */

        /* Container */
        .container {
          width: 80%;
          margin: 0 auto;
        }

        /* Links */
        a {
          color: white;
          text-decoration: none;
        }

        /* Logo */
        a.logo {
          display: block;
          padding-top: 16px;
          font-weight: bold;
          text-transform: uppercase;
          font-size: 12px;
        }

        /* Heading */
        h1 {
          margin: 64px 0 30px 30px;
          color: white;
        }

        /* Paragraph */
        p {
          color: #b2cef2;
          line-height: 20px;
          font-size: 16px;
        }

        /* CTA => (Call TO Action) Button */
        a.cta {
          display: inline-block;
          background: #5099ff;
          padding: 14px 28px;
          font-weight: bold;
          border-radius: 30px;
          transform: translateX(50%);
          margin-top: 32px;
        }

        /* Show Column: */
        /* Improvements */
       
        /* Show Vertical Line */
        .container {
			border-left: 1px solid rgb(255, 255, 255, 0);
        }
        
        h1 {
            margin-left: 0;
        }
        
        a.cta {
            transform: none;
        }
    </style>
    <title>Alignment</title>
  </head>
  <body>
    <header class="container">
      <a href="#" class="logo">Company Logo</a>

      <h1>Some Heading</h1>

      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua.
      </p>

      <a href="#" class="cta">Sign Up</a>
    </header>
  </body>
</html>
```

## UI Design Fundamentals Challenge 1

![img](https://cdn-images-1.medium.com/max/1000/1*of4b_MqmW4Tvks8kUO3iuQ.png)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <style>
        * {
          margin: 0;
          padding: 0;
        }

        body {
          font-family: Arial, Helvetica, sans-serif;
          background-color: rgb(255, 252, 222);
          height: 100vh;

          /* Initiating The Flexbox Model */
          display: flex;

          justify-content: center;
          align-items: center;
        }

        /* Shared Styles for Sections */
        .section {
          width: 400px;

          background-color: rgb(166, 248, 159);
        }

        /* imges */
        img {
          width: 400px;
          height: 400px;
          object-fit: cover;
        }

        /* Date */
        .section .content p:first-of-type {
          text-align: center;
        }

        /* headline */
        .section .content h3 {
          text-align: right;
        }

        /* Improvements */  
    </style>
    <title>Challenge 1 - Solution - White Space & Alignment</title>
  </head>
  <body>
    <!-- section*3.section.section-$>img+div.content>p{Nov 10, 2100}+h3{Some Headline}+p{Some Content} -->

    <!-- About Dog -->
    <section class="section section-1">
      <img src="/challenge-1-img/1 (5).jpg" alt="Dog" />
      <div class="content">
        <p>Nov 10, 2100</p>
        <h3>Dog</h3>
        <p>
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Impedit
          reiciendis, dolorem magnam ad tenetur quod eum aut beatae labore
          repudiandae quia atque voluptatem ab enim error praesentium? Omnis,
          nostrum aliquam.
        </p>
      </div>
    </section>

    <!-- About Moose -->
    <section class="section section-2">
      <img src="/challenge-1-img/1 (13).jpg" alt="Moose" />
      <div class="content">
        <p>Nov 10, 2100</p>
        <h3>Moose</h3>
        <p>
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Impedit
          reiciendis, dolorem magnam ad tenetur quod eum aut beatae labore
          repudiandae quia atque voluptatem ab enim error praesentium? Omnis,
          nostrum aliquam.
        </p>
      </div>
    </section>

    <!-- About Owl -->
    <section class="section section-3">
      <img src="/challenge-1-img/1 (15).jpg" alt="Owl" />
      <div class="content">
        <p>Nov 10, 2100</p>
        <h3>Owl</h3>
        <p>
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Impedit
          reiciendis, dolorem magnam ad tenetur quod eum aut beatae labore
          repudiandae quia atque voluptatem ab enim error praesentium? Omnis,
          nostrum aliquam.
        </p>
      </div>
    </section>
  </body>
</html>
```

Div - Acting like one element



### Improved Output

![img](https://cdn-images-1.medium.com/max/1000/1*8imJ1TKrlPtav8L6saj2eQ.png)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <style>
        * {
          margin: 0;
          padding: 0;
        }

        body {
          font-family: Arial, Helvetica, sans-serif;
          background-color: rgb(255, 252, 222);
          height: 100vh;

          /* Initiating The Flexbox Model */
          display: flex;

          justify-content: center;
          align-items: center;
        }

        /* Shared Styles for Sections */
        .section {
          width: 400px;

          background-color: rgb(166, 248, 159);
        }

        /* imges */
        img {
          width: 400px;
          height: 400px;
          object-fit: cover;
        }

        /* Date */
        .section .content p:first-of-type {
          text-align: center;
        }

        /* headline */
        .section .content h3 {
          text-align: right;
        }

        /* Improvements */  
        .section {
          margin: 0 15px 0;
        }

        .section .content p:first-of-type,
        .section .content h3,
        .section .content p:last-of-type {
          text-align: left;
          margin-top: 15px;
          margin-left: 25px;
        }

        .section .content p:last-of-type {
          margin-bottom: 20px;
          margin-right: 20px;
          line-height: 1.6;
        }
    </style>
    <title>Challenge 1</title>
  </head>
  <body>
    <!-- section*3.section.section-$>img+div.content>p{Nov 10, 2100}+h3{Some Headline}+p{Some Content} -->

    <!-- About Dog -->
    <section class="section section-1">
      <img src="https://cdn-images-1.medium.com/max/1000/1*q8OtHQOW_CULEXcxFVgNUQ.jpeg" alt="Dog" />
      <div class="content">
        <p>Nov 10, 2100</p>
        <h3>Dog</h3>
        <p>
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Impedit
          reiciendis, dolorem magnam ad tenetur quod eum aut beatae labore
          repudiandae quia atque voluptatem ab enim error praesentium? Omnis,
          nostrum aliquam.
        </p>
      </div>
    </section>

    <!-- About Moose -->
    <section class="section section-2">
      <img src="https://cdn-images-1.medium.com/max/1000/1*WJNy-rCdTNVaRcE-KLIPLg.jpeg" alt="Moose" />
      <div class="content">
        <p>Nov 10, 2100</p>
        <h3>Moose</h3>
        <p>
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Impedit
          reiciendis, dolorem magnam ad tenetur quod eum aut beatae labore
          repudiandae quia atque voluptatem ab enim error praesentium? Omnis,
          nostrum aliquam.
        </p>
      </div>
    </section>

    <!-- About Owl -->
    <section class="section section-3">
      <img src="https://cdn-images-1.medium.com/max/1000/1*97Y_OKUVpt-yR69Fn_cEtA.jpeg" alt="Owl" />
      <div class="content">
        <p>Nov 10, 2100</p>
        <h3>Owl</h3>
        <p>
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Impedit
          reiciendis, dolorem magnam ad tenetur quod eum aut beatae labore
          repudiandae quia atque voluptatem ab enim error praesentium? Omnis,
          nostrum aliquam.
        </p>
      </div>
    </section>
  </body>
</html>
```

## The Contrast & Scale UI Design Fundamentals

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Contrast and Scale Example</title>
  </head>
  <body>
    <!-- main#main-content>section*3.section.section-$>img+div.content>p{Nov 15, 2100}+h3{Some Title}+p{Some Text} -->

    <main id="main-content">
      <!-- About Sheep -->
      <section class="section section-1">
        <img src="https://cdn-images-1.medium.com/max/1000/1*aqtjqy983b0DiH9dLuBuBg.jpeg" alt="sheep" />
        <div class="content">
          <p>Nov 15, 2100</p>
          <!--First of its kind-->
          <h3>Sheep</h3>
          <p>
            <!--(- * - => +)-->
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Culpa
            asperiores alias numquam consectetur hic, in natus iste, odit atque
            doloremque minus architecto aut, corrupti cum velit quam perferendis
            amet animi?
          </p>
        </div>
      </section>

      <!-- About Bird -->
      <section class="section section-2">
        <img src="https://cdn-images-1.medium.com/max/1000/1*0k64rIgICpKnA5G40Q9YNg.jpeg" alt="bird" />
        <div class="content">
          <p>Nov 15, 2100</p>
          <h3>Bird</h3>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Culpa
            asperiores alias numquam consectetur hic, in natus iste, odit atque
            doloremque minus architecto aut, corrupti cum velit quam perferendis
            amet animi?
          </p>
        </div>
      </section>

      <!-- About Tiger -->
      <section class="section section-3">
        <img src="https://cdn-images-1.medium.com/max/1000/1*_YphsTgOaE33RJ-MbrNisg.jpeg" alt="tiger" />
        <div class="content">
          <p>Nov 15, 2100</p>
          <h3>Tiger</h3>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Culpa
            asperiores alias numquam consectetur hic, in natus iste, odit atque
            doloremque minus architecto aut, corrupti cum velit quam perferendis
            amet animi?
          </p>
        </div>
      </section>
    </main>
  </body>
</html>
```

```css
* {
  margin: 0;
  padding: 0;
}

body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  background-color: rgb(61, 70, 78);
}

/* shared styles for sections */
.section {
  background-color: rgb(7, 55, 119);

  /* Initiating the Flexbox Model */
  display: flex;
}

/* img */
img {
  width: 150px;
  height: 150px;
  object-fit: cover;
  border-radius: 50%;
}

/* Improvements */
#main-content {
  padding: 30px;

  display: flex;
  flex-direction: column;
  align-items: center;
}

.section {
  width: 70%;
  justify-content: space-evenly;
  margin-bottom: 20px;
  padding: 20px;
  background-color: rgb(131, 167, 214);
  border-radius: 10px;
  transition: transform 0.35s ease-in-out;
}

.section:hover {
  transform: scale(1.05);
}

.content {
  width: 70%;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
}

p:not(:first-of-type) {
  font-size: 20px;
}

.section .content h3 {
  font-size: 30px;
  margin-bottom: 10px;
}
```

## The Typography UI Design Fundamental

![img](https://cdn-images-1.medium.com/max/1000/1*c4uBNUjStu6yBMtLTQPaZQ.png)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link
      href="https://fonts.googleapis.com/css?family=Liu+Jian+Mao+Cao|Oswald|Spicy+Rice&display=swap"
      rel="stylesheet"
    />
    <title>Typography</title>
  </head>
  <body>
    <main>
      <h1 id="main-heading">Some Heading</h1>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Nobis mollitia
      </p>
      <div class="all-content">
        <!-- About Cat -->
        <section class="section section-1">
          <div class="content">
            <img src="https://cdn-images-1.medium.com/max/1000/1*XO81xd2XI11_lcU-OA9QFw.jpeg" alt="cat" />
            <p>This is a really important topic about cats that must be read</p>
            <p>Mr Cat</p>
          </div>
        </section>

        <!-- About Giraffe -->
        <section class="section section-2">
          <div class="content">
            <img src="https://cdn-images-1.medium.com/max/1000/1*hKg4Z8qg8aXDuttxS37lEg.jpeg" alt="giraffe" />
            <p>
              This is a really important topic about giraffes that must be read
            </p>
            <p>Mr Giraffe</p>
          </div>
        </section>

        <!-- About Fox -->
        <section class="section section-3">
          <div class="content">
            <img src="https://cdn-images-1.medium.com/max/1000/1*M3TfkwD8LLkkuz1qAEhPQQ.jpeg" alt="fox" />
            <p>
              This is a really important topic about foxes that must be read
            </p>
            <p>Mr Fox</p>
          </div>
        </section>
      </div>
    </main>
  </body>
</html>
```

```css
* {
  margin: 0;
  padding: 0;
}

/* shared styles for sections */
main {
  background-color: rgb(216, 230, 218);
  padding: 30px;
}

main .all-content {
  display: flex;
  justify-content: space-evenly;
}

main .all-content .section {
  width: 250px;
  background-color: rgb(83, 95, 107);
}

img {
  width: 150px;
  height: 150px;
  object-fit: cover;
  border-radius: 50%;
}

h1 {
  font-family: "Oswald", sans-serif;
}

p:not(:first-of-type) {
  text-align: left;
  font-family: "Liu Jian Mao Cao", cursive;
}

p {
  font-family: "Spicy Rice", cursive;
}
```

1. Heading이 Paragraph과 다른 글자 종류를 가지고 있다.
2. 총체적 난국이다.

## Improved Typography Version

![img](https://cdn-images-1.medium.com/max/1000/1*UKZIQbRnRp9fx2Scfo6z9A.png)

```css
* {
  margin: 0;
  padding: 0;
}

/* shared styles for sections */
main {
  background-color: rgb(216, 230, 218);
  padding: 30px;
}

main .all-content {
  display: flex;
  justify-content: space-evenly;
}

main .all-content .section {
  width: 250px;
  background-color: rgb(83, 95, 107);
}

img {
  width: 150px;
  height: 150px;
  object-fit: cover;
  border-radius: 50%;
}

h1 {
  font-family: "Oswald", sans-serif;
}

p:not(:first-of-type) {
  text-align: left;
  font-family: "Liu Jian Mao Cao", cursive;
}

p {
  font-family: "Spicy Rice", cursive;
}

/* Improvements */
main > h1,
main > p {
  text-align: center;
}

h1 {
  margin-bottom: 10px;
}

.section {
  margin: 20px 0;
  padding: 20px;
  border: 5px;
  color: white;
}

img {
  display: block;
  margin: 0 auto 15px;
}

p:not(:first-of-type),
p {
  font-family: Arial, Helvetica, sans-serif;
  margin-bottom: 15px;
}

p {
  line-height: 1.6;
}
```

## The Color UI Design Fundamental

![img](https://cdn-images-1.medium.com/max/1000/1*1mSWTZeHY0wjhDU_-4IiTw.png)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Color</title>
  </head>
  <body>
    <header></header>
    <section>
      <h1>Some Very Important Title</h1>
      <p>
        Some text that relates to the above very important topic is supposed to
        apppear here
      </p>
      <a href="#">Some link</a>
    </section>
    <footer></footer>
  </body>
</html>

```

```css
body {
  font-family: Arial, Helvetica, sans-serif;
  background-color: #1f0252;
}

header {
  height: 5rem;
  background-color: #7141c4;
}

section {
  padding: 3rem 2rem 2rem;
  background: #811573;
}

h1 {
  margin: 0;
  color: #617bff;
}
a {
  background: #157a81;
  padding: 0.5rem 2.3rem;
  display: inline-block;
  color: #3c1581;
  text-decoration: none;
  border-radius: 1rem;
  font-weight: bold;
  font-size: 0.9rem;
  margin-top: 1.5rem;
  margin-bottom: 2rem;
}

p {
  color: #ff6eec;
  margin: 2rem 0;
}

footer {
  height: 2rem;
  background: #1f0252;
}
```

## Improved Color Version

![img](https://cdn-images-1.medium.com/max/1000/1*yLglEkBr0xiJLe9lJ24e_Q.png)

```css
body {
  font-family: Arial, Helvetica, sans-serif;
  background-color: #1f0252;
}

header {
  height: 5rem;
  background-color: #7141c4;
}

section {
  padding: 3rem 2rem 2rem;
  background: #811573;
}

h1 {
  margin: 0;
  color: #617bff;
}
a {
  background: #157a81;
  padding: 0.5rem 2.3rem;
  display: inline-block;
  color: #3c1581;
  text-decoration: none;
  border-radius: 1rem;
  font-weight: bold;
  font-size: 0.9rem;
  margin-top: 1.5rem;
  margin-bottom: 2rem;
}

p {
  color: #ff6eec;
  margin: 2rem 0;
}

footer {
  height: 2rem;
  background: #1f0252;
}

/* Improvements */
section {
  background-color: #3c1581;
}

/* More Readable */
h1,
p {
  color: white;
}

a {
  background-color: #feed00;
}
```

https://colorpalettes.net/category/warm-colors/

https://webkul.github.io/coolhue/

https://flatuicolors.com/

https://www.color-hex.com/

https://www.smashingmagazine.com/2010/01/color-theory-for-designers-part-1-the-meaning-of-color/

https://www.smashingmagazine.com/2010/02/color-theory-for-designers-part-2-understanding-concepts-and-terminology/

https://www.smashingmagazine.com/2010/02/color-theory-for-designer-part-3-creating-your-own-color-palettes/

https://www.smashingmagazine.com/2012/10/the-code-side-of-color/

https://colorme.io/

## UI Design Fundamentals Challenge 2

![img](https://cdn-images-1.medium.com/max/1000/1*b7sC9Kz7vMpfyckLpxFh2w.png)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Challenge 2 - Colors</title>
  </head>
  <body>
    <section>
      <h1>Contact Us</h1>
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Vero nobis in
        nemo, necessitatibus reiciendis quia!
      </p>
      <form>
        <label for="name">Your name</label>
        <input type="text" id="name" />

        <label for="message">Your Message</label>
        <textarea id="message" rows="15"></textarea>

        <input type="submit" value="Send message" />
      </form>
    </section>
  </body>
</html>
```


```css
body {
  background: rgba(0, 0, 0, 0.8);
  color: white;
  font-family: Arial, Helvetica, sans-serif;
}

section {
  margin-top: 3rem;
  border-left: 0.7rem solid gray;
  padding: 0 3rem;
  width: 60%;
}

h1 {
  margin: 0;
}
p {
  color: #9d9d9d;
  margin: 0.5rem 0 2rem;
}

label {
  display: block;
  font-weight: bold;
  margin-bottom: 0.7rem;
}

input[type="text"],
textarea {
  margin-bottom: 1.5rem;
  display: block;
  padding: 0.5rem;
  width: 80%;
  background: gray;
  border: none;
  border-bottom: 1px solid lightgray;
  outline: 0;
  color: black;
}

input[type="text"]:focus,
textarea:focus {
  border-bottom: 1px solid white;
}

input[type="submit"] {
  background: gray;
  border: none;
  color: white;
  font-weight: bold;
  padding: 0.8rem 2rem;
  border-radius: 2rem;
  font-size: 0.8rem;
}

/* Improvements */
```

### Improved Version

![img](https://cdn-images-1.medium.com/max/1000/1*Lb9g5bboOErX7R-D7rZYwA.png)

```css
body {
  background: rgba(0, 0, 0, 0.8);
  color: white;
  font-family: Arial, Helvetica, sans-serif;
}

section {
  margin-top: 3rem;
  border-left: 0.7rem solid gray;
  padding: 0 3rem;
  width: 60%;
}

h1 {
  margin: 0;
}
p {
  color: #9d9d9d;
  margin: 0.5rem 0 2rem;
}

label {
  display: block;
  font-weight: bold;
  margin-bottom: 0.7rem;
}

input[type="text"],
textarea {
  margin-bottom: 1.5rem;
  display: block;
  padding: 0.5rem;
  width: 80%;
  background: gray;
  border: none;
  border-bottom: 1px solid lightgray;
  outline: 0;
  color: black;
}

input[type="text"]:focus,
textarea:focus {
  border-bottom: 1px solid white;
}

input[type="submit"] {
  background: gray;
  border: none;
  color: white;
  font-weight: bold;
  padding: 0.8rem 2rem;
  border-radius: 2rem;
  font-size: 0.8rem;
}

/* Improvements */
body {
  background-color: white;
  color: #1c2022;
}

section {
  border-left: 0.7rem solid #ff01ff;
}

p {
  color: #2b3337;
}

input[type="text"],
textarea {
  background-color: white;
  border-bottom: 1px solid #506671;
  color: #2b3337;
}

input[type="submit"] {
  background-color: #ff01ff;
}

input[type="text"]:focus,
textarea:focus {
  border-bottom: #ff01ff 1px solid;
}
```

## The Visual Hierarchy UI Design Fundamental

1. Same Level of Importance
2. Higher importance than the rest
3. Visual Hierarchy through contrast
4. Higher Level of Importance through color
5. Higher Level of Importance through scale
6. A combination of UI Design Fundamentals = Scale + Color + Contrast

![img](https://cdn-images-1.medium.com/max/1000/1*IOf2LyxCFni-XZ_NjDlRKA.png)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Visual Hierarchy</title>
    <style>
      body {
        background-color: #7141c4;
        height: 100vh;

        overflow: hidden;

        display: flex;
        justify-content: center;
        align-items: center;
      }

      section {
        height: 100px;
        width: 100px;
        border-radius: 50%;
        background-color: lightyellow;
        margin: 30px 50px;
      }
    </style>
  </head>
  <body>
    <section></section>
    <section></section>
    <section></section>
    <section></section>
    <section></section>
  </body>
</html>

```

![img](https://cdn-images-1.medium.com/max/1000/1*8ZB4o2bkv7vNwMCqj65SWw.png)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Visual Hierarchy</title>
    <style>
      body {
        background-color: #7141c4;
        height: 100vh;

        overflow: hidden;

        display: flex;
        justify-content: center;
        align-items: center;
      }

      section {
        height: 100px;
        width: 100px;
        border-radius: 50%;
        background-color: lightyellow;
        margin: 30px 50px;
      }

      section:first-child {
        align-self: flex-start;
      }
    </style>
  </head>
  <body>
    <section></section>
    <section></section>
    <section></section>
    <section></section>
    <section></section>
  </body>
</html>
```

![img](https://cdn-images-1.medium.com/max/1000/1*x9gzVPPqJoGomA4SPBr5sg.png)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Visual Hierarchy</title>
    <style>
      body {
        background-color: #7141c4;
        height: 100vh;

        overflow: hidden;

        display: flex;
        justify-content: center;
        align-items: center;
      }

      section {
        height: 100px;
        width: 100px;
        border-radius: 50%;
        background-color: lightyellow;
        margin: 30px 50px;
      }

      section {
        background-color: rgba(255, 255, 255, 0.4);
      }

      section:nth-child(3) {
        background-color: rgba(255, 255, 255, 1);
      }
    </style>
  </head>
  <body>
    <section></section>
    <section></section>
    <section></section>
    <section></section>
    <section></section>
  </body>
</html>
```

![img](https://cdn-images-1.medium.com/max/1000/1*CvCpEIsyfGnKbdkztW4nJQ.png)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Visual Hierarchy</title>
    <style>
      body {
        background-color: #7141c4;
        height: 100vh;

        overflow: hidden;

        display: flex;
        justify-content: center;
        align-items: center;
      }

      section {
        height: 100px;
        width: 100px;
        border-radius: 50%;
        background-color: lightyellow;
        margin: 30px 50px;
      }

      section:nth-child(4) {
        background-color: #feed00;
      }
    </style>
  </head>
  <body>
    <section></section>
    <section></section>
    <section></section>
    <section></section>
    <section></section>
  </body>
</html>
```

![img](https://cdn-images-1.medium.com/max/1000/1*Ke_tw3BzRckYbNkce3Guwg.png)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Visual Hierarchy</title>
    <style>
      body {
        background-color: #7141c4;
        height: 100vh;

        overflow: hidden;

        display: flex;
        justify-content: center;
        align-items: center;
      }

      section {
        height: 100px;
        width: 100px;
        border-radius: 50%;
        background-color: lightyellow;
        margin: 30px 50px;
      }

      section {
        transform: scale(0.89);
      }

      section:nth-child(5) {
        transform: scale(1.5);
      }
    </style>
  </head>
  <body>
    <section></section>
    <section></section>
    <section></section>
    <section></section>
    <section></section>
  </body>
</html>
```

![img](https://cdn-images-1.medium.com/max/1000/1*f2Xz1WH9Sd-xdDdMENnsmA.png)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Visual Hierarchy</title>
    <style>
      body {
        background-color: #7141c4;
        height: 100vh;

        overflow: hidden;

        display: flex;
        justify-content: center;
        align-items: center;
      }

      section {
        height: 100px;
        width: 100px;
        border-radius: 50%;
        background-color: lightyellow;
        margin: 30px 50px;
      }

      section {
        transform: scale(0.89);
      }

      section {
        transform: scale(0.89);
        background-color: rgba(255, 255, 255, 0.4);
      }

      section:nth-child(2) {
        transform: scale(1.5);
        background-color: #feed00;
      }
    </style>
  </head>
  <body>
    <section></section>
    <section></section>
    <section></section>
    <section></section>
    <section></section>
  </body>
</html>
```

### Hierarchy Example

![img](https://cdn-images-1.medium.com/max/1000/1*E6ChbXz_YE60X1Hrqa9Rtg.png)

1. Bigger Heading Tag
2. Visible Input Tag Container
3. Visible Button

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Visual Hierarchy</title>
  </head>
  <body>
    <!-- <section></section>
    <section></section>
    <section></section>
    <section></section>
    <section></section> -->

    <section>
      <h1>Join our Newsletter</h1>
      <form>
        <label for="email">Email Address</label>
        <div class="input-container">
          <input type="email" />
          <input type="submit" value="Submit email" />
        </div>
      </form>
    </section>
  </body>
</html>
```

```css
body {
  padding: 2rem;
  background: #5801cb;
  color: white;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}

h1 {
  font-size: 1rem;
}

form {
  width: 500px;
  padding: 20px;
}

label {
  display: block;
  padding: 10px 0;
}

input[type="email"] {
  padding: 10px;
  width: 70%;
  border: none;
  margin: 0 5px 0 0;
}

input[type="submit"] {
  border: 1px solid white;
  padding: 10px;
  color: white;
  background: none;
}
```

![img](https://cdn-images-1.medium.com/max/1000/1*S2YpksT8OmreJxZJ3IMDcw.png)

```css
body {
  padding: 2rem;
  background: #5801cb;
  color: white;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}

h1 {
  font-size: 1rem;
}

form {
  width: 500px;
  padding: 20px;
}

label {
  display: block;
  padding: 10px 0;
}

input[type="email"] {
  padding: 10px;
  width: 70%;
  border: none;
  margin: 0 5px 0 0;
}

input[type="submit"] {
  border: 1px solid white;
  padding: 10px;
  color: white;
  background: none;
}

/* Imrpovements */
h1 {
  font-size: 2.8rem;
}

form {
  background-color: #6900f3;
}

label {
  font-weight: bold;
  font-size: 1rem;
}

input[type="submit"] {
  font-size: 0.8rem;
  background-color: #ffed8c;
  color: #5801cb;
  font-weight: bold;
}
```

1. Improved Heading
2. Form Tag Background Color - Increasing the level of difference 
3. Label Font Weight
4. Input Type Submit Button - color + background-color + font-weight

## UI Design Fundamentals Final Challenge

![img](https://cdn-images-1.medium.com/max/1000/1*myfbD0BAma1Xzit82rEuFA.png)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Final Challenge - Put Everything Together</title>
  </head>
  <body>
    <!-- aside+main#main-content>h1{Movies}+section.content>h3{Favorite Movies}+ul>li*4>span*2 -->

    <aside></aside>
    <main id="main-content">
      <h1>movies</h1>
      <section class="content">
        <h3>Favorite Movies</h3>
        <ul>
          <li><span>Winter Soldier</span> <span>9.5</span></li>
          <li><span>Aquaman</span> <span>7.4</span></li>
          <li><span>Endgame</span> <span>9.8</span></li>
          <li><span>Justice League</span> <span>4.4</span></li>
        </ul>
      </section>
    </main>
  </body>
</html>
```

```css
* {
  margin: 0;
  padding: 0;
}

body {
  background: #014bcb;
  height: 100vh;
  color: white;
  font-family: Arial, Helvetica, sans-serif;

  display: flex;
}

aside {
  background: #1d3154;
  width: 5%;
  height: 100vh;
}

h1 {
  margin-left: 1rem;
  font-size: 1rem;
  text-transform: uppercase;
}

main {
  width: 30%;
}

.content {
  background: #6c22ff;
  margin-right: 2rem;
  border-radius: 0.8rem;
}

h3 {
  margin: 0;
  font-size: 0.9rem;
  color: #ff69f5;
}

ul {
  list-style-type: none;
  padding: 0;
  margin-bottom: 0;
}

li {
  margin-bottom: 0.5rem;
  font-size: 0.8rem;
}

/* Improvements */
```

### Improved Version

![img](https://cdn-images-1.medium.com/max/1000/1*EnSeVabYz5imK9SBELNq1Q.png)

```css
* {
  margin: 0;
  padding: 0;
}

body {
  background: #014bcb;
  height: 100vh;
  color: white;
  font-family: Arial, Helvetica, sans-serif;

  display: flex;
}

aside {
  background: #1d3154;
  width: 5%;
  height: 100vh;
}

h1 {
  margin-left: 1rem;
  font-size: 1rem;
  text-transform: uppercase;
}

main {
  width: 30%;
}

.content {
  background: #6c22ff;
  margin-right: 2rem;
  border-radius: 0.8rem;
}

h3 {
  margin: 0;
  font-size: 0.9rem;
  color: #ff69f5;
}

ul {
  list-style-type: none;
  padding: 0;
  margin-bottom: 0;
}

li {
  margin-bottom: 0.5rem;
  font-size: 0.8rem;
}

/* Improvements */
h1 {
  margin: 2rem 2rem 2rem 0;
  font-size: 3rem;
}

main {
  padding: 1rem;
}

.content {
  background-color: #0044b9;
  padding: 1.5rem;
}

.content h3 {
  margin: 1rem 0;
  font-size: 1.3rem;
}

.content ul li {
  padding: 0.2rem 0;
  display: flex;

  justify-content: space-between;
}

ul li span {
  font-size: 1rem;
}
```



























