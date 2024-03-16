
# UNIVERSITY ASSINGNMENT (credit:LUMINAR) 

- sem_2_practical_record1

> [!tip]
> yea give some star guys

>[!warning]
>comment mat chap lena (Rishi)

- goal
- [x] complete all question 

# Q1 student grade calculator

```python

from statistics import mean
class Student:
 	def __init__(self,name,a,b,c,d,e):
 		self.name=name
 		self.lst={'english':a,'mathematics':b,'science':c,'social studies':d,'computer':e}

 	def grade(self,subject_marks):
 		if subject_marks>=90:
 			return 'A'
 		elif subject_marks<90 and subject_marks>=80:
 			return 'B'
 		elif subject_marks<80 and subject_marks>=70:
 			return 'C'
 		elif subject_marks<70 and subject_marks>=60:
 			return 'D'
 		elif subject_marks<60 and subject_marks>=40:
 			return 'E'
 		else:
 			return 'ERROR'

 	def avera(self):
 		tem_lst=[]
 		x=0
 		for i in self.lst.items():
 			tem_lst.append(i[1])
 		print(f'mean/avg {mean(tem_lst)}')
 		for _ in tem_lst:
 			x+=_ 
 		print(f"mean {x/len(tem_lst)}")

 	def display_std(self):
 		print(f'student name {self.name}')
 		for _ in self.lst.items():
 			print(f'{_[0] } : { _[1]}')
 		self.avera()


std1=Student('ola',80,40,50,60,30)
# std1.avera()s
std1.display_std()



```



# Q2 prime & odd set

```python

lst1_odd={ _ for _ in range(1,41,2) }
lst_prime={}
def check_prime(input_variable:int) ->bool:
	cnt=0
	for  i in range(1,input_variable+1):
		if input_variable%i == 0:
			cnt+=1
		else:
			continue

		if cnt>2:
			break

	if cnt==2:
		return True
	else:
		return False
temp_lst=[]
for i in range(1,41):
	
	# print(f" {i}  {check_prime(i)} ",end=' ')
	if check_prime(i):
		# print(i)
		temp_lst.append(i)

lst_prime= set(temp_lst)
print(lst_prime)
print(lst1_odd)

print(f'union {lst_prime | lst1_odd}')
print(f'intersection {lst_prime &lst1_odd}')
print(f'difference {lst_prime - lst1_odd}')
print(f'symmeric difference {lst_prime ^lst1_odd}')




```



# Q3 contact
```python


def check(inp: str)-> None:
	if not inp.isdigit():
		print('only digit accepted')
		return
	if not len(inp)==10:
		print('at least 10 digit require')
		return
	if int(inp)<0:
		print('number can not be negative')
		return
	
	print(f'your contact number> {'*'*7}{inp[-3:]}')


while 1:
	inp=input("enter the contact>")
	check(inp)

```
# Q4 e-mail

```python

inp=input('enter the mail>')
spl=inp.split('@')
print(f'User Name {spl[0]} \nDomain {spl[1]}')
```


# Q5 shapes
```python
class Shape:
	def __init__(self,x,y,typ):
		self.varx=x 
		self.vary=y 
		self.type=typ
	def cal_per(self):
		print(f'perimeter of {self.type} {self.varx+self.vary}')

class Square(Shape):
	def __init__(self,x,y):
		super().__init__(x,y,typ='square')
		self.varx=x 
		self.vary=y 
	def cal_per(self):
		super().cal_per()

class Rectangle(Shape):
	def __init__(self,x,y):
		super().__init__(x,y,typ='Rectangle')
		self.varx=x 
		self.vary=y 
	def cal_per(self):
		super().cal_per()

class Triangle(Shape):
	def __init__(self,x,y,z):
		super().__init__(x,y,typ='Triangle')
		self.varx=x 
		self.vary=y+z
	def cal_per(self):
		super().cal_per()
		
sq=Square(10,20)
sq.cal_per()
sq=Rectangle(10,30)
sq.cal_per()
sq=Triangle(10,20,30)
sq.cal_per()
```



# Q6 Vehicle

```python

class Vehicle():
	def __init__(self,type_vh):
		self.type_=type_vh 

	def prt_tp(self):
		print(f'The type of Vehicle {self.type_}')

class Car(Vehicle):
	def __init__(self,typ_vh):
		super().__init__('4wheeler')
		self.fule=typ_vh
	def prt_tp(self):
		super().prt_tp()

class Motorcycle(Vehicle):
	def __init__(self,typ_vh):
		super().__init__('2wheeler')
		self.fule=typ_vh
	def prt_tp(self):
		super().prt_tp()

cr=Car('Desel')
mb=Motorcycle('Petrol')
cr.prt_tp()
mb.prt_tp()
print(f'fuel {cr.fule} {mb.fule}')



```

# Q7 pie
```python

import  matplotlib.pyplot as plt

lst=[]
lst2=[ 'subject'+str(i) for i in range(1,6)]
print(lst2)
for _ in range(5):
	inp=int(input('enter the number>'))
	lst.append(inp)

print(lst)
plt.figure(figsize=(5,5),)
plt.pie(lst,labels=lst2)
plt.show()



```


# Q8 Employee
```python

class Employee:
	def __init__(self,employee_name,employee_id,hourly_rate):
		self.name=employee_name
		self.id_=employee_id
		self.hourly_rate=hourly_rate

	def monthly_salary(self,hour_work):
		print(f'employe pay roll of 30 days { 30*(hour_work* self.hourly_rate) }')


	def display_information(self):
		print(f'name:{self.name}\nid:{self.id_}')

emp1=Employee('Aplha omega','SCP100',20)
emp1.display_information()
emp1.monthly_salary(2)



```

# Q9 list odd even

```python

lst=[_ for _ in range(1,20) ]
print(lst)
print( list
		(
			map
			(lambda x: x/2 if x%2==0 else x*2 ,lst
		)
	)
)



```
# Q10 analysis

```python

inp=input('Enter a string')
lst_aeiou=['a','e','i','o','u']
upper,lower,aeiou,not_aeiou,digit,space=0,0,0,0,0,0
for _ in inp:
	if _.isupper():
		upper+=1
	elif _.islower():
		lower+=1

	if _.lower() in lst_aeiou: 
		aeiou+=1
	elif _.lower() not in lst_aeiou and _.isalpha(): 
		not_aeiou+=1 

	if _.isdigit():
		digit+=1

	if _.isspace():
		space+=1

print(f"type count \nupper case {upper}\nlower case {lower}\nvowels {aeiou}\nconsonants {not_aeiou}\ndigits {digit}\nspace {space}" )





```
