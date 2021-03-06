### Getting argument through command line

```
import sys

arg1 = sys.argv[1]
arg2 = sys.argv[2]
```

### Getting current directory

```
import os

path = os.getcwd()
```

### Reversing a list

```
def ListReverse(List):
	
	temp = List
	temp = temp[::-1]
	return temp
```

***sometimes reverse() doesn't work*** <br>

### Switching the keys and values of a dictionary

```
def Switch_KeysVals(dictionary):
	new_dict = {y:x for x,y in dictionary.iteritems()}
	return new_dict
```

### Generatign a dictionary with keys from a given list

```
def DictFromKeyList(List):
	newdict = dict((element,None) for element in List)
	return newdict
```

### Difference between list methods append and extend (very important):

**Easier just to go to the link:**
http://stackoverflow.com/questions/252703/python-append-vs-extend

###Deleting something from a string / stripping (Useful for removing linebreaks(\n))

```
str = "ABCWhateveR\nWhateverAgaiN\n"
str.replace("\n","")
>>"ABCWhateveRWhateverAgaiN"
```

*** split() can also be used, but in some cases it can't delete the linebreaks. Such as, after reading a file and splitting it by something (let's say semicolon), then trying to split it. If there were linebreaks before a semicolon it won't remove the linebreaks. *** <br>

###Implementing enum (similar to enum in Java)

```
def enum(**enums):
  return type('Enum', (), enums)
```
**Usage:** <br>
```
Connectives = enum(AND=1, OR=2, IMPLIES=3, IFF=4, NOT=5)
Connectives.AND
>> 1
Connectives.NOT
>> 5
```
**To automatically increase the numbers:**<br>
```
def enum(**sequential, **named):
  enums = dict(zip(sequential, range(len(sequential))), **named)
  return type('Enum', (), enums)
```
**Usage:**
```
Connectives = enum(AND, OR, IMPLIES, IFF, NOT)
Connectives.AND
>> 0
Connectives.OR
>>1
```

Ref:<br>
http://stackoverflow.com/questions/36932/how-can-i-represent-an-enum-in-python
http://stackoverflow.com/questions/8305518/switching-keys-and-values-in-a-dictionary-in-python
http://stackoverflow.com/questions/3869487/how-do-i-create-a-dictionary-with-keys-from-a-list-and-values-defaulting-to-say
