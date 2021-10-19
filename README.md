# Knowledge

# 18.10.2021 - New start
Массивы в Java
```
Для инициализации места в массиве используем: 
int month_days[];
month_days = new int [12]; - 12 нулевых значений
```
Можно заменить верхние строки на: int month_days[]

# 19.10.2021
### Что делает new? 
new - динамически, во время выполнения програмы резервирует память для объекта и возвращает ссылку на него. 
```
Box myBox1;m - объявить ссылку на объект 
myBox1 = new Box ();- выделить память для объекта 
```
### Отличие класса от объкта?
Класс создает тип объектов. Класс - логический каркас, который связывает части программы воедино.
При объявлении объекта класса создается его экземпляр. НО физическую сущность имеют объекты, тбо они занимают память. 
### Что будет, если мы объединим два класса? 
        Box myBox1 = new Box ();
        Box myBox2 = myBox1;
Само собой, они ссылаются на один объект. НО КОПИРУЕТСЯ НЕ ОБЪЕКТ, А ССЫЛКА!!!
ЕСЛИ будем изменять от имени одного из любых экземпляров, то это приведет к totality-изменялити. 
### Чем отличаются классы public, private, just class? 

Static — модификатор, применяемый к полю, блоку, методу или внутреннему классу. Данный модификатор указывает на  привязку субъекта  к текущему классу.

А то, что если переменная не статическая, то у каждого нового объекта данного класса будет своё значение этой переменной, меняя которое мы меняем его исключительно в одном объекте:
```
public class Car {
  static int km;
}
Orange car - 85
Blue car - 85

```
## Статический блок
Есть два блока инициализации — обычный и статический.

Блок предназначен для инициализации внутренних переменных. Если блок обычный, то им инициализируют внутренние переменные объекта, если же статический, соответственно, им задают статические переменные (то есть переменные класса).

Пример класса со статическим блоком инициализации: 

```
public class Car {
  static int km;

  static {
     km = 150;
  }
}
```
## Статический класс в Java
Статическим классом может быть только внутренний класс.

Опять же, этот класс привязан к внешнему классу, и если внешний наследуется другим классом, то этот не будет наследован. При этом данный класс можно наследовать, как и он может наследоваться от любого другого класса и имплементировать интерфейс.

По сути статический вложенный класс ничем не отличается от любого другого внутреннего класса за исключением того, что его объект не содержит ссылку на создавший его объект внешнего класса. 

Тем не менее, благодаря этому статический класс наиболее похож на обычный не вложенный, ведь единственное различие состоит в том, что он упакован в другой класс. В некоторых случаях для нас это преимущество, так как с него у нас есть доступ к приватным статическим переменным внешнего класса.
```
public class Counter {
  static int count;

  public static void invokeCounter() {
     count++;
     System.out.println("Текущее значение счётчика - " + count);
  }
}
```
## Прейдем к методам 
Если метод ничего не возвращает, то тогда мы используем VOID. 
Просто прикреплю программу для подсчета объемов 2 пар-ов: 
```
public class Box {
    double width;
    double height;
    double depth;

    void volume (double cat){
        System.out.println("The volume of the FIRST parallelepiped "+cat);
    }
}
/*the volume of two parallelepiped*/
class BoxDemo {
    public  static void main (String[] args) {
        Box myBox1 = new Box ();
        Box myBox2 = new Box();
        myBox1.width = 2;
        myBox1.height = 12;
        myBox1.depth = 12;
        /*We'll gonna find the biggest one*/
        myBox2.width = 3;
        myBox2.height = 123;
        myBox2.depth = 32;
        double vol1, vol2;
        vol1= myBox1.width*myBox1.depth*myBox1.height;
        vol2= myBox2.width*myBox2.depth*myBox2.height;
        if (vol1>vol2) {System.out.println ("The biggest one is vol1");}
        else {System.out.println("The biggest one id vol2");}
        myBox1.volume(vol1); --------------- ВЫЗОВ ОСУЩЕСТВЛЯЕТСЯ ПО ОТНОШЕНИЮ К MYBOX1
        myBox1.volume(vol2);

    }
}
``` 
### возврат значений в методах - return
```
public class return_ki {
    int square (int i){
        return i*i; 
    }
    int x, y; 
    x= square (10);
    
}
I----- ПАРАМЕТР 
____________________________________________________________
АРГУМЕНТ - ЭТО ЗНАЧЕНИЕ, ПЕРЕДАВАЕМОЕ МЕТОДУ ПРИ ЕГО ВЫЗОВЕ.  
```
## Совершенствуем код, по нахождению объёма параллепипеда:
``` 
public class BOXIC {
double width;
double depth;
double height;
    double volume (){
        return width*height*width;
    }
    void set_size (double a, double b, double c){
        width=a;
        depth=b;
        height=c;
    }
}
class BOXIC_DEMO{
    public static void main (String[] args){
        BOXIC mybox1 = new BOXIC();
        BOXIC mybox2 = new BOXIC();
        mybox1.set_size(12,12,2);
        mybox2.set_size(10,10,2);
        double vol;
        vol=mybox1.volume();
        System.out.println("First volume "+vol);
        vol=mybox2.volume();
        System.out.println("Second volume "+vol);
    }
}
```





