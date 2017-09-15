#HSLIDE
## Being functional
HackSoft Conf 2017, Георги Божинов

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
insert introduction here :: Text
```

#HSLIDE
### 1. Какво е ФП?
* Нов стил на програмиране
* Чистота - в кода и в програмите
* Функции, функции
* Два нови подхода на програмиране - мързеливост + композиция

#HSLIDE
### 2. Някои принципи на ФП
* Краткост, модулярност
* Лесен и разбираем за четене код, лесно се тества, лесно за обобщаване на операции за различни типове.

```haskell
data List a = Nil | Cons a (List a)

sum Nil = 0 
sum (Cons a list) = a + sum list

-- 0 and + -> only specific to sum elements

sum = foldr (+) 0
```

#HSLIDE
### 2. Някои принципи на ФП
* Използване на една функция за имплементацията на много други.

```haskell
product = foldr (*) 1
any = foldr (v) False
all = foldr (^) True
```

#HSLIDE
### 2. Някои принципи на ФП
* Map, filter, reduce (=foldr)

```haskell
map (+1) [1, 2, 3, 4]
```

```haskell
filter odd [1, 2, 3, 4]
```

```haskell
foldr Cons Nil [1, 2, 3, 4]
```

#HSLIDE
### 2. Някои принципи на ФП
* Композиция на функции
```haskell
doubleAll list = foldr (\n -> n * 2) Nil list
```
```haskell
doubleAll = foldr doubleList Nil
  where 
    double n list = Cons (2 * n) list
```
```haskell
doubleAll = fandcons double
  where
    fandcons f n list = Cons (f n) list
```
```haskell
fandcons f = Cons . f 
```

* Правило на композицията -> (Cons . f) a = Cons (f a)

#HSLIDE
### 2. Някои принципи на ФП
* Мързеливост

```haskell
( sumFirstTwo . quickSort ) xs
```

```haskell
take 10 [1..]
```

* Синхронизация, функция се изпълнява само толкова, колкото е нужно. 

#HSLIDE
### 2. Някои принципи на ФП
* Казваме какво да се изпълни, не как.

#HSLIDE
### 3. Кое му е доброто?
* Лесно и удобно разделение на програмите на компоненти и модули.
* Тестването на отделни компоненти е по-лесно.
* Мързеливо се оценява всичко и позволява работа с потенциално безкрайни структури.

#HSLIDE
### 3. Кое му е доброто?
* Няма странични ефекти, или ако има, се контролират.
* Това, което не ни трябва, не се оценява.
* Referential transparency.

#HSLIDE
### 4. Примери
```haskell
(take 10 . filter (<1) . map (1/)) [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 0]
```

```sql
SELECT * from ...
SELECT * from ... WHERE
SELECT * from ... WHERE ... ORDER BY ...
```

```haskell
data Maybe a = Nothing | Just a
```

#HSLIDE
### 5. Защо харесвам ФП?
* Елегантен и кратък код.
* Силна теоретична обосновка, доказателствата са лесни за извеждане.
* Разделението на задача на части е по-лесно от всякога.

#HSLIDE
## Благодаря за вниманието!
