# Глава 2. Прости пресмятания с числа

В настоящата глава ще се запознаем със следните концепции и програмни техники:
- какво представлява системната конзола;
- как да прочитаме числа от системната конзола;
- типовете данни и променливи, които са ни необходими при обработка на числа и операциите между тях;
- как да изведем резултат (число) на системната конзола;
- извършване на прости аритметични операции: събиране, изваждане, умножение, деление, съединяване на низ.

## Видео
<div class="video-player">
  Гледайте видео-урок по тази глава тук: <a target="_blank"
    href="https://www.youtube.com/watch?v=0f7c9RIZGaE">https://www.youtube.com/watch?v=0f7c9RIZGaE</a>.
</div>
<script src="/assets/js/video.js"></script>

## Системна конзола
Обикновено наричана само "конзола", системната, или още компютърната конзола, представлява устройството, чрез което подаваме команди на компютъра и получаваме резултатите от изпълнението на тези команди. В повечето случаи системната конзола представлява текстови терминал, т.е. приема и визуализира само текст, без графични елементи като например бутони, менюта и т.н. 

## Четене на числа от конзолата

За да прочетем цяло (не дробно) число от конзолата е необходимо да декларираме променлива, да посочим типа на числото, както и да използваме стандартната команда за четене на информация от системната конзола:

```cs
var num = int.Parse(Console.ReadLine());
```
Нека разгледаме и следния пример - пресмятане на лице на квадрат със страна а:

```cs
Console.Write("a = ");              
var a = int.Parse(Console.ReadLine());
var area = a * a;
Console.Write("Square area = ");
Console.WriteLine(area);
```
Ето как би работила програмата при квадрат със размер на страната 3:
![squareArea](https://github.com/SoftUni/Programming-Basics-Book-CSharp-BG/blob/master/assets/chapter-2-images/squareArea.png)

Тествайте вашето решение тук: https://judge.softuni.bg/Contests/Practice/Index/151#0

## Пресмятания в програмирането

За компютрите знаем, че са машини, които обработват данни. Всички **данни** се записват в компютърната памет (RAM памет) в **променливи**.
Всяка една **променлива** в C# има **име**, **тип** и **стойност**. Ето как бихме дефинирали една променлива, като едновременно с декларацията й, присвояваме и стойност:

![declaring variables](https://github.com/SoftUni/Programming-Basics-Book-CSharp-BG/blob/master/assets/chapter-2-images/declaringVariables.png)

След тяхната обработка, данните се записват отново в променливи.

## Типове данни и променливи

В програмирането, всяка една променлива съхранява определена стойност от даден **тип**. Типовете данни могат да бъдат например: число, буква, текст (стринг), дата, цвят, картинка, списък и др.
Ето и няколко примета за типове данни:
- Тип цяло число: 1, 2, 3, 4, 5, …
- Тип дробно число: 0.5, 3.14, -1.5, …
- Тип буква от азбуката (символ): 'a', 'b', 'c', …
- Тип текст (стринг): "Здрасти", "Hi", "Beer", …
- Тип ден от седмицата: Monday, Tuesday, …

## Четене на дробно число от конзолата

За да прочетем дробно число от конзолата е необходимо отново да декларираме променлива, да посочим типа на числото, както и да използваме стандартната команда за четене на информация от системната конзола:

```cs
var num = double.Parse(Console.ReadLine());
```

Нека разгледаме следния пример за работа с дробни числа - прехвърляне от инчове в сантиметри:

```cs
Console.Write("Inches = ");              
var inches = double.Parse(Console.ReadLine());
var centimeters = inches * 2.54;
Console.Write("Centimeters = ");
Console.WriteLine(centimeters);
```
Сега нека стартирам програмата и да се уверим, че при подаване на стойност в инчове, получаваме коректен резултат в сантиметри:

![inchesToCm](https://github.com/SoftUni/Programming-Basics-Book-CSharp-BG/blob/master/assets/chapter-2-images/inchesToCm.png)

Тествайте вашето решение тук: https://judge.softuni.bg/Contests/Practice/Index/151#1

## Четене и печатане на текст

За да прочетем текст (стринг) от конзолата отново декларираме нова променлива и използваме стандартната команда за четене на информация от системната конзола:

```cs
var str = Console.ReadLine();
```
Обърнете внимание, че при четене на текст не се декларира по никакъв начин тип "стринг"(текст). Това е така, защото по подразбиране метода ```Console.ReadLine()``` приема като параметър текст. Допълнително, вие можете да зададете текстът да бъде прехвърлен в цяло число чрез ```int.Parse()``` или дробно число чрез ```double.Parse()```. Ако това не се направи, за програмата всяко едно число ще бъде просто текст, с който не биха могли да се извършват аритметични операции.

Нека за пример напишем кратка програма за поздрав по име:

```cs
Console.Write("Enter your name: ");              
var name = Console.ReadLine();
Console.WriteLine("Hello, {0}!", name);
```
В случая, изразът {0} се замества с първия подаден аргумент -  в примера променливата "name":
![greetingByName](https://github.com/SoftUni/Programming-Basics-Book-CSharp-BG/blob/master/assets/chapter-2-images/greetingByName.png)

Тествайте вашето решение тук: https://judge.softuni.bg/Contests/Practice/Index/151#2

## Съединяване на текст и числа

При печат на системната конзола на текст, числа и други данни, ние можем да ги съединим, като използваме шаблони **{0}**, **{1}**, **{2}**,... В програмирането тези шаблони се наричат **placeholders**.
```cs
var firstName = Console.ReadLine();
var lastName = Console.ReadLine();
var age = int.Parse(Console.ReadLine());
var town = Console.ReadLine();
Console.WriteLine(
  "You are {0} {1}, a {2}-years old person from {3}.",
  firstName, lastName, age, town);
```
Ето резултатът, който ще получим, след изпълнение на този пример:
![placeholdersInAction](https://github.com/SoftUni/Programming-Basics-Book-CSharp-BG/blob/master/assets/chapter-2-images/placeholders.png)

Обърнете внимание, как всяка една променлива трябва да бъде подадена в **реда, в който искаме да се печата**. По същество,  шаблонът (плейсхолдър) приема променливи от всякакъв вид. Не се допуска да има шаблони, които да имат една и съща поредност, т.е. два или повече шаблона под номер 2. В такъв случай, вашата програма няма да се компилира. 

Тествайте вашето решение тук: https://judge.softuni.bg/Contests/Practice/Index/151#3

## Аритметични операции събиране и изваждане

### Събиране на числа (оператор +)

```cs
var a = 5;
var b = 7;
var sum = a + b; // резултатът е 12
```
### Изваждане на числа (оператор -)

```cs
var a = int.Parse(Console.ReadLine());
var b = int.Parse(Console.ReadLine());
var result = a - b;
Console.WriteLine(result);
```
Съответно, ето и резултатът от изпълението на програмата, при числа 10 и 3:
![subtracting](https://github.com/SoftUni/Programming-Basics-Book-CSharp-BG/blob/master/assets/chapter-2-images/subtracting.png)

## Аритметични операции умножение и деление

### Умножение на числа (оператор *)

```cs
var a = 5;
var b = 7;
var product = a * b; // 35
```

### Деление на числа (оператор /)

```cs
var a = 25;
var i = a / 4;      // резултатът от тази операция ще бъде 6 – дробната част се отрязва, 
                    // тъй като извършваме деление с цели числа
var f = a / 4.0;    // 6.25 – дробно деление. Изрично сме указали числото 4 да се интерпретира
                    // като дробно, като сме добавили 0 след десетичната запетая
var error = a / 0;  // Грешка: деление на 0
```

### Особености при деление на числа в C#

В тази секция ще обърнем внимание на някои особености. При деление на цели числа резултатът е цяло число:

```cs
var a = 25;
Console.WriteLine(a / 4);  // Целочислен резултат: 6
Console.WriteLine(a / 0);  // Грешка: деление на 0
var error = a / 0;  // Грешка: деление на 0
```
При деление на дробни числа резултатът е дробно число:

```cs
var a = 15;
Console.WriteLine(a / 2.0);  // Дробен резултат: 7.5
Console.WriteLine(a / 0.0);  // Резултат: Infinity
Console.WriteLine(0.0 / 0.0); // Резултат: NaN (Not a Number), 
                              // резултатът от операцияте не представлява числена стойност
```

## Съединяване на текст и число

Терминът за съединяване на текст и/или числа е конкатенация. Ето как можем да съединяваме текст и число с оператора `+`:

```cs
var firstName = "Maria";
var lastName = "Ivanova";
var age = 19;
var str = firstName + " " + lastName + " @ " + age;
Console.WriteLine(str);  // Maria Ivanova @ 19
```

Още един пример:

```cs
var a = 1.5;
var b = 2.5;
var sum = "The sum is: " + a + b;
Console.WriteLine(sum);  // The sum is: 1.52.5
```

## Числени изрази

В програмирането можем да пресмятаме числови изрази:

```cs
var expr = (3 + 5) * (4 – 2);
```
В сила е стандартното правило, че умножение и деление се извършват винаги преди събиране и изваждане. При наличие на израз в скоби, то той се изчислява пръв. 

Пример: изчисляване на лице на трапец:
```cs
var b1 = double.Parse(Console.ReadLine());
var b2 = double.Parse(Console.ReadLine());
var h = double.Parse(Console.ReadLine());
var area = (b1 + b2) * h / 2.0;
Console.WriteLine("Trapezoid area = " + area);
```
Тестване на решението: https://judge.softuni.bg/Contests/Practice/Index/151#4

## Периметър и лице на кръг – пример

Нека напишем една програма, която при въвеждане радиуса r на кръг изчислява лицето и периметъра на кръга / окръжността.
Формули:
- Лице = π * r * r
- Периметър = 2 * π * r
- π ≈ 3.14159265358979323846…

```cs
Console.Write("Enter circle radius. r = ");
var r = double.Parse(Console.ReadLine());
Console.WriteLine("Area = " + Math.PI * r * r);
Console.WriteLine("Perimeter = " + 2 * Math.PI * r);
```
Нека изпробваме програмата с радиус = 10:
![circleArea](https://github.com/SoftUni/Programming-Basics-Book-CSharp-BG/blob/master/assets/chapter-2-images/circleArea.png)

Тестване на решението: https://judge.softuni.bg/Contests/Practice/Index/151#5

## Лице на правоъгълник в равнината – пример

Правоъгълник е зададен с координатите на два от своите срещуположни ъгъла. Да се пресметнат площта и периметъра му:

<img alt="rectangleArea" src="https://github.com/SoftUni/Programming-Basics-Book-CSharp-BG/blob/master/assets/chapter-2-images/rectangleArea.png" width="250" height="200" />

```cs
double x1 = double.Parse(Console.ReadLine());
double y1 = double.Parse(Console.ReadLine());
double x2 = double.Parse(Console.ReadLine());
double y2 = double.Parse(Console.ReadLine());
double width = Math.Max(x1, x2) - Math.Min(x1, x2);
double height = Math.Max(y1, y2) - Math.Min(y1, y2);
Console.WriteLine("Area = {0}", width * height);
Console.WriteLine("Perimeter = {0}", 2 * (width + height));
```
При стартиране на програмата със стойностите от координатната система в условието, получаваме следния резултат:

![rectangleAreaExample](https://github.com/SoftUni/Programming-Basics-Book-CSharp-BG/blob/master/assets/chapter-2-images/rectangleAreaExample.png)

TODO: judge link

## Какво научихме от тази глава?

- Как да въвеждаме текст: ``` var str = Console.ReadLine();```

- Как да въвеждаме цяло число: ``` var num = int.Parse(Console.ReadLine());```

- Как да извършваме пресмятания с числа и да използваме съответни оператори за това: +, -, *, /, (): ``` var sum = 5 + 3;```

- Извеждане на текст по шаблон: ``` Console.WriteLine("{0} + {1} = {2}", 3, 5, 3 + 5);```

## Упражнения: Прости пресмятания

TODO: да се следва файла "2. Simple-Calculations-Exercises.docx"

### 0.	Празно Visual Studio решение (Blank Solution)
### 1.	Пресмятане на лице на квадрат
### 2.	От инчове към сантиметри
### 3.	Поздрав по име
### 4.	Съединяване на текст и числа
### 5.	Лице на трапец
### 6.	Периметър и лице на кръг
### 7.	Лице на правоъгълник в равнината
### 8.	Лице на триъгълник
### 9.	Конзолен конвертор: от градуси °C към градуси °F
### 10.	Конзолен конвертор: от радиани в градуси
### 11.	Конзолен конвертор: USD към BGN
### 12.	* Конзолен междувалутен конвертор
### 13.	** Пресмятане с дати: 1000 дни на Земята

## Упражнения: графични и уeb приложения

TODO: да се следва файла "2. Simple-Calculations-Exercises.docx"

### Графично приложение: конвертор от BGN към EUR

TODO: да се следва файла "2. Simple-Calculations-Exercises.docx"

### *** Графично приложение: хвани бутона!

TODO: да се следва файла "2. Simple-Calculations-Exercises.docx"
