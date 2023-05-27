
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
                    
                    
                    
    convert number to binary without leading zeros life hack
                    
    def add_binary(a,b):
    num = str(format((a + b), '0>8b'))
    num = num.lstrip('0')
    
    return num
                    
                    
    return first and last of list
                    
    def min_max(nums):
    return [min(nums), max(nums)]
                    
                    
    Prac Exam Uno
                    
                    
    def josephus_permutation(items, k):
    if not items:
        return []

    n = len(items)
    result = []
    index = 0

    while n > 0:
        index = (index + k - 1) % n  # Calculate the index to remove based on circular counting
        result.append(items.pop(index))  # Remove and add the item to the result
        n -= 1

    return result
                
    1 #!/usr/bin/env python3
  2 def invert(l):
  3     '''Inverts the given list
  4     Args:
  5         l (list): list of strings representing integers in the range [0-255]
  6     Returns:
  7         None
  8     '''
  9     counter = 0
 10     for pixel in l:
 11         l[counter] = str(255 -int(pixel))
 12         counter += 1
 13     return
 14 def inverted(l):
 15     '''Returns a new list that is the given list inverted
 16     Args:
 17         l (list): list of strings representing integers in the range [0-255]
 18     Returns:
 19         list: new list that is the given list inverted
 20     '''
 21     
 22     newlst = []
 23     counter = 0
 24     for pixel in l:
 25         newlst.append(l[counter])
 26         counter += 1
 27     invert(newlst)
 28     return newlst
 29 
 30 
 31 if __name__ == '__main__':
 32     pass



 #!/usr/bin/env python3
  2 
  3 def steg_encode_char(char, cover):
  4     '''LSB encodes a character
  5     Args:
  6         char (str): a single character string
  7         cover (list): list of 8 strings representing integers in the range [0-255]
  8     Returns:
  9         None
 10     '''
 11     pass
 12     msgbin = format(ord(char), '0>8b')
 13     #coverbin = format(int(cover[0]),'0>8b')
 14     #coverbinl= list(coverbin)
 15     for i in range(0,8):
 16         coverbinl = list(format(int(cover[i]), '0>8b'))
 17         coverbinl[-1] = msgbin[i]
 18         cover[i] = str(int(''.join(coverbinl), base = 2))
 19 
 20 def steg_decode_char(stego):
 21     '''LSB decodes a character
 22     Args:
 23         stego (list): list of 8 strings representing integers in the range [0-255]
 24     Returns:
 25         str: character that was decoded
 26     '''
 27     pass
 28     msgbits = []
 29     for bits in stego:
 30         msgbits.append(bin(int(bits))[-1])
 31     return chr(int(''.join(msgbits),base=2))
 32 
 33 
 34 if __name__ == '__main__':
 35     pass
~    


Challenge: Using the file school_prompt.txt, if the character ‘p’ is in a word, then add the word to a list called p_words.

   with open('school_prompt.txt', 'r') as fp:
    words = fp.read().split()
    p_words = []
    for word in words:
            if 'p' in word:
                p_words.append(word)
  PRACTICE EXAM
  1 #!/usr/bin/env python3
  2 
  3 def q1(floatstr):
  4     '''
  5     TLO: 112-SCRPY002, LSA 3,4
  6     Given the floatstr, which is a comma separated string of
  7     floats, return a list with each of the floats in the 
  8     argument as elements in the list.
  9     '''
 10     pass
 11     floatstr = floatstr.split(',')
 12     for f in range(0,len(floatstr)):
 13         floatstr[f] = float(floatstr[f])
 14     return floatstr
 15 def q2(*args):
 16     '''
 17     TLO: 112-SCRPY006, LSA 3
 18     TLO: 112-SCRPY007, LSA 4
 19     Given the variable length argument list, return the average
 20     of all the arguments as a float
 21     '''
 22     return (sum(args) / len(args))
 23     pass
 24 
 25 def q3(lst,n):
 26     '''
 27     TLO: 112-SCRPY004, LSA 3
 28     Given a list (lst) and a number of items (n), return a new 
 29     list containing the last n entries in lst.
 30     '''
 31     newlst = []
 32     while n > 0:
 33         newlst.append(lst[-1*n])
 34         n -= 1
 35     return newlst
 36     pass
 37 
 38 def q4(strng):
 39     '''
 40     TLO: 112-SCRPY004, LSA 1,2
 41     TLO: 112-SCRPY006, LSA 3
 42     Given an input string, return a list containing the ordinal numbers of 
 43     each character in the string in the order found in the input string.
 44     '''
 45     new = []
 46     for s in strng:
 47         n = ord(s)
 48         new.append(n)
 49     return new
 50     pass
 51 
 52 def q5(strng):
 53     '''
 54     TLO: 112-SCRPY002, LSA 1,3
 55     TLO: 112-SCRPY004, LSA 2
 56     Given an input string, return a tuple with each element in the tuple
 57     containing a single word from the input string in order.
 58     '''
 59     strng = strng.split()
 60     strng = tuple(strng)
 61     return strng
 62     pass
 63 
 64 def q6(catalog, order):
 65     '''
 66     TLO: 112-SCRPY007, LSA 2
 67     Given a dictionary (catalog) whose keys are product names and values are product
 68     prices per unit and a list of tuples (order) of product names and quantities,
 69     compute and return the total value of the order.
 70 
 71     Example catalog:
 72     {
 73         'AMD Ryzen 5 5600X': 289.99,
 74         'Intel Core i9-9900K': 363.50,
 75         'AMD Ryzen 9 5900X': 569.99
 76     }
 77 
 78     Example order:
 79     [
 80         ('AMD Ryzen 5 5600X', 5), 
 81         ('Intel Core i9-9900K', 3)
 82     ]
 83 
 84     Example result:
 85     2540.45 
 86 
 87     How the above result was computed:
 88     (289.99 * 5) + (363.50 * 3)
 89     '''
 90     total = 0
 91     print(catalog)
 92     print(order)
 93     numofitems = (len(order))
 94     print(numofitems)
 95     for n in range(0,numofitems):
 96         #grabs the tuple of the order of n 
 97         orde = order[n]
 98         print (orde)
 99         #grabs the name of the item
100         item1 = orde[0]
101         #grabs cost of the item 
102         cost1 = orde[1]
103         ord1p = catalog[item1]
104         print(ord1p)
105         over1p = ord1p * cost1
106         total += over1p
107 
108 
109     return total
110     pass
111 
112 def q7(filename):
113     '''
114     TLO: 112-SCRPY005, LSA 1
115     Given a filename, open the file and return the length of the first line 
116     in the file excluding the line terminator.
117     '''
118     with open(filename, 'r') as fp:
119         line = fp.readlines()[0]
120         line = list(line)
121         num = len(line) - 1
122         return num
123     pass
124 
125 def q8(filename,lst):
126     '''
127     TLO: 112-SCRPY003, LSA 1
128     TLO: 112-SCRPY004, LSA 1,2
129     TLO: 112-SCRPY005, LSA 1
130     Given a filename and a list, write each entry from the list to the file
131     on separate lines until a case-insensitive entry of "stop" is found in 
132     the list. If "stop" is not found in the list, write the entire list to 
133     the file on separate lines.
134     '''
135 
136     with open(filename, 'w') as fp:
137         for n in lst:
138             if n is 'stop':
139                 break
140             fp.write(n + '\n')
141     pass
142 
143 def q9(miltime):
144     '''
145     TLO: 112-SCRPY003, LSA 1
146     Given the military time in the argument miltime, return a string 
147     containing the greeting of the day.
148     0300-1159 "Good Morning"
149     1200-1559 "Good Afternoon"
150     1600-2059 "Good Evening"
151     2100-0259 "Good Night"
152     '''
153     miltime = int(miltime)
154     if miltime >= 300 and miltime < 1200:
155         return 'Good Morning'
156     elif miltime >= 1200 and miltime < 1600:
157         return 'Good Afternoon'
158     elif miltime >= 1600 and miltime < 2100:
159         return 'Good Evening'
160     else:
161         return 'Good Night'
162     pass
163 
164 def q10(numlist):
165     '''
166     TLO: 112-SCRPY003, LSA 1
167     TLO: 112-SCRPY004, LSA 1
168     Given the argument numlist as a list of numbers, return True if all 
169     numbers in the list are NOT negative. If any numbers in the list are
170     negative, return False.
171     '''
172     pos = True
173     for n in numlist:
174         if n < 0:
175             pos = False
176 
177     return pos
178     pass
179 

                              
 
