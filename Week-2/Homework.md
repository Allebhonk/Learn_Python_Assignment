# HW2 Python

## Q1
```python
list_1 = [12, 35, 9, 56, 24]
print (list_1)
list_2 = list_1.copy()
list_1[0] = list_1[4]
list_1[4] = list_2[0]
print (list_1)
```

## Q2
```python
list_1 = [12, 35, 9, 56, 24, 79, 62, 32, 31, 100]
x = min(list_1)
y = max(list_1)

print("The smallest number is {} and the biggest is {}".format(x,y)) # printing the smallest and biggest numbers 

list_2 = list_1
list_2.remove(y) # removing largest number to find neext largest number
z = max(list_2)
print("The two largest numbers are {} and {}".format(y,z)) # printing 2 largest numbers
list_2.append(y)
list_3 = list_1.copy() #making a copy for sorting part
list_3.sort()
for i in range (2,6):
    list_1.sort()
print(list_1)
```

## Q3
```python
gift_list=['socks', '4K drone', 'wine', 'jam']
gift_list.append('cheese')
gift_list.remove('socks')
print(gift_list)
```

## Q4
```python
l = ["a","c","d","a","kk","k","c","stu","ta","she","kk","kk","d","g"]
x = []
y = 0 # for the counting no. of elements later
for i in l:
    if i not in x:
        x.append(i)
print("These are the unique elements {}".format(x))
for num in x:
    y = y+1
print("This is the no. of unique elements {}".format(y))
```

## Q5
```python
l = [1,8,90,70,1000,10,300,82,90]
add_tot = 0

for num in l:
    add_tot = add_tot + num # adds each element in the list to a variable
print("The sum of these numbers is {}".format(add_tot)) # prints the value

mul_tot = 1 # starts as 1 because it's a product not a sum
for num in l:
    mul_tot = mul_tot*num # multiplies the values
print("The product of these numbers is {}".format(mul_tot))  #prints it

even_sum = 0 # starts as 0 because it's a sum
for num in l:
    if (num % 2) == 0: # remainder if divided by 2 must equal to 0
        if (0<=num<=1000):
            even_sum = even_sum + num
print("The sum of the even numbers between 0 and 1000 is {}".format(even_sum))# prints it
```

## Q6
```python
l = [4, 6, 4, 3, 3, 4, 3, 4, 3, 8]
k = 3
frequency = {}
for num in l:
    if num in frequency: # for if numer already exists
        frequency[num] += 1
    else: # for new numbers
        frequency[num] = 1

        
print(frequency)
l = ([num for num in l if frequency[num] < k]) # removes all numbers whose frequency is greater than k
print(l)
```

## Q7
```python
nums = [12,7,11,15,20,18,3,2]
target = 9
for x in nums:
    for y in nums: # systematically goes through each number combination 
        if x+y==target:
            print(x,y) # prints correct number combinations to see them
```
