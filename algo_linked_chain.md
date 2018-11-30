# Listes chaînées :


```Python
class Node:
    def __init__(self, value, next=None):
        self.value = value
        self.next = next
    def __str__(self):
        return f’{self.value}’

head = Node(‘A’)
head.next = Node(‘B’)
```

```Python
print(head)
>>> A
```

```Python
print(head.next)
>>> B
```

```Python
print(head.next.next)
None
```

```Python
head = {‘value’: ‘A’}
head[‘next’] = {‘value’: ‘B’}
{‘value’: ‘B’}

print(head[‘next’][‘value’]
>> B
```

## Parcourir :

```Python
def parcourir(liste=None):
    head = liste
    while head != None:
        yield head.value
        head = head.next

ma_liste = Node(‘A’, Node(‘B’, Node(‘C’)))
for a in parcourir(ma_liste):
    print(a)
Sélectionner :

def selectionner(liste, index=0):
    for i, valeur in enumerate(parcourir(liste)):
        if i >= index:
            return valeur
    raise IndexError()

enumerate(parcourir(ma_liste))
```
