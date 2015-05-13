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
</tbody>



