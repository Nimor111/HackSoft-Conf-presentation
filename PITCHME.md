#HSLIDE
## Функционално програмиране
( полезни практики )  

#HSLIDE
## Съдържание
0. Представяне
1. Какво е ФП?
2. Някои принципи на ФП
3. Кое му е доброто?
4. Примери
5. Защо харесвам ФП?

#HSLIDE
### 0. Представяне
```haskell
insert introduction here :: String
```

#HSLIDE
### 1. Какво е ФП?
* Нов стил на програмиране
* Чистота - в кода и в програмите
* Функции, функции

#HSLIDE
### 2. Някои принципи на ФП
* Краткост, модулярност
* Лесен и разбираем за четене код, лесно се тества, лесно за обобщаване на операции за различни типове.

```haskell
data List a = Nil | Cons a (List a)

sum Nil = 0
sum (Cons a list) = a + sum list

sum = foldr (+) 0
```

#HSLIDE
### 2. Някои принципи на ФП
* Използване на една фунцкия за имплементацията на много други.

```haskell
product = foldr (*) 1
any = foldr (v) False
all = foldr (^) True
```

#HSLIDE
### 2. Някои принципи на ФП
* Map, filter, reduce (=foldr)

```python
xs = [1, 2, 3, 4]
mapped = map(lambda x: x + 1, xs)
```

```python
filtered = filter(lambda x: x >= 2, xs)
```

```python
sum = reduce(lambda x, acc: acc + x, xs)
```

#HSLIDE
### 2. Някои принципи на ФП
* Мързеливост

```python
for i in range(100000):
    yield(i)
```

```haskell
take 10 [1..]
```

Синхронизация, функция се изпълнява само толкова, колкото е нужно. 

#HSLIDE
### 2. Някои принципи на ФП
* Казваме какво да се изпълни, не как.
