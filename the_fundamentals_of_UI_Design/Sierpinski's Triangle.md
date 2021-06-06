## Sierpinski's Triangle

재귀(Recursion)는 정의한 함수가 자기 자신을 다시 호출하는 프로그래밍 기법이다. 반복문으로 해결할 수 있는 대부분의 문제는 재귀로 해결이 가능하다. 시에르핀스키(Sierpinski) 삼각형은 재귀를 잘 사용할 수 있는 좋은 예시다.

![img](https://miro.medium.com/max/2396/1*RAPD6pU2DXYRrMQypUDsFg.png)

재귀를 사용하려면 베이스가 존재해야한다. 일반적으로 `n == 0` 혹은 `n == 1`일 때 발생한다. `n == 1` 인 경우에 시에르핀스키 삼각형은 하나의 정삼각형이다.

![정삼각형 - 위키백과, 우리 모두의 백과사전](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ec/Regular_triangle.svg/1200px-Regular_triangle.svg.png)

`draw_triangle`라는 함수는 삼각형을 하나 그릴 때 사용할 수 있다. 변의 길이를 함수에 전달하고, `turtle`이라는 그래픽 모듈을 이용해서 삼각형을 그릴 수 있다.

```python
import turtle

turtle = turtle.Turtle() # turtle이라 불리는 팬을 하나 생성
turtle.forward() # turtle을 앞으로 이동
turtle.backward() # turtle을 뒤로 이동
turtle.left(angle) # angle 만큼 왼쪽으로 회줜
turtle.right(angle) # angle 만큼 오른쪽으로 회줜
turtle.pendown() # pen down
turtle.penup() # pen up
turtle.speen(n) # turtle 속도

# 삼각형 그리는 함수
def draw_triangle(length):
	for i in range(3):
        turtle.right(120)
        turtle.forward(length)
```

시에르핀스키의 삼각형은 음수가 아닌 양수 정수에 의해 동작한다. 다시 말해서 순서가 1부터 시작하기 때문에, `draw_triangle` 함수 자체가 기본 케이스가 될 수 있다. 이제는 이 `draw_triangle` 함수를 이용해서 세 개의 삼각형을 그리는 방법에 대해 알아보자

```python
def sierpinski_order_two(length):
    draw_triangle(length)
    turtle.right(120)
    turtle.forward(length)
    draw_triangle(length)
    turtle.left(120)
    turtle.forward(length)
    draw_triangle(length)
    turtle.forward(length)
```

`sierpinski_order_two` 함수는 순서가 1인 (기본 케이스)인 `draw_triangle` 함수를 세 번 호출한다. 조금 더 구체적으로 보자면, 첫 번째 삼각형이 정점으로 이동하고, 두번째 삼각형은 오른쪽으로 이동하고, 세번째 삼각형은 두번째를 기준으로 왼쪽으로 이동한다. 그래서 아래와 같은 결과가 출력된다.

![img](https://cdn-images-1.medium.com/max/1000/1*LKECXWTjMSLxJlUO8ornHg.jpeg)

순서가 1과 2인 경우를 처리할 수 있는 방식으로 함수를 재귀적으로 작성해보겠습니다. 

```python
def sierpinski_order_two_recursive(n, length):
    if n == 1:
        draw_triangle(length)
    else:
        sierpinski_order_two_recursive(n - 1, length)
        turtle.right(120)
        turtle.forward(length)
        sierpinski_order_two_recursive(n - 1, length)
        turtle.left(120)
        turtle.forward(length)
        sierpinski_order_two_recursive(n - 1, length)
        turtle.forward(length)
```

n = 2 인 경우

![img](https://cdn-images-1.medium.com/max/1000/1*LKECXWTjMSLxJlUO8ornHg.jpeg)

n = 1

![정삼각형 - 위키백과, 우리 모두의 백과사전](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ec/Regular_triangle.svg/1200px-Regular_triangle.svg.png)

n = 3

![img](https://cdn-images-1.medium.com/max/1000/1*lcoNp836XCzMiJtU_CoQLg.jpeg)

n = 3을 넣었을 때, 육안으로는 괜찮아 보이지만, 시어핀스키 형태의 삼각형을 그리지 않는 것을 확인할 수 있다. 위 코드를 조금 수정해서 시어핀스키 형태의 삼각형을 만들어보자

```python
def sierpinski_order_two_recursive(n, length):
    if n == 1:
        draw_triangle(length)
    
    else:
        sierpinski_order_two_recursive(n - 1, length)
        turtle.right(120)
        turtle.forward(length * (n - 1))
        sierpinski_order_two_recursive(n - 1, length)
        turtle.left(120)
        turtle.forward(length * (n - 1))
        sierpinski_order_two_recursive(n - 1, length)
        turtle.forward(length)
```

![img](https://cdn-images-1.medium.com/max/1000/1*5bQGwDzTXbPnGhGJLn09uw.png)

n = 3일 때 위와 같이 잘 동작하는 것을 확인할 수 있다.

n = 4

![img](https://cdn-images-1.medium.com/max/1000/1*V86mVKFQhde_GW6i7ehGIA.png)

시어리스키 삼각형의 형태를 띄지만 아직은 중간에 겹침의 발생을 알 수 있다.

n = 5

![img](https://cdn-images-1.medium.com/max/1000/1*NNVizZi-qp6nZLnZ6sGlqw.png)



Order 1 : length = 1

Order 2:  length = 2

Order 3: length  = 4

Order 4: length = 8

2 ^ (n - 1)

```python
def sierpinski_order_two_recursive(n, length):
    if n == 1:
        draw_triangle(length)
    
    else:
        sierpinski_order_two_recursive(n - 1, length)
        turtle.right(120)
        turtle.forward(length * 2 ** (n - 1))
        sierpinski_order_two_recursive(n - 1, length)
        turtle.left(120)
        turtle.forward(length * 2 ** (n - 1))
        sierpinski_order_two_recursive(n - 1, length)
        turtle.forward(length * 2 ** (n - 1))
```

n = 4

![img](https://cdn-images-1.medium.com/max/1000/1*hhGEbIbp1SBI8iLzAPivuQ.png)

n = 8

![img](https://cdn-images-1.medium.com/max/1000/1*WIPtnlI_5F8l6FH8ZiekHQ.png)

