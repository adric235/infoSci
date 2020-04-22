# 1) Program to print 100 bears
```.py
# print a list of 100 bears 
for i in range(101): # create a loop where i goes from 0 to 100             
 print(f'{i} bears')
 ```
    
# 2) To print 1900 - 2000  
```.py
for i in range (1900, 2001):
          print ("The year is", i)

```
    
# 3) To print celsius to fahrenheit
```.py
# Create a program that prints the conversion for Celsius to Fahrenheit
def celsius_to_fahrenheit(celsius):
    ''' create a function to convert celsius degree to fahrenheit degree'''
    fahrenheit = (celsius * 9/5) + 32
    return fahrenheit

for c in range(101):
    f = celsius_to_fahrenheit(c)
    print(f'{c} degrees Celsius = {f} degrees Fahrenheit')
```
# 4) Bargraph + Counting 
```.py
x = []
y= []
person = [False, True] #False=>infected
il = 0
h = 25
c = 0
bar = 0

def setup():
    size(500,500)
    for n in range (25):
        x.append(random(0, 500))
        person.append(True) #All Healthy
        y.append(random(0, 500))
        barGraph()
        

        
def distance(x1, x2, y1, y2):
    a = (x1 - x2)
    b = (y1 - y2)
    c = sqrt(a**2 + b**2)
    return c


    
    
def draw():
    global x, y, il, h, c, l
    background(255)
    strokeWeight(2)
    barGraph()
    c += 1
    if il == 25:
        c -= 1


    
    #create 1st individual
    for i in range(0, 25):
        if person[i] == True:
            fill(255) #healthy
        else:
            fill (255, 0, 0) #infected

            
            
        circle(x[i], y[i], 40)
        
        x[0] = x[0] + random(-10, 10)
        y[0] = y[0] + random(-10, 10)

        x[1] = x[1] + random(-10, 10)
        y[1] = y[1] + random(-10, 10)
        
        for g in range(len(x)):
            if g == i:
                continue
            d = distance(x[i], x[g], y[i], y[g])
            if d < 40 and (person[g] == False or person[i]== False):
                #infection happens
                person[i] = False
                person[g] = False

        
        #boundaries conditions
        if x[i] > 500:
            x[i] = 500
    
        # add three more extentions
        
        if x[i] < 0:
            x[i] = 0
            
        if y[i] > 500:
            y[i] = 500
    
        if y[i] < 0:
            y[i] = 0
            
    il = 0
    h = 25
    for bar in range (25):
        if person[bar] == False:
            il += 1
            h -= 1
            
    textSize(10)
    fill(0)
    text("Infected", 445, 478)
    text("Healthy", 445, 458)
    text (c, 80, 470)
    text("Iteration #:", 20, 470)
    

def barGraph():
    strokeWeight(1)
    stroke(0)
    fill(255, 0, 0)
    rect (440, 470, -il*2, 8)
    fill (255)
    rect (440, 450, -h*2, 8)
```
 # 5) Table 
  Case Number         Number of people moving       Population size     Number of iterations until all population is infected
  1                     1                           25                   1100
  2                     2                           25                   818
  3                     3                           25                   275
  4                     5                           25                   352
  5                     7                           25                   103

# 6) Another Table Proposal
- Changing the size
- speed of movement (varied speeds)
- Transmissions that were infected, but did not directly infect(could be on them, but they dont have it because they sanitized prior)
