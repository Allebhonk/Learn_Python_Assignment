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

