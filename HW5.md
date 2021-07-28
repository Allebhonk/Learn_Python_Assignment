#HW 5

## Q1
```python
def stringToInt(string):
    """
    input type: str 
    return type: int
    """
    sign = 1 # The sign is what determines whether the value is positive or negative
    index = 0 # Determines how many signs or 0's are before the number
    if(string[0]=='+'): 
        index = index+1 # If the first value in the string is equal to '+', it adds 1 to index
    elif(string[0]=='-'):
        index = index+1 # Else, if the first value in the string is equal to '-', it adds 1 to index
        sign = -1
    while(string[index]=='0'):
        index = index+1 # As long as the string starts with 0's it keeps adding 1 to index
    
    sum_val = 0 # A variable for the final value
    for i in range(index,len(string)): # Counts in range between index and the length of the string to skip all the 0's and symbols
        sum_val = sum_val*10 + int(string[i]) # counts from left to right so it multiplies by 10 then adds the next digit
    return sign*sum_val # returns the sum_value multiplied by the sign to correct whether the value is positive or negative.

s = "-000123"
print(stringToInt(s))
##print(stringToInt(s))
```

## Q2
```python
def removeDuplicate(l):
    """
    input type: list
    return type: list
    """
    record = {} ## to record duplicate
    new_l = []  # The new list for unique values
    for i in range(len(l)):
        if l[i] in record: 
            continue # If the value is in in record, this does nothing
        else:
            record[l[i]] = 1 
            new_l.append(l[i]) # If the value isn't in record, it adds the value to the new list
    
    return new_l # Returns the new list

l = [1,2,3,3,3,3,4,5]
print(removeDuplicate(l))
```

## Q3
```python
def checkPalindrome(string):
    """
    input type: str
    return type:bool
    """
    half = int(len(string)/2) # Gets a number equal to half the length of the list
    for i in range(half):
        if(string[i]!=string[len(string)-1-i]): # for the range hald of the list, if the front of the list is not equal to the back then return false
            return False
    return True # If the above isn't false then it will return true

a = "cabac" 
print(checkPalindrome(a))
b = "abc"
print(checkPalindrome(b))
```

## Q4
```python
def majorityElement(nums):
    """
    input type: list
    return type: int
    """
    result = nums[0]
    times = 1 # default answer is the first value and it's conuted as repeated once
    for i in range(1,len(nums)):
        if (times==0): # if the no of times becomes 0 that means the other value has equal amount to the first value so it swaps.
            result = nums[i]
            times = 1
        elif nums[i] == result: # if the number if the same as the result. add one to the no. of times
            times += 1
        else: # if it isn't, subtract one
            times -= 1
    
    return result
l = [2,2,1,1,1,2,2]
print(majorityElement(l))

# Code doesn't work when there's an equal frequency
m = [2,2,1,1,1,2,2,1] # equal frequency
print(majorityElement(m))

n = [2,2,1,1,1,2,3] # equal frequency on two values then an extra third value
print(majorityElement(n))
```

## Q5
```python
class Student:
    def __init__(self,stu_id,stu_name,stu_class): # defines the class and creates variables for the input values
        self.stu_id = stu_id
        self.stu_name = stu_name
        self.stu_class = stu_class
        
    def __str__(self):
        return "student: id={},name={},class={}".format(self.stu_id,self.stu_name,self.stu_class) # Defines what to return when the class is being called

       

stu = Student(10010,"davis","Class two")
print(stu)
```

## Q6
```python
class Rectangle:
    def __init__(self,length,width): # Defined the class and sets the variables
        self.length = length
        self.width = width
    
    def __str__(self): # Defines what to return when just the object is being called.
        return "length:{}   width:{}".format(self.length,self.width)
    
    def area(self): # Defines the functionto get the area
        return self.length*self.width
    
    def perimeter(self): # defined the function to get the perimeter
        return 2*(self.length+self.width)
    
rect = Rectangle(4,5)
print(rect.area())
print(rect)
print(rect.perimeter())
```
