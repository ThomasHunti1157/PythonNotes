
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
      

number = input('Please input your number: ')
  7 
  8     number = int(number)
  9 
 10     if (number % 3 ==0) & (number % 5 ==0):
 11         print('fizzbuzz')
 12     elif number % 3==0:
 13         print('fizz')
 14     elif number % 5==0:
 15         print('buzz')
 16     else:
 17         print(str(number) + " is not divisible by 3 or 5.")

        
            FUNCTIONS
        
 -functions are used for a callback to make repetitive code much cleaner
        def nameoffunction():
            
            <code block>
            <you can use <pass> as a placeholder>
            
            <return> returns code from above statement feeds back up
 
           LOOPS
    
  
    FOR LOOPS
                
                my_list = ["tis", "is, "mu, "list"]
                
          for i in my_list:
              ^
           will cycle through each part of list (can be changed letters)
           
           range() function <start stop<will not hit that stop> step>
           to make range readable turn it into a list
           
           fori in range(0,10):
                print(i)
    WHILE LOOPS
           will continue looping until that conditional is false
            you can also use the break statement if neccesary to end the loop prematurely  
            
                
                print(i)

                
   1 #!/usr/bin/env python3
  2 
  3 def guess_number(n):
  4     while True:
  5         user = int(input("Enter number: "))
  6         if user > n:
  7             print("TOO HIGH")
  8         elif user < n:
  9             print("TOO LOW")
 10         else:
 11             print("WIN")
 12             return
 13 
 14 guess_number(23)

                            
 LIST SLICING SING A COLON
                          
    myList[0:10]   <will show the first 10 items
    myList[-10:]   <will show last 10>
    
                
   can also slice through strings
   myStr [::-1]  <shortcut to reverse whatever list your in>
   
                use colon for [start:stop:step]
         
  
    CHARACTERS
                
  myChr = 'a'
  ord(myChr)
  97
                
 ord only works on single value decimals.
      
can use <bin> on something to find the binary value of a given character.
                
                
                
bin(ord(myChr))
      '0b1100001'
format(ord(myChr), '0>8b')
      '01100001'
list(format(ord(myChr), '0>8b'))
                <lists out bytes in a list>
''.join(list(format(ord(myChr), '0>8b')))
      '01100001'
turn back into a character
      int(''.join(list(format(ord(myChr), '0>8b'))), 2)
                                                     ^
                                               Turn on base2
                   
               #!/usr/bin/env python3
 80 
 81 def steg_encode_char(char, cover):
 82 
 83      msgbin = format(ord(char),'0>8b')
 84      coverbin = format(int(cover[0]),'0>8b')
 85      coverbinl = list(coverbin)
 86 
 87      for i in range(0,8):
 88         coverbinl = list(format(int(cover[i]),'0>8b'))
 89         coverbinl[-1] = msgbin[i]
 90         cover[i] = str(int(''.join(coverbinl),base=2))
 91      pass
 92 
 93 def steg_decode_char(stego):
 94 
 95     pass
 96     msgbits = []
 97 
 98     for bits in stego:
 99             msgbits.append(bin(int(bits))[-1])
100 
101     return chr(int(''.join(msgbits),base=2))
102 
103 if __name__ == '__main__':
104     pass

                    
return chr(int(''.join([bin(int(b))[-1] for b in stego]),2))      <one liner>                    

                    
                    
                    
        FILE INPUT OUTPUT
          
 vim fileio.py
        
    fp = open('myfile.txt')
    fp.close()                 <fp stands for file pointer>
    python has a built in way to open and close files for oyu
                    
    with open('myfile.txt', 'r') as fp:
                             ^
                     stands for read
                    
    print(fp.read(<amount you want to read))
               ^
       will read the document as a huge string
                   
    other method called fp.readlines()
                              ^
                    every line is printed in a list
                          
                          
    with open('myfile.txt', 'w') as fp:
    fp.write('This is my new fil. But whre are the newlines?\n')   <have to add new lines>
                    
    fp.writelines('This\n' 'is\n', etc...)
                   
    copying a file
                    
    with open('myfile.txt', 'r') as fp0:
                    with open('newfile.txt', 'w') as fp1:
                        fp1.write(fp0.read())
                    
                    
     with open('school_prompt.txt', 'r') as fp:
    words = fp.read().split()
    p_words = [word for word in words if 'p' in word]
