# Info Science Journal
*13/2/2020*

1.What did we do?

We programmed a dice into processing using python. We added functions like a number counter, a bar graph and talked about animating it although it doesn't seem like that will work.

2.What did you learn?

I learned how to use stroke() to program different colors into the bargraph as well as the dice itself. Learned to always double check my own code because my biggest problem seems to be forgetting commas, ;, : etc etc

3.What question(s) do you have?

How to animate something/ is it possible to?
How is a dice program used in real life situations e.g. games(board games especially)?




Code for this lesson:

```.py
#These variables are to count the rolls of the dice
ones=0
twos=0
threes=0
fours=0
fives=0
sixes=0

def setup():
    size (600,600)
    background(255)
    
def draw():
    x=0
    delay(500)
    mouseClick()
    barGraph()

    
def barGraph():
    fill(0)
    textSize(20)
    for x in range(6):
        text(x+1,(150+50*x), 580)
   
    stroke(12,244,252)    
    rect(150, 550 - ones, 10, ones)
    stroke(12,88,252)
    rect(200, 550 - twos, 10, twos)
    stroke(252,12,12)
    rect(250, 550 - threes, 10, threes)
    stroke(0,255,0)
    rect(300, 550 - fours, 10, fours)
    stroke(229,255,50)
    rect(350, 550 - fives, 10, fives)
    stroke(0)
    rect(400, 550 - sixes, 10, sixes)
    stroke(252,124,12)
 

def mouseClick():
    global ones, twos, threes, fours, fives, sixes
    background(255)
    stroke(0)
    fill(255)
    rect(100,100, 400, 400, 10)
    stroke(255,0,0)
    strokeWeight(10)

    
    
    n=random(0,6)
    print(n)
    if 0<=n<1.0:
        circle(300,300,50)
        ones= ones + 1
        print("Number of times one has been rolled: ",ones)
    if 1.0<=n<2.0:
        circle(200,200,50)
        circle(400,400,50)
        twos= twos + 1
        print("Number of times twos has been rolled: ",twos)
    if 2.0<=n<3.0:
        circle(200,200,50)
        circle(400,400,50)
        circle(300,300,50)
        threes= threes + 1
        print("Number of times threes has been rolled: ",threes)
    if 3.0<=n<4.0:
        circle(200,200,50)
        circle(400,200,50)
        circle(200,400,50)
        circle(400,400,50)
        fours= fours + 1
        print("Number of times fours has been rolled: ",fours)
    if 4.0<=n<5.0:
        circle(200,200,50)
        circle(400,200,50)
        circle(200,400,50)
        circle(400,400,50)
        circle(300,300,50)
        fives= fives + 1
        print("Number of times fives has been rolled: ",fives)
    if 5.0<=n<6.0:
        circle(200,200,50)
        circle(400,200,50)
        circle(200,400,50)
        circle(400,400,50)
        circle(200,300,50)
        circle(400,300,50)
        sixes= sixes + 1
        print("Number of times sixes has been rolled: ",sixes)
```
