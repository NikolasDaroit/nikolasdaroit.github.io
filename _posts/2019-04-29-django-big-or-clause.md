---
title: 'Django query for big OR clause'
layout: post
categories:
  - '[Django'
  - ' Python]'
tags:
  - Query
published: false
---
## Django Query for big OR clause

Instead of making raw queries like

```python
User.objects.raw('SELECT * FROM table WHERE (first_name, last_name) IN %s',
      [ (('John','Doe'),('Jane','Smith'),('Bill','Clinton')) ])
```
you could create a reduced query to filter
```python
import operator
from itertools import izip
query = reduce(
    operator.or_, 
    (Q(firstname=fn, lastname=ln) for fn, ln in izip(first_list, last_list))
    )

Person.objects.filter(query)
```
this will generate the following SQL
```sql
SELECT <fieldnames here...> FROM <tablename>
WHERE (fistname="X1" AND lastname="y1")
OR (firstname="x2" AND lastname="Y2")
OR <etc....>
```