# Глава 4. По-сложни проверки

В настоящата глава...

TODO

## Видео

<div class="video-player">
  Гледайте видео-урок по тази глава тук: <a target="_blank"
  href="https://www.youtube.com/watch?v=z8XxYIyesz0">
  https://www.youtube.com/watch?v=z8XxYIyesz0</a>.
</div>
<script src="/assets/js/video.js"></script>

## Вложени проверки

Конструкциите if-else могат да се влагат една в друга:

if (condition1)
{
   if (condition2)
      Console.WriteLine("condition2 valid");
   else
      Console.WriteLine("condition2 not valid");
   Console.WriteLine("condition1 valid");
}


### Пример: Обръщение според възраст и пол

Според въведени възраст и пол (m / f) да се отпечата обръщение:
“Mr.” – мъж (пол “m”) на 16 или повече години
“Master” – момче (пол “m”) под 16 години
“Ms.” – жена (пол “f”) на 16 или повече години
“Miss” – момиче (пол “f”) под 16 години

TODO: table holding sample input / output

TODO: анализ на задачата и разсъждения как можем да я решим.

TODO: image - картинката с диаграмата от слайдовете

Решение на задачата:

var age = double.Parse(Console.ReadLine());
var gender = Console.ReadLine();
if (age < 16)
{
   if (gender == "m") Console.WriteLine("Master");
   else if (gender == "f") Console.WriteLine("Miss");
}
else
{
   if (gender == "m") Console.WriteLine("Mr.");
   else if (gender == "f") Console.WriteLine("Ms.");
}

Тестване на решението: https://judge.softuni.bg/Contests/Practice/Index/153#0


### Пример: Квартално магазинче

Предприемчив българин отваря по едно квартално магазинче в няколко града с различни цени за следните продукти:

TODO: таблица с цените по градове и продукти

По даден град, продукт и количество да се пресметне цената. Примери:

TODO: таблица с примерните вход и изход

Решение: квартално магазинче

var product = Console.ReadLine().ToLower();
var town = Console.ReadLine().ToLower();
var quantity = double.Parse(Console.ReadLine());
if (town == "sofia")
{
   if (product == "coffee") 
      Console.WriteLine(0.50 * quantity);
  // TODO: finish this …
}
if (town == "varna") // TODO: finish this …
if (town == "plovdiv") // TODO: finish this …

Тестване на решението: https://judge.softuni.bg/Contests/Practice/Index/153#1


## По-сложни проверки

Нека разгледаме как можем да правим по-сложни логически проверки, ако се наложи. Може да използваме логическо "и", логическо "или", логическо отрицание и скоби...


## Логическо "И"

Логическо "И" (оператор &&) означава няколко условия да са изпълнени едновременно

if (x >= x1 && x <= x2 && y >= y1 && y <= y2) …

### Точка в правоъгълник
Пример: проверка дали точка {x, y} се намира вътре в правоъгълника {x1, y1} – {x2, y2}

TODO: image

Необходимо е точката {x, y} да е:
надясно от x1 и наляво от x2 и
надолу от y1 и нагоре от y2

Точка е вътрешна за даден правоъгълник, ако е:
надясно от лявата му страна, наляво то дясната му страна, надолу от горната му страна и нагоре от долната му страна

var x = 8, y = -1;
var x1 = 2, y1 = -3;
var x2 = 12, y2 = 3;
if (x >= x1 && x <= x2 && y >= y1 && y <= y2)
   Console.WriteLine("Inside");
else
   Console.WriteLine("Outside");

Тестване на решението: https://judge.softuni.bg/Contests/Practice/Index/153#2


## Логическо "ИЛИ"

Логическо "ИЛИ" (оператор ||) означава да е изпълнено поне едно измежду няколко условия

if (s == "banana" || s == "apple" || s == "kiwi")
  Console.WriteLine("fruit");

### Задача: плод или зеленчук?
Плодовете "fruit" са: banana, apple, kiwi, cherry, lemon, grapes
Зеленчуците "vegetable" са: tomato, cucumber, pepper, carrot
Всички останали са "unknown"

TODO: smaple input and output

Решение на задачата "плод или зеленчук":

var s = Console.ReadLine();
if (s == "banana" || s == "apple" || s == "kiwi" ||
    s == "cherry" || s == "lemon" || s == "grapes")
  Console.WriteLine("fruit");
else if (s == "tomato" || s == "cucumber" ||    s == "pepper" || s == "carrot")
  Console.WriteLine("vegetable");
else
  Console.WriteLine("unknown");

Тестване на решението: https://judge.softuni.bg/Contests/Practice/Index/153#3


## Логическо отрицание

Логическо отрицание (оператор !) означава да не е изпълнено дадено условиe
Пример:
Дадено число е валидно, ако е в диапазона [100…200] или е 0
Да се направи проверка за невалидно число

var inRange = (num >= 100 && num <= 200) || num == 0;
if (!inRange)
  Console.WriteLine("invalid");

Тестване на решението: https://judge.softuni.bg/Contests/Practice/Index/153#4

### Пример: Точка върху страна на правоъгълник

Да се напише програма, която чете 6 десетични числа x1, y1, x2, y2, x и y
Печата дали точката е върху страна от правоъгълника или не
Ограничения: x1 < x2 и y1 < y2

TODO: table holding the sample input / output + the image


## По-сложни логически условия

Точка лежи върху някоя от страните на правоъгълник, ако:
x съвпада с x1 или x2 и същевременно y е между y1 и y2 или
y съвпада с y1 или y2 и същевременно x е между x1 и x2

TODO: image

if (((x == x1 || x == x2) && 
     (y >= y1) && (y <= y2)) ||
    ((y == y1 || y == y2) && 
     (x >= x1) && (x <= x2)))
{
   Console.WriteLine("Border");
}

Предходното условие може да се опрости ето така:

var onLeftSide = (x == x1) && (y >= y1) && (y <= y2);
var onRightSide = (x == x2) && (y >= y1) && (y <= y2);
var onUpSide = (y == y1) && (x >= x1) && (x <= x2);
var onDownSide = (y == y2) && (x >= x1) && (x <= x2);
if (onLeftSide || onRightSide ||     onUpSide || onDownSide)
{
    Console.WriteLine("Border");
}

Тестване на решението: https://judge.softuni.bg/Contests/Practice/Index/153#5

### Пример: Магазин за плодове

Магазин за плодове в работни дни продава на следните цени:

TODO: table

В почивни дни цените са по-високи:

TODO: table

Примерен вход и изход:

TODO: sample input / output

Решение на задачата:

if (day == "saturday" || day == "sunday")
{
   if (fruit == "banana") price = 2.70;
   else if (fruit == "apple") price = 1.25;
   // TODO: more fruits come here …
}
else if (day == "monday" || day == "tuesday" || day ==
   "wednesday" || day == "thursday" || day == "friday")
{
   if (fruit == "banana") price = 2.50;
   // TODO: more fruits come here …
}

Тестване на решението: https://judge.softuni.bg/Contests/Practice/Index/153#6

### Пример: Търговски комисионни

Фирма дава следните комисионни на търговците си според града, в който работят и обема на продажбите s:

TODO: table

Напишете програма, която по град и обемна продажбите изчислява комисионната
Резултатът да се изведе закръглен с 2 десетични цифри

TODO: sample input / output

var comission = -1.0;
if (town == "sofia")
{
  if (0 <= sales && sales <= 500) comission = 0.05;
  else if (500 < sales && sales <= 1000) comission = 0.07;
  // TODO: check the other price ranges …
}
else if (town == "varna") // TODO: check the price ranges …
else if (town == "plovdiv") // TODO: check the price ranges …
if (comission >= 0)
  Console.WriteLine("{0:f2}", sales * comission);
else Console.WriteLine("error");

Тестване на решението: https://judge.softuni.bg/Contests/Practice/Index/153#7

## Условна конструкция switch-case

Switch-case работи като поредица if-else-if-else
Пример: Принтирайте деня от седмицата (на английски) според въведеното число (1…7)

int day = int.Parse(Console.ReadLine());
switch (day)
{
  case 1: Console.WriteLine("Monday"); break;
  case 2: Console.WriteLine("Tuesday"); break;
  …
  case 7: Console.WriteLine("Sunday"); break;
  default: Console.WriteLine("Error!"); break;
}

Тестване на решението : https://judge.softuni.bg/Contests/Practice/Index/153#8

### Множество етикети в switch-case

Напишете програма, която принтира вида на животно според името му: dog -> mammal; crocodile, tortoise, snake -> reptile; others -> unknown

switch (animal)
{
  case "dog": Console.WriteLine("mammal"); break;
  case "crocodile":
  case "tortoise":
  case "snake": Console.WriteLine("reptile"); break;
  default: Console.WriteLine("unknown"); break;
}

Тестване на решението: https://judge.softuni.bg/Contests/Practice/Index/153#9


## Какво научихме от тази глава?

Вложени проверки:

if (condition1)
{
   if (condition2) …
   else …
}

По-сложни проверки с &&, ||, ! и ():

if ((x == left || x == right) && y >= top && y <= bottom)
  Console.WriteLine("Point on the left or right side.");


## Упражнения: по-сложни проверки

TODO: да се ползва като основа файла "4. Complex-Conditions-Exercises.docx".
TODO: повтарящите се задачи и обясненията за тях да се качат по-горе в текста.

### 0. Празно Visual Studio решение (Blank Solution)

### 1. Обръщение според възраст и пол

### 2. Квартално магазинче

### 3. Точка в правоъгълник

### 4. Плод или зеленчук?

### 5. Невалидно число

### 6. Точка върху страната на правоъгълник

### 7. Магазин за плодове

### 8. Търговски комисионни

### 9. Day of Week

### 10. Animal Type

### 11. Кино

### 12. Волейбол

### 13. * Точка във фигурата

## Упражнения: графични и уеб приложения

### 14. * Точка и правоъгълник – графично (GUI) приложение

TODO: да се ползва като основа файла "4. Complex-Conditions-Exercises.docx".
