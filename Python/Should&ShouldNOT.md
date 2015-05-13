Source: http://safehammad.com/downloads/python-idioms-2014-01-16.pdf
http://images.immobilien.de/expose/00/04/04/36/0004043615/etc248188603/writing_idiomatic_python_3.pdf

-----------------
* **Don't Write This:**
```python 
my_container = ['Larry', 'Moe', 'Curly']
index = 0
for element in my_container:
    print ('{} {}'.format(index, element))
    index += 1
```
* **Write This:**
```python
my_container = ['Larry', 'Moe', 'Curly']
for index, element in enumerate(my_container):
    print ('{} {}'.format(index, element))
```
--------------
* **Don't Write This:**
```python
if name != '' and len(pets) > 0 and owners != {}:
    print('We have pets!')

```
* **Write This:**
```python
 name = 'Safe'
 pets = ['Dog', 'Cat', 'Hamster']
 owners = {'Safe': 'Cat', 'George': 'Dog'}
 if name and pets and owners:
    print('We have pets!')
```
<table>
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

</table>



