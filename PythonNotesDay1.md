
    Python Day 1 

-python is an interpreter (can also be ocmpiled)
-human readable (booleans etc...)
-can store variables
-commonly use vim over nano sinceit is more common on linux systems to edit text.
-

def makedeck):
  deck = []
  suits = ['\u2660', '\u2665']
  ranks = [A" , 2, 3, 4, 5, 6, 7, 8, 9]for suit in ranks"
    for ranks in ranks:
      deck.append ()
     print
     
makedeck()



-remember to add '#!/usr/bin/python3' before scripts to run in this exact language

-to run script add './' before script in command prompt
-Learn to read python in the python documentation. "docs.python.org/'version'/"

      TYPES
      
find type "type(variable)"

muteable - cant change, immuteable = can change (such as changing items in a list). any variable that is able to be changed is immuteable

typecasting = changing the typ of a variable efore eing presented. 

c = 7.4
d = str(c)
d = '7.4' (turned it into a string)

str() float() list() dict() etc...

      LISTS
      
-lists can contain different types as long as they are abbreviated correctly
a = [1,2,3,4]
a[0]
1
a[-1] (takes te last form a list)
4
  modify
  
a[0] = 6
a[6,2,3,4]

muteable = changing but remains in the same id space. immuteable such as a variable will comepletely chan ge that id memory space.

  append from a list

a.append(7) (adds to the end of the list)
del a[index]


    TOUPLES
    
instead of brackets use parantheses
t = (1,2,3,4)
are able to call on certain indexes, but cannot change objects in the list. 

    MATH IN PYTHON<indented code bloc
    
difference between int division and float division is / or //

modulus  is the %  sign 
best use of this is to determine if it is odd or not by modulo by 2.

    FORMAT
  
different types of formating 

'Hello. My name is {}.'.format('Whatever You want to put such as variables a or b)

or

f'Hello. My name is {} {}.'


    SPLIT and JOIN
    
'helo world'.split()
['hello', 'world']

'user:passwd'.split(':')
['user', 'passwd']



to split a word typecast it into a list

use the join to join letters back into a word 
x = ['h', 'e', 'l', 'l', 'o']
''.join(x)
'hello'


the join function jins by the desired character 

    INPUT
    
 name = input('enter a name: ')
 going to be input as a string will have to typecast for further work
 
Day1Excercise Code

\#!/usr/bin/python3
  2 
  3 email = input('Please input your email:')
  4 
  5 
  6 name, secondhalf = email.split('@')
  7 middle, end = secondhalf.split('.')
  8 emaillist = [name, middle, end]
  9 
 10 print(emaillist)

or

email = name@domain.com

lst = '.'.join(email.split('@')).split('.')

print(lst)

    IF ELSE IF ELSE
    
-else is an ending that will help end a condition if it does not match any others.
-elif are middle statements that can be added multiple times in order to gate through statements.

if <condition>:
    <indented code block>
elif <condition>
    <indented code block>
else: <condition>
    <indented code block>
      
-
