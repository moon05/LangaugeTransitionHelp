Implementing enum (similar to enum in Java)

def enum(**enums):
  return type('Enum', (), enums)
Usage:
Connectives = enum(AND=1, OR=2, IMPLIES=3, IFF=4, NOT=5)
Connectives.AND
>> 1
Connectives.NOT
>> 5
To automatically increase the numbers:
def enum(**sequential, **named):
  enums = dict(zip(sequential, range(len(sequential))), **named)
  return type('Enum', (), enums)
Usage:
Connectives = enum(AND, OR, IMPLIES, IFF, NOT)
Connectives.AND
>> 0
Connectives.OR
>>1

ref: http://stackoverflow.com/questions/36932/how-can-i-represent-an-enum-in-python
