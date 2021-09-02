In the past week, I learned two online courses, [Machine Learning](#Part 1 Machine Learning) on Bilibili by Andrew Ng, [Python programming](#Part 2 Python programming) on Mooc. Here are study notes and code on these.

# Part 1 Machine Learning

Machine learning

​	-machine learning is a field that had grown out of the field of AI

​	-machine learning was developed as a new capability for computers

Examples:

​	-Database mining

​		Large datasets from growth of automation/web.

​		E.g., Web click data, medical records, Computational biology, engineering

​	-Applications can't program by hand.

​		E.g., Autonomous helicopter, handwriting recognition, most of Natural Language Processing(NLP), Computer Vision.

​	-Self-customizing programs

​		E.g., Amazon, Netflix product recommendations

​	-Understanding human learning (brain, real AI).

Machine Learning definition

Arthur Samuel(1959). Machine Learning: Field of study that gives computers the ability to learn without being explicitly programmed.

Tom Mitchell(1998) Well-posed Learning Problem: A computer program is said to learn from experience E with respect to some task T and some performance measure P, if its performance on T, as measured by P, improves with experience E.

 

Machine learning algorithms:

-Supervised learning

-Unsupervised learning

Others: Reinforcement learning, recommender systems.

Also talk about: Practical advice for applying learning algorithms.



## Supervised Learning

Supervised Learning refers to the fact that we gave the algorithm a data set in which the "right answers" were given.

To define with a bit more terminology this is also called a regression problem.

In supervised learning, in every example in our data set, we are told what is the "correct answer" that we would have quite liked the algorithms have predicted on that example.



## Unsupervised Learning

Given a data set with the same label or just without any label, an unsupervised learning algorithm might decide that the data lives in two different clusters. So this is called a clustering algorithm.

# Part 2 Python programming

```python
dayup = pow(1.001,365)
daydown = pow(0.999,365)
print("向上：{:.2f},向下：{:.2f}".format(dayup,daydown))
```

```python
dayfactor = 0.005
dayup = pow(1+dayfactor,365)
daydown = pow(1-dayfactor,365)
print("向上：{:.2f},向下：{:.2f}".format(dayup,daydown))
```

```python
dayup = 1.0
dayfactor = 0.01
for i in range(365):
    if i%7 in [6,0]:
        dayup = dayup*(1-dayfactor)
        
    else:
        dayup = dayup*(1+dayfactor)
print("工作日的力量：{:.2f}".format(dayup))
```

```python
def dayup(df):
    dayup = 1
    for i in range(365):
        if i%7 in [6,0]:
            dayup = dayup*(1-0.01)
        else:
            dayup = dayup*(1+df)
    return dayup
dayfactor = 0.01
while dayup(dayfactor) <37.78:
    dayfactor+=0.001
print("工作日的努力参数是：{:.3f}".format(dayfactor))
```

```python
import random
def dayUP(df,dayup):
    for i in range(365):
        dayup = dayup+df
    print("在此模式下，努力一年的结果是{:.3f}".format(dayup))
def choice():
    print("1.每天努力0.001")
    print("2.每天努力0.005")
    print("3.每天努力0.01")
    print("4.工作日努力0.019，休息日下降0.001")
    print("5.随机努力与否")
    x = eval(input("选择你的努力模式"))
    if x == 1:
        dayUP(0.001,1)
    elif x==2:
        dayUP(0.005,1)
    elif x==3:
        dayUP(0.01,1)
    elif x==4:
        dayUpwork(0.019,0.001,1)
    elif x==5:
        dayUprand()
    else:
        return('break')
def dayUprand():
    duf = random.choice([0.001,0.002,0.003,0.004,00.005,0.006,0.007,0.008,0.009,0.01])
    ddf = 0.001


    # upday = random.randint(1,365)
    dayup = 1
    for i in range(365):
        upordown = random.choice([0, 1])
        if upordown == 0:
            dayup = dayup+duf
        elif upordown == 1:
            dayup = dayup-ddf
    print("在随机模式下，努力一年的结果是{:.3f}".format(dayup))
def dayUpwork(duf,ddf,dayup):
    for i in range(1,366):
        if i%7 in [6,0]:
            dayup = dayup+duf
        else:
            dayup = dayup-ddf
    print("在工作日模式下，努力一年的结果是{:.3f}".format(dayup))
while True:
    choice()
```

```python
a = eval(input())
b = pow(a,0.5)
print("{:+>30.3f}".format(b))
```

```python
x = input()
print(x.split('-')[0]+'+'+x.split('-')[-1])
```

```python
while True:
    z = ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z']
    x = input()
    for i in x:
        if i.upper() != i:
            print(z[(z.index(i.upper()) + 3) % 26].lower(), end='')
        elif i not in z:
            print(i, end='')
            continue
        elif i.upper()==i:
            print(z[(z.index(i)+3) % 26],end = '')
```

```python
import random
x = 1
while True:
    set=[]
    upordown = random.choice([0, 1])
    if upordown == 0:
        print('1')
        set.append(1)
    elif upordown == 1:
        print('2')
        set.append(2)

    x+=1
    if x >100:
        print(set)
        break
```

```python
# import time
# for i in range(101):
#     print("\r{:3}%".format(i),end='')
#     time.sleep(0.1)
import random
upordown = random.choice([0,1])
if upordown == 0:
    print('1')
elif upordown == 1:
    print('2')
```

```python
import time
scale = 50
print("执行开始".center(scale//2,'-'))
start = time.perf_counter()
for i in range(scale+1):
    a = i/scale*100
    b = '*' * i
    c = ' ' * (scale-i)
    dur = time.perf_counter() - start
    print("\r{:^3.0f}%[{}->{}]{:.2f}s".format(a,b,c,dur),end='')
    time.sleep(0.1)
print("\n"+"执行结束".center(scale//2,'-'))
```

```python
import time
scale = 10
print("{0:-^20}".format('执行开始'))
for i in range(scale+1):
    a = '*'*i
    b = '.'*(scale - i)
    c = (i/scale)*100
    print("\r{:^3.0f}%[{}->{}]".format(c,a,b),end="")
    time.sleep(0.1)
print("\n{0:-^20}".format('执行结束'))
```

```python
import time
for i in range(101):
    print("\r{:3}%".format(i), end="")
    time.sleep(0.1)
```

```python
# import time
# scale = 50
# print("执行开始".center(scale//2, "-"))
# start = time.perf_counter()
# for i in range(scale+1):
#     a = '*' * i
#     b = '.' * (scale - i)
#     c = (i/scale)*100
#     dur = time.perf_counter() - start
#     print("\r{:^3.0f}%[{}->{}]{:.2f}s".format(c,a,b,dur),end='')
#     time.sleep(0.1)
# print("\n"+"执行结束".center(scale//2,'-'))
import time
scale = 50
print("执行开始".center(scale//2,'-'))
start = time.perf_counter()
for i in range(scale+1):
    a = i/scale*100
    b = '*' * i
    c = ' ' * (scale-i)
    dur = time.perf_counter() - start
    print("\r{:.0f}%[{}->{}]{:.2f}s".format(a,b,c,dur),end='')
    time.sleep(0.1)
print("\n"+"执行结束".center(scale//2,'-'))
```

```python
x = eval(input())
for i in range(1,x+1,2):
    print("{0:^{1}}".format('*'*i,x))
    # print("{}{}".format(' '*((x-i)//2),'*'*i))
```

```python
while True:
    x = eval(input())
    print("{:-^20}".format(x*x*x))
```

```python
height,weight = eval(input())
c ,a = '',''
x = weight/pow(height,2)
if x < 18.5:
    a = '偏瘦'
    c = '偏瘦'
elif 18.5 < x < 24:
    a = '正常'
    c = '正常'
elif 24<x<25:
    a = '正常'
    c = '偏胖'
elif 25<x<28:
    a = '偏胖'
    c = '偏胖'
elif 28<x<30:
    a = '偏胖'
    c = '肥胖'
elif x>30:
    a = '肥胖'
    c = '肥胖'
print('BMI数值为:{:.2f}'.format(x))
print("BMI指标为:国际'{}',国内'{}'".format(a,c))
```

```python
Nnums = []
for i in range(100,1000):
    if pow(eval(str(i)[0]),3)+pow(eval(str(i)[1]),3)+pow(eval(str(i)[2]),3) == i:
        Nnums.append(i)
print(*Nnums,sep = ',')
```

```python
import random as rd
bits = eval(input())
round = 0.0
rd.seed(123)
for i in range(1,bits+1):
    x,y = rd.random(),rd.random()
    if pow(x**2+y**2,0.5)<1:
        round = round+1
print('{:.6f}'.format(4*round/bits))
```

```python
import random as rd
from time import perf_counter

darts = 100000000
hits = 0.0
start = perf_counter()
for i in range(1,darts+1):
    x,y = rd.random(),rd.random()
    dist = pow(x**2+y**2,0.5)
    if dist<=1.0:
        hits = hits+1
pi = 4*(hits/darts)
print('圆周率的值为{}'.format(pi))
print('运行时间为：{:.5f}s'.format(perf_counter()-start))
```

```python
for s in range(1000,10000,1):
    if eval(str(s)[0])**4+eval(str(s)[1])**4+eval(str(s)[2])**4+eval(str(s)[3])**4 == s:
        print(s)
```

```python
user = 'Kate'
password = '666666'

count = 0
while True:
    u = input()
    p = input()
    if u == user and p == password:
        print('登录成功！')
        break
    if u!=user or p!=password:
        count+=1
    if count==3:
        print('3次用户名或者密码均有误！退出程序。')
        break
```

