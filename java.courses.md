## Что такое JDK 
Комплект разработчика на языке Java; 
JDK - JRE,  JAVAC (JAVA КОМПИЛЯТОР), СТАНДАРТНЫЕ БИБЛИОТЕКИ
JAVA RUNTIME ENVIRONMENT - СРЕДА РАЗРАБОТКИ ПРИЛОЖЕНИЙ. 
Если надо запустить  - нуден JRE. 
Jre (Java virtual MACHINE + library) 
## Порядок создания приложения 
```
1) создаем файл - помещаем код (.JAVA)
2) Javac - компилирует: синтаксис, ошибки 

BYTE code

---> .CLASS 
Общий формат, который позволяет считывать код на всех устройствах.
СКОМПИЛИРОВАНОЕ ОДНАЖДЫ - ЗАПУСТИТСЯ ВЕЗДЕ! 
3) JVM- отличается от платформы. Т.к. тесно связана с ОС. JVM отличаются. 
```
## ООП
```
Парадигма - способ мышления/восприятия чего-нибудь

что-то понять - упростить 

парадигма программирования - ТЗ. Человек берет задание, делит на части -> программный код
процедурная парадигма: спать, есть, помыться - АЛГОРИТМ 

dependency-injection
```
ПРИНЦИПЫ ООП

1. Сейчас мы применили принцип в ООП — выделение наиболее важных характеристик и информации об объекте. Этот принцип ООП называется абстракцией.
```
public abstract class AbstractPhone {
    private int year;

    public AbstractPhone(int year) {
        this.year = year;
    }
    public abstract void call(int outputNumber);
    public abstract void ring (int inputNumber);
}
```
2. Инкапсуляция
С помощью абстракции мы выделяем общее для всех объектов.Однако каждая модель телефона — индивидуальна и чем-то отличается от других. Как же нам в программе провести границы и обозначить эту индивидуальность?

один базовый принцип ООП, при котором атрибуты и поведение объекта объединяются в одном классе, внутренняя реализация объекта скрывается от пользователя, а для работы с объектом предоставляется открытый интерфейс.

Задача программиста — определить, какие атрибуты и методы будут доступны для открытого доступа, а какие являются внутренней реализацией объекта и должны быть недоступны для изменений. 
```Возможность же изменения состояния и поведения осуществляется с помощью модификаторов доступа к полям и методам – private, protected, public, а также default (доступ по умолчанию). Это означает, что получить доступ к private полям из вне невозможно, как и нет возможности вызвать private методы. ```
3. Наследование
```
public abstract class WirelessPhone extends AbstractPhone {

    private int hour;

    public WirelessPhone(int year, int hour) {
        super(year);
        this.hour = hour;
    }
    }
```
```
public class CellPhone extends WirelessPhone {
    public CellPhone(int year, int hour) {
        super(year, hour);
    }

    @Override
    public void call(int outputNumber) {
        System.out.println("Вызываю номер " + outputNumber);
    }

    @Override
    public void ring(int inputNumber) {
        System.out.println("Вам звонит абонент " + inputNumber);
    }
}
```
4. Полиморфизм
Если мы посмотрим на все модели телефонов, то, несмотря на различия во внешнем облике и устройстве моделей, мы можем выделить у них некое общее поведение – все они могут принимать и совершать звонки и имеют достаточно понятный и простой набор кнопок управления. Применяя известный нам уже один из основных принципов ООП абстракцию в терминах программирования можно сказать, что объект телефон имеет один общий интерфейс. Поэтому пользователи телефонов могут вполне комфортно пользоваться различными моделями, используя одни и те же кнопки управления (механические или сенсорные), не вдаваясь в технические тонкости устройства. Так, вы постоянно пользуетесь сотовым телефоном, и без труда сможете совершить звонок с его стационарного собрата. 
```
public class ThomasEdisonPhone extends AbstractPhone {

public ThomasEdisonPhone(int year) {
    super(year);
}
    @Override
    public void call(int outputNumber) {
        System.out.println("Вращайте ручку");
        System.out.println("Сообщите номер абонента, сэр");
    }

    @Override
    public void ring(int inputNumber) {
        System.out.println("Телефон звонит");
    }
```
```

public class Phone extends AbstractPhone {

    public Phone(int year) {
        super(year);
    }

    @Override
    public void call(int outputNumber) {
        System.out.println("Вызываю номер" + outputNumber);
    }

    @Override
    public void ring(int inputNumber) {
        System.out.println("Телефон звонит");
    }
}
```
### POM (Project Object Model) является базовым модулем Maven. Это специальный XML-файл, который всегда хранится в базовой директории проекта и называется pom. xml. Файл POM содержит информацию о проекте и различных деталях конфигурации, которые используются Maven для создания проекта.
# 26.10.2021
Стандартный ввод данных:
``` 
public class Main {

   public static void main(String[] args) {

       Scanner sc = new Scanner(System.in);
       System.out.println("Введите число:");

       int number = sc.nextInt();

       System.out.println("Спасибо! Вы ввели число " + number);

   }
}
```
Ввод данных при импорте библиотеки: 
````
package com.company;
import java.util.Scanner;
import static java.lang.System.*;
public class CheckPassword {

    public static void main(String[] args) {
	out.println("Please enter a password!");
    Scanner scanner = new Scanner(in);
    String password = scanner.next();
    


    }
}
````
## Для сравнения того, чтобы узнать, сслыаются ли примитивы на один объект используют ==. Для того, чтобы узнать, равны ли объекты используют equals()
== для сравнения битов 
Пример 
int a = 3
byte b = 3 
if (a==b) 
Они будут равны. Но суть заключается в том, что у них одтинаковые значащие части, просто у первого больше нулей и все. 

== от этого знака скрыта вся информация об объкте только ссылка. 

геттер 
 
private 

передача по значению
переменная экземпляра

```
Псевдокод - сосредоточиться на логике не вникая в синтаксис 
Тестовый код 
Реальный код
```
## МОРСКОЙ БОЙ 
int guess = Integer.parseInt (stringGuess); //Преобразует строку в целочисленную переменную
Integer - класс встроенный в Java

Поэтому, у примитивных типов есть объекты-аналоги - так называемые "классы оболочки", или "wrapper" (с англ. "обертка, упаковка"). Класс называется "оболочкой" потому, что он, по сути, копирует то, что уже существует, но добавляет новые возможности для работы с привычными типами.
Например, обычный int занимает меньше места, и если нет необходимости проводить над ним особые операции, Ваш компьютер будет работать быстрее.

В свою очередь, с помощью класса-оболочки Integer можно выполнять специальные операции - например, перевести текст в число (с помощью метода .parseInt() для Integer-а ). Если попробовать сделать это с помощью кода самому придется изрядно повозиться.

Integer и int можно сравнить с компьютером и записной книжкой:Компьютер, безусловно, может больше, чем блокнот - но Вы не будете целый день носить с собой три килограмма для того, чтобы сделать несколько заметок?

Кроме того, есть ситуации, когда нельзя использовать объекты, или наоборот, когда можно использовать только объекты.

        String a = "11";
 
        int b = Integer.parseInt(a);
    
    for (int cell : LocationCells) - 

    Для каждого значения (cell) в LocationCells выполнять
    Integer.toString(randomNum) - обратное действие 
    Parse (в переводе от англ.) - разбор, анализ

## Array list - это объект. В то время как массив лишь подобие.
1) В массиве для определение длины пишут: 
MyArray.length();
В листе пишун MyArray.size (); 
2) Удаление : MyArray[1] = null ----> <lol>.remove()
3)Проверка "наличия":
boolean isIn = myList.contains(<item>)
В массиве: 
boolean isIn = false;
    for (String item : myList){
        if (b.equals(item))
        isIn = true;
        break;
    }
4) Указание размеров: 
Массив требует уточнения своего размера: new String [2]
В то время как арэйка нет: new ArrayList <String>()
Можно указать размер- но зачем? Он динамечен, тем самым удобен 
5) Массивы требуют особого отношения. В то время как арэйка ведет себя как вполне обычный класс. Можно вызывать методы для включенных элементов. НО
### ПАРМЕТРИЗОВАННЫЕ ТИПЫ В ARRAYLIST
Или угловые скобочки <> Это типовой аргумент. Означает к примеру: ArrayList<String>  - список объектов строкового типа. ТИП СУЩНОСТИ 
### МОРСКОЙ БОЙ - редачим вместе с Array 
 class SimpleDotCom {
        private ArrayList<String> LocationCells;
        int numOfHits = 0;

        public void setLocationCells(ArrayList<String> loc ) {
           LocationCells = loc;
        }

        public String checkYourself(String userInput) {
            String result = "Мимо";
            int index = LocationCells.indexOf(userInput); // Проверяет существует ли передаваемый объект в Array.
            //Если - нет, то возвращается -1. Если да то 1, 0
            if (index>=0) {
                LocationCells.remove(index);
                if (LocationCells.isEmpty()) {
                    result = "Потопил";
                } else {
                    result = "Попал";
                }
            }
            System.out.println(result);
            return result;
        }
    }
### Что же такое BufferReader и с чем его едят? 
```
 class GameHelper {
        public String getUserInput(String promt) {
            String inputLine = null;
            System.out.println(promt + " ");
            try {
                BufferedReader is = new BufferedReader(
                        new InputStreamReader(System.in)
                );
                inputLine = is.readLine();
                if (inputLine.length() == 0) return null;
            } catch (IOException e) {
                System.out.println("IOException: " + e);
            }
            return inputLine;
        }
    }
```
1) String promt - WTF
отображает диалоговое окно с необязательным запросом на ввод текста

String inputLine = null - мой ответ изначально равен 0 

System.out.println(promt + " "); - Диалог + пробел 

BufferedReader читает текст из потока ввода символов 

Считываем данные с консоли и записываем в файл: new InputStreamReader(System.in)  --> inputLine = is.readLine();

catch (IOException e) {
                System.out.println("IOException: " + e); - базовая запись 


return inputLine - вернуть мою строку 

