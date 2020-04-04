# Info Science Journal
*04/04/2020*

Task 1

What are some ways in which Computer Science can help the fight against Covid-19?

Scientists are using computer simulations to try to figure how Covid-19's "spike proteins" work. However, since one computer does not possess nearly enough processing power to run these simulations, they need a lot of people to bring over processing power to succefully run their experiments.

In your opinion, should people enable access to the resources of their personal computers as tools for research? Are there any risks?
Yes, in this fight for humanity and for each other we should contribute however we can. If it helps to solve this problem of Covid-19, we should take any measure we can as a community. After reading this article, I have already signed up to help. I believe since it is coming from such a reputable medical insititution, it should be completely safe to use. 

What should be some behaviours (at least 3) that we will need to include in our simulation to be a realistic approximation of the current situation in the world? Explain.
1. Collisions- The circles in the simulation go through each other instead of colliding and then rebounding off of each other. Individuals in the real world dont pass through each other, they bump each other and then go seperate ways. 
2. Infections- If a circle starts off being infected with the virus it should have a color, and touching other circles will make that color transfer onto others. If an individual also has recovered, there should be a color code detailing it.
3. Size of circles - size could be an indicitor of age 

Video #1 

```.py
posx = 300
posy = 300

def setup():
    size(500,500)
    
def draw():
    global posx,posy
    background(255)
    strokeWeight(2)
    #individual
    circle(posx, posy, 40)
    posx = posx + random(-10, 10)
    posy = posy + random(-10, 10)
   
    #boundaries conditions
    if posx > 500:
        posx = 500
        
    if posx < 0:
        posx = 0
    
    if posy > 500:
        posy = 500
        
    if posx < 0:
        posy = 0
     
       
    delay(100)
    



Video #2(making 10 circles using values in lists)
x = []
y = []

def setup():
    size(500,500)
    for i in range(10):
        x.append(random(0,500))
        y.append(random(0,500))
    
def draw():
    global x, y
    background(255)
    strokeWeight(2)
    
 
    
    #individual           
    for i in range(10):
        circle(x[i], y[i], 40)
        x[i] = x[i] + random(-10, 10)
        y[i] = y[i] + random(-10, 10)

        #boundaries conditions
        if  x[i] > 500:
            x[i] = 500
            
        if  x[i] < 0:
            x[i] = 0
        
        if y[i] > 500:
            y[i] = 500
            
        if y[i] < 0:
            y[i] = 0
        
       
    delay(100)
    
    
    
    
