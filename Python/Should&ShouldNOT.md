Source: http://safehammad.com/downloads/python-idioms-2014-01-16.pdf

<table>
<tr>
<th>Don't Write This:</th>
<th>Write This:</th>
</tr>
<tbody>
<tr>
<td>
```python
my_container = ['Larry', 'Moe', 'Curly']
index = 0
for element in my_container:
    print ('{} {}'.format(index, element))
    index += 1
```
</td>
<td>
```python
my_container = ['Larry', 'Moe', 'Curly']
for index, element in enumerate(my_container):
    print ('{} {}'.format(index, element))
```
</td>
</tr>
<tr>
<td>
```python
if name != '' and len(pets) > 0 and owners != {}:
    print('We have pets!')

```
</td>
<td>
```python
 name = 'Safe'
 pets = ['Dog', 'Cat', 'Hamster']
 owners = {'Safe': 'Cat', 'George': 'Dog'}
 if name and pets and owners:
    print('We have pets!')
```
</td>
</tr>
<tr> 
<td>
```python
 name = 'Safe Hammad'
 if name.find('H') != -1:
    print('This name has an H in it!')
```
</td>
<td> 
```python
 name = 'Safe Hammad'
 if 'H' in name:
    print('This name has an H in it!')
```
</td>
</tr>
<tr>
<td>
```python
 pets = ['Dog', 'Cat', 'Hamster']
 i = 0
 while i < len(pets):
    print('A', pets[i], 'can be very cute!')
    i += 1
```
</td>
<td>
```python
 pets = ['Dog', 'Cat', 'Hamster']
 for pet in pets:
    print('A', pet, 'can be very cute!')
```
</td>
</tr>
<tr>
<td>
```python
 a, b = 5, 6
 print(a, b) # 5, 6

 temp = a
 a = b
 b = temp
 print(a, b) # 6, 5

```
</td>
<td>
```python
 a, b = 5, 6
 print(a, b) # 5, 6
 a, b = b, a
 print(a, b) # 6, 5

```
</td>
</tr>
<tr>
<td>
```python
 chars = ['S', 'a', 'f', 'e']
 name = ''
 for char in chars:
    name += char
    print(name) # Safe

```
</td>
<td>
```python
 chars = ['S', 'a', 'f', 'e']
 name = ''.join(chars)
 print(name) # Safe

```
</td>
</tr>
<tr>
<td>
```python
 d = {'x': '5'}
 if 'x' in d and isinstance(d['x'], str) and \
 d['x'].isdigit():
    value = int(d['x'])
 else:
    value = None
```
</td>
<td>
```python
 d = {'x': '5'}
 try:
    value = int(d['x'])
 except (KeyError, TypeError, ValueError):
    value = None
```
</td>
</tr>
<tr>
<td>
```python
 data = [7, 20, 3, 15, 11]
 result = []
 for i in data:
    if i > 10:
        result.append(i * 3)
 print(result) # [60, 45, 33]

```
</td>
<td>
```python
 data = [7, 20, 3, 15, 11]
 result = [i * 3 for i in data if i > 10]
 print(result) # [60, 45, 33]

```
</td>
</tr>
<tr>
<td>
```python
 keys = ['Safe', 'Bob', 'Thomas']
 values = ['Hammad', 'Builder', 'Engine']
 d = {}
 for i, key in enumerate(keys):
    d[keys] = values[i]
 print(d) # {'Bob': 'Builder',
            'Safe': 'Hammad',
            'Thomas': 'Engine'}
```
</td>
<td>
```python
 keys = ['Safe', 'Bob', 'Thomas']
 values = ['Hammad', 'Builder', 'Engine']
 d = dict(zip(keys, values))
 print(d) # {'Bob': 'Builder',
            'Safe': 'Hammad',
            'Thomas': 'Engine'}
```
</td>
</tr>
<tr>
<td>

</td>
<td>
```python
 while True:
 break # This will spark discussion!!!
● Generators and generator expressions.
● Avoid from module import *
Prefer: import numpy as np; import pandas as pd
● Use _ for “throwaway” variables e.g.:
for k, _ in [('a', 1), ('b', 2), ('c', 3)]
● dict.get() and dict.setdefault()
● collections.defaultdict
● Sort lists using l.sort(key=key_func)
● Avoid comparing directly to True, False, or None
```
</td>
</tr>
<tr>
<td>
```python
is_generic_name = False
name = 'Tom'
if name == 'Tom' or name == 'Dick' or name == 'Harry':
    is_generic_name = True
```
</td>
<td>
```python
name = 'Tom'
is_generic_name = name in ('Tom', 'Dick', 'Harry')
```
</td>
</tr>
<tr>
<td>

</td>
<td>

</td>
</tr>
<tr>
<td>

</td>
<td>

</td>
</tr>
<tr>
<td>

</td>
<td>

</td>
</tr>
<tr>
<td>

</td>
<td>

</td>
</tr>
<tr>
<td>

</td>
<td>

</td>
</tr>
<tr>
<td>

</td>
<td>

</td>
</tr>
</tbody>



