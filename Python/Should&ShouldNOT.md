Source: http://safehammad.com/downloads/python-idioms-2014-01-16.pdf
http://images.immobilien.de/expose/00/04/04/36/0004043615/etc248188603/writing_idiomatic_python_3.pdf

1. Enumerate
------
 
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
2. Test for *`True`* and *`False`* values
------
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
3. Use `in` where possible
------
* **Don't Write This:**
```python
 name = 'Safe Hammad'
 if name.find('H') != -1:
    print('This name has an H in it!')
```
* **Write This:**
```python
 name = 'Safe Hammad'
 if 'H' in name:
    print('This name has an H in it!')
```
4. Use `in` where possible
------
* **Don't Write This:**
```python
 pets = ['Dog', 'Cat', 'Hamster']
 i = 0
 while i < len(pets):
    print('A', pets[i], 'can be very cute!')
    i += 1
```
* **Write This:**
```python
 pets = ['Dog', 'Cat', 'Hamster']
 for pet in pets:
    print('A', pet, 'can be very cute!')
```
5. Swap values without `temp` variable
------
* **Don't Write This:**
```python
 a, b = 5, 6
 print(a, b) # 5, 6

 temp = a
 a = b
 b = temp
 print(a, b) # 6, 5

```
* **Write This:**
```python
 a, b = 5, 6
 print(a, b) # 5, 6
 a, b = b, a
 print(a, b) # 6, 5

```
6. Build strings using sequence
------
* **Don't Write This:**
```python
 chars = ['S', 'a', 'f', 'e']
 name = ''
 for char in chars:
    name += char
    print(name) # Safe

```
* **Write This:**
```python
 chars = ['S', 'a', 'f', 'e']
 name = ''.join(chars)
 print(name) # Safe

```
7. `Try...exception` is better than check for specific type
------
* **Don't Write This:**
```python
 d = {'x': '5'}
 if 'x' in d and isinstance(d['x'], str) and \
 d['x'].isdigit():
    value = int(d['x'])
 else:
    value = None
```
* **Write This:**
```python
 d = {'x': '5'}
 try:
    value = int(d['x'])
 except (KeyError, TypeError, ValueError):
    value = None
```
8. Build lists using list comprehensions (except the second form can be clearer)
------
* **Don't Write This:**
```python
 data = [7, 20, 3, 15, 11]
 result = []
 for i in data:
    if i > 10:
        result.append(i * 3)
 print(result) # [60, 45, 33]

```
* **Write This:**
```python
 data = [7, 20, 3, 15, 11]
 result = [i * 3 for i in data if i > 10]
 print(result) # [60, 45, 33]

```
9. Create dict from keys and values using `zip`
------
* **Don't Write This:**
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
* **Write This:**
```python
 keys = ['Safe', 'Bob', 'Thomas']
 values = ['Hammad', 'Builder', 'Engine']
 d = dict(zip(keys, values))
 print(d) # {'Bob': 'Builder',
            'Safe': 'Hammad',
            'Thomas': 'Engine'}
```
10. Avoid repeating variable `name` in compound `if` statement
------
* **Don't Write This:**
```python
is_generic_name = False
name = 'Tom'
if name == 'Tom' or name == 'Dick' or name == 'Harry':
    is_generic_name = True
```
* **Write This:**
```python
name = 'Tom'
is_generic_name = name in ('Tom', 'Dick', 'Harry')
```
11. Use `else` to execute code after a `for` loop concludes
------
* **Don't Write This:**
```python
for user in get_all_users():
    has_malformed_email_address = False
    print ('Checking {}'.format(user))
    for email_address in user.get_all_email_addresses():
        if email_is_malformed(email_address):
            has_malformed_email_address = True
            print ('Has a malformed email address!')
            break
    if not has_malformed_email_address:
        print ('All email addresses are valid!')

```
* **Write This:**
```python
for user in get_all_users():
    print ('Checking {}'.format(user))
    for email_address in user.get_all_email_addresses():
        if email_is_malformed(email_address):
            print ('Has a malformed email address!')
            break
    else:
        print ('All email addresses are valid!')
```

13. Use `*args` and `**kwargs` to accept arbitrary arguments
--------------------
* **Don't Write This:**
```python
def make_api_call(foo, bar, baz):
	if baz in ('Unicorn', 'Oven', 'New York'):
		return foo(bar)
	else:
		return bar(foo)
# I need to add another parameter to `make_api_call`
# without breaking everyone's existing code.
# I have two options...
def so_many_options():
 # I can tack on new parameters, but only if I make
 # all of them optional...
def make_api_call(foo, bar, baz, qux=None, foo_polarity=None,
                 baz_coefficient=None, quux_capacitor=None,
                 bar_has_hopped=None, true=None, false=None,
                 file_not_found=None):
	# ... and so on ad infinitum
 	return file_not_found
def version_graveyard():
# ... or I can create a new function each time the signature
# changes.
	def make_api_call_v2(foo, bar, baz, qux):
		return make_api_call(foo, bar, baz) - qux
	def make_api_call_v3(foo, bar, baz, qux, foo_polarity):
		if foo_polarity != 'reversed':
			return make_api_call_v2(foo, bar, baz, qux)
		return None
	def make_api_call_v4(foo, bar, baz, qux, foo_polarity, baz_coefficient):
		return make_api_call_v3(foo, bar, baz, qux, foo_polarity) * baz_coefficient
	def make_api_call_v5(foo, bar, baz, qux, foo_polarity, baz_coefficient, quux_capacitor):
		# I don't need 'foo', 'bar', or 'baz' anymore, but I have to
		# keep supporting them...
		return baz_coefficient * quux_capacitor
```
* **Write This:**
```python
def make_api_call(foo, bar, baz):
	if baz in ('Unicorn', 'Oven', 'New York'):
		return foo(bar)
	else:
		return bar(foo)
# I need to add another parameter to `make_api_call`
# without breaking everyone's existing code.
# Easy...
def new_hotness():
	def make_api_call(foo, bar, baz, *args, **kwargs):
		# Now I can accept any type and number of arguments
		# without worrying about breaking existing code.
		baz_coefficient = kwargs['the_baz']
		# I can even forward my args to a different function without
		# knowing their contents!
		return baz_coefficient in new_function(args)
```
14. Use the `*` operator to represent the “rest, middle, head” of a list
--------------------
* **Don't Write This:**
```python
some_list = ['a', 'b', 'c', 'd', 'e']
(first, second, rest) = some_list[0], some_list[1], some_list[2:]
print(rest)
(first, middle, last) = some_list[0], some_list[1:-1], some_list[-1]
print(middle)
(head, penultimate, last) = some_list[:-2], some_list[-2], some_list[-1]
print(head)

```
* **Write This:**
```python
some_list = ['a', 'b', 'c', 'd', 'e']
(first, second, *rest) = some_list
print(rest)
(first, *middle, last) = some_list
print(middle)
(*head, penultimate, last) = some_list
print(head)
```
15. `dict.get` to provide default values
--------------------
* **Don't Write This:**
```python
log_severity = None
if 'severity' in configuration:
	log_severity = configuration['severity']
else:
	log_severity = 'Info'

```
* **Write This:**
```python
log_severity = configuration.get('severity', 'Info')
```
16. Use a `dict comprehension` to build a `dict` clearly and efficiently
--------------------
* **Don't Write This:**
```python
user_email = {}
for user in users_list:
	if user.email:
		user_email[user.name] = user.email

```
* **Write This:**
```python
user_email = {user.name: user.email for user in users_list if user.email}	
```
17. Prefer the `format` function for formatting strings
--------------------
* **Don't Write This:**
```python
def get_formatted_user_info_worst(user):
	# Tedious to type and prone to conversion errors
	return 'Name: ' + user.name + ', Age: ' + str(user.age) + ', Sex: ' + user.sex
def get_formatted_user_info_slightly_better(user):
	# No visible connection between the format string placeholders
	# and values to use. Also, why do I have to know the type?
	# Don't these types all have __str__ functions?
	return 'Name: %s, Age: %i, Sex: %c' % (user.name, user.age, user.sex)

```
* **Write This:**
```python
def get_formatted_user_info(user):
# Clear and concise. At a glance I can tell exactly what
# the output should be. Note: this string could be returned
# directly, but the string itself is too long to fit on the
# page.
	output = 'Name: {user.name}, Age: {user.age}, Sex: {user.sex}'.format(user=user)
	return output
```
18. Chain `string` functions to make a simple series of transformations more clear
--------------------
* **Don't Write This:**
```python
book_info = ' The Three Musketeers: Alexandre Dumas'
formatted_book_info = book_info.strip()
formatted_book_info = formatted_book_info.upper()
formatted_book_info = formatted_book_info.replace(':', ' by')

```
* **Write This:**
```python
book_info = ' The Three Musketeers: Alexandre Dumas'
formatted_book_info = book_info.strip().upper().replace(':', ' by')
```
19. Define `__str__` in a class to show a human-readable representation
--------------------
* **Don't Write This:**
```python
class Point():
	def __init__(self, x, y):
		self.x = x
		self.y = y
p = Point(1, 2)
print (p)
# Prints '<__main__.Point object at 0x91ebd0>'
```
* **Write This:**
```python
class Point():
	def __init__(self, x, y):
		self.x = x
		self.y = y
	def __str__(self):
		return '{0}, {1}'.format(self.x, self.y)
p = Point(1, 2)
print (p)
# Prints '1, 2'
```



12. 
------
* **Write This:**
```python
 while True:
  break # This will spark discussion!!!
```  
* Generators and generator expressions.
* Avoid from module import *
 Prefer: import numpy as np; import pandas as pd
* Use _ for “throwaway” variables e.g.:
for k, _ in [('a', 1), ('b', 2), ('c', 3)]
* dict.get() and dict.setdefault()
* collections.defaultdict
* Sort lists using l.sort(key=key_func)
* Avoid comparing directly to True, False, or None





