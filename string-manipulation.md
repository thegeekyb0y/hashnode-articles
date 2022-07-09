## String Manipulation In Python : Part 1

Hey python programmers, I am *Aditya Tiwari* ,  *web developer also learning backend*, welcome you to today's blog. Assuming that you know *what are strings and its basic operations* In Python, lets deep dive into strings and learn some awesome string manipulation techniques.

### 1. String Slices

In Python, string slice is a term which refers to a part of the string, where strings are sliced using a range of indices.

**Syntax** : string[n:m] , where n and m are integers.
Python will return a slice of the string by returning the characters falling between indices n and m - starting at n,n+1,n+2,n+3......till m-1.

For example: Take a word , let 'Aditya' , lets do string slicing of it. This is the pattern of numbering in each word.


> 0  1  2  3  4  5 : A  D  I  T  Y  A

>-6 -5 -4 -3 -2 -1 :  A D  I   T  Y   A



Then, play wth your code :)


```
name = 'aditya'
print(name[0:5])
print(name[1:5])
print(name[3:4])
print(name[-6:5])
print(name[-4:-1])

# Output 
#adity
#dity
#t
#adity
#ity

``` 

Note that: You can skip either begin-index (n) or last(m), python will consider the limits of the string i.e. for missing begin-index(M),  it will consider 0 for first index and for missing last value , it will consider the length of the string.

> Pro tip: You can use string[: : -1] to reverse a string.

### 2. The len() function

It returns the length of its argument string, length, in the sense, characters present in that string.

```
name = 'aditya'
print(len(name))

# Output: 6
``` 

### 3. The count() function
It returns the integer of how many times a particular word, group of words have occured in the argumented string.


```
name = 'aditya'
print(name.count('a'))

#output : 2

name = ' 121112111211'
print(name.count('1'))

#output: 9
``` 

### 4. find() function
It returns the lowest index in the string where the substring is found within the slice range of start and end. It will return -1 if substring is not found.

```
<string>.find(sub[,start[,end]])
``` 


``` 
string = 'I love Python'
print(string.find('love'))
``` 

### 5. index() function
It returns the lowest index where the specified substring is found. If the substring is not found then an exception, *Value error* is raised.

It is similar to find(), but find() returns -1 if substring is not found, whereas index() will raise *Value error * if the substring is not found in string.

```
>>> 'abracadabra'.index('ab')
0
``` 
You must have observed it returned 0, why ?
index() or find() always returns the lowest index of the substring, if there are more than 1 indexes of same substring.

### 6. replace() method
As the name says, it will return a copy of the string with all occurences of old substring replaced by a new one. 
```
#syntax
<string>.replacable(old,new)
``` 

```
s=' I love Javascript'
print(s.replace('Javascript','Python'))

#output: I love Python
``` 

### 7. join() function
It joins a string or character after each member if the string iterator i.e. string based sequence.


```
#syntax
<string>.join(<string iterable>)
``` 

```
>>> '#'.join('Python)
P#y#t#h#o#n
``` 
### 8. capitalize() function

It will return as a copy of the string with its first letter capitalized.

```
#syntax
<string>.capitalize()
``` 

```
>>> 'aditya'.capitalize
#output : Aditya
``` 
### 9. title() function

It will return a copy of the string where all words will start with uppercase characters and other characters will be in lowercase. It is different from capitalize function because capitalize function returns with first letter in uppercase while title will make first letter uppercase for all words in the string,


```
s = 'i love python'
print(s.title)

#output : I Love Python
```
Thats pretty much for today' blog, meet you in part 2 of this blog. I hope this blog helped you. 
Follow me on twitter to get awesome information , i daily share, on Python programming.
 [Click here to Join me on twitter](https://twitter.com/thegeekyb0y) 
