# 后端笔试题
## 2.语言基础
### 2.3双向链表
定义Node类
```java
class Node{
    int data;
    Node prev;//储存前一个结点
    Node next;//储存后一个结点
    public Node(int data){
        this.data=data;
        this.prev=null;
        this.next=null;
    }//定义构造方法，创建对象时传入该结点的数据
}//定义结点
```
定义DoublyLinkedList类
```java
class DoublyLinkedList{
    private Node head;
    public DoublyLinkedList(){
        head=null;
    }//构造函数将head的引用设为空
    //在尾部增加结点
    public void append(int data){
        Node newNode=new Node(data);
        if(head==null){
            head=newNode;
        }else{
            Node current=head;
            while(current.next!=null){
                current=current.next;
            }
            current.next=newNode;
            newNode.prev=current;
        }
    }
    //遍历链表
    public void printList(){
        Node current=head;
        while(current!=null){
            System.out.println(current.data+" ");
            current=current.next;
        }
        System.out.println();
    }
}

```
可以通过DoublyLinkedList创建双向链表对象，调用appen方法增加结点，调用printList方法打印链表，可以满足小埋存放每天睡觉小时数的要求。

---

#### 2.3.1复用
定义Node类
```java
class Node<T>{
    T data;
    Node prev;//储存前一个结点
    Node next;//储存后一个结点
    public Node(T data){
        this.data=data;
        this.prev=null;
        this.next=null;
    }//定义构造方法，创建对象时传入该结点的数据
}//定义结点
```
定义DoublyLinkedList类
```java
class DoublyLinkedList<T>{
    private Node head;
    public DoublyLinkedList(){
        head=null;
    }//构造函数将head的引用设为空
    //在尾部增加结点
    public void append(T data){
        Node newNode=new Node(data);
        if(head==null){
            head=newNode;
        }else{
            Node current=head;
            while(current.next!=null){
                current=current.next;
            }
            current.next=newNode;
            newNode.prev=current;
        }
    }
    //遍历链表
    public void printList(){
        Node current=head;
        while(current!=null){
            System.out.println(current.data+" ");
            current=current.next;
        }
        System.out.println();
    }
}

```
main方法运行示例：
```java
public class Main {
    public static void main(String[] args) {
        DoublyLinkedList dll=new DoublyLinkedList();
        dll.append("这一天写代码写太晚没有睡觉~");
        dll.append(20);
        dll.append(true);
        dll.printList();
    }
}
```
运行结果：
```java
这一天写代码写太晚没有睡觉~ 
20 
true
```
#### 2.3.3
main函数：
```java
public class Main {
    public static void main(String[] args) {
        DoublyLinkedList dll=new DoublyLinkedList();
        for (int i = 0; i < 20; i++) {
            dll.append(i);
        }//在链表中添加20个结点
        dll.circle(7);//在第七个结点成环
        dll.findcircle();//找出成环结点的位置，并消除环
        System.out.println("链表的长度为："+dll.length());//测试是否可以遍历链表来输出链表的长度
    }
}
```
DoublyLinkedList中的方法：
```java
class DoublyLinkedList<T>{
    private Node head;
    public Node point;
    public DoublyLinkedList(){
        head=null;
    }//构造函数将head的引用设为空
    //在尾部增加结点
    public void append(T data){
        Node newNode=new Node(data);
        if(head==null){
            head=newNode;
        }else{
            Node current=head;
            while(current.next!=null){
                current=current.next;
            }
            current.next=newNode;
            newNode.prev=current;
            point=newNode;
        }
    }
    //遍历链表
    public void printList(){
        Node current=head;
        while(current!=null){
            System.out.println(current.data+" ");
            current=current.next;
        }
        System.out.println();
    }
    public int length(){
        Node p=new Node(null);
        if(head==null)
            return 0;
        else p=head;
        int i=1;
        while(p.next!=null){
            p=p.next;
            i++;
        }
        return i;
    }//返回链表的长度
    public void circle(int p){
        Node point1;
        if(p<this.length())
            point1=head;
        else return;
        for (int i = 1; i < p; i++) {
            point1=point1.next;
        }
        Node mark=point1;
        while (point1.next!=null){
            point1=point1.next;
        }
        point1.next=mark;
    }//将链表的尾部接到第p个结点
    public void findcircle(){
        Node s1=head;
        Node s2=head;
        Node p=head;
        int i=1;
        while(s2!=null&&s2!=null){
            s1=s1.next;
            s2=s2.next.next;
            if(s1==s2) break;
        }
        //用s1和s2两个结点，s1每次前进一个结点，s2每次前进两个结点，两个结点将会在环中相遇，且此时s1还没有走完整个环
        //设头结点到成环结点s的长度为x，s到相遇的结点的距离为y，相遇结点到s的距离为z
        //则有2*(x+y)=x+y+n*(y+z),化简为x=(n-1)*(y+z)+z,可知将s1置于头结点，s1和s2同时逐个遍历，当s1到达s时，s2也到达
        s1=head;
        while(s1!=s2){
            s1=s1.next;
            s2=s2.next;
        }
        while (p!=s1){
            p=p.next;
            i++;
        }
        System.out.println("成环发生在第"+i+"个结点");
        while (p.next!=s1){
            p=p.next;
        }
        p.next=null;
    }//找出链表成环的位置，并消除环
}

```
运行结果
```java
成环发生在第7个结点
链表的长度为：20

Process finished with exit code 0
```
尝试过多个数据，该findcircle方法可以解决链表尾部成环的问题
### 2.4实践题-算法
该题的涉及到背包问题，使用动态规划的思路来解决，逐个增加背包的体积和炸弹的种类，依次找到每种组合下的最优解。
```java
import java.util.Scanner;
public class Keli {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt(); // 炸弹种类数量
        int V = scanner.nextInt(); // 背包容量
        int[] s = new int[N]; // 炸弹体积
        int[] w = new int[N]; // 炸弹威力
        int[] num = new int[N]; // 每种炸弹的数量限制
        for (int i = 0; i < N; i++) {
            s[i] = scanner.nextInt();
            w[i] = scanner.nextInt();
            num[i] = scanner.nextInt();
        }
        long startTime = System.currentTimeMillis();
        int[][] dp = new int[N + 1][V + 1];
        for (int i = 1; i <= N; i++) {
            for (int j = 0; j <= V; j++) {
                dp[i][j] = dp[i - 1][j]; // 初始化为上一行的值
                for (int k = 1; k <= num[i - 1] && k * s[i - 1] <= j; k++) {
                    dp[i][j] = Math.max(dp[i][j], dp[i - 1][j - k * s[i - 1]] + k * w[i - 1]);
                }//每增加一个炸弹都要考虑两种选择：不增加这个炸弹，或者空出体积放这个新炸弹，这两个选择中取总威力的最大值即为当前的最优解
                //同时还要考虑到不要超过炸弹的数量
            }
        }
        System.out.println("最多能装下的蹦蹦炸弹威力为：" + dp[N][V]);
        scanner.close();
        long endTime=System.currentTimeMillis();
        System.out.println("运行时间"+(endTime-startTime)+"毫秒");
    }
}

```
运行结果为：
```java
4 5
1 2 3
2 4 1
3 4 3
4 5 2
最多能装下的蹦蹦炸弹威力为：10
运行时间2毫秒
```
符合预期
## 2.5思考题
### 2.5.1 常见的排序算法及其复杂度（以从小到大排序为例）
- 插入排序（时间：O(n^2);空间：O(1)）：  
从第二个元素开始每个元素和前一个元素比较，若前一个数更大则该数后移，直到找到一个更小的数。
- 希尔排序（时间：O(n);空间：O(1)）  
先选定一个小于序列长度的数gap作为增量，每隔gap的数为一组，对每组进行插入排序，完成后再选择一个更小的gap进行排序，当gap减小到1时，即为对整个序列插入排序，完成排序。希尔排序先将待排序的序列预排序，时其接近有序，最后再插入排序。
- 选择排序：（时间：O(n^2);空间：O(n^2)）  
每次在序列中选择一个最小值和最大值，分别放在序列的开头和末尾，直到排完全部序列。
- 冒泡排序：（时间：O(n^2);空间：O(1)）  
每次从序列的开头开始排每相邻的两个，每次排完都可以将最大的一个数排到最后确定位置，依次这样排完整个序列。
- 归并排序（时间：O(nlongn);空间：O(n)）  
将序列从中间分成两部分，在将两部分分成四部分，直到分割成一个个的数据，再将这些数据两两比较归并到一起，直到归并成整个序列。
- 快速排序——三数取中（时间：O(nlongn);空间：O(longn)）  
在序列的头尾分别设一个指针low和high，先提取出第一个数，此时low为空，检测不为空的high，大于枢纽值则high左移，小于则填到low的位置，high为空，依次排完整个序列，直到high和low重合，将枢纽值填入该位置，就可以得到两个子序列，再依次对每个子序列用同样的方法排序。

---


### 2.5.2 语言特性
1. 面向对象和面向过程的内涵和区别：
面向过程一般是为了解决当前的问题来设计函数，对于其他不同的问题一般是难以复用的；而面向过程则是考虑到未来的使用，设计不同的类，在类中设计方法，通过继承、多态等功能使得程序不仅对于当前情景有作用，日后面对其他有相同特点的问题时也可以复用一部分，提高开发的效率，同时面向对象的封装特性使得可以将数据和行为封装在对象的内部，可以更好地修改和维护。面向过程的编程会更加适合轻量的程序编写，面向过程则更适合复杂的系统如大型软件的开发。  

---


2. Java 的拆箱和装箱过程以及其作用  
拆箱是将包装类对象转换成基本数据类型的过程，装箱则是将基本数据类型转换成包装类对象的过程，1.5以后版本的Java中都实现了自动装箱和拆箱的功能，不需要手动创建包装类对象或是用velueof方法等。  
作用：允许基本数据类型和Object类型的相互转换,可以通过这样的方法来使值类型适用于一些只能使用应用类型的场景，如集合类。  

---


3. String 类型的设计思路  
不可变性：一旦创建了String类的对象，其值就不能再更改，使得该类对象有这些优点：1.安全性：多个引用可以指向同一个对象，而不用担心其值会被修改；2.线程安全：可以被多个线程安全地共享，不需要额外的同步措施；3.缓存哈希码：哈希值可以在创建的时候就计算和储存，使得字符串在在哈希表等结构中的储存更加高效；4：提高了性能：可共享的字符串内容和创建时就计算和储存的哈希值，减少了内存的占用，提高了性能  
字符串池：String类的对象通常被储存在字符串池中，以便共享相同内容的字符串，创建字符串字面量时，Java会先检查字符串池中是否有相同的字符串，存在则返回其引用，不存在则会创建新的字符串并放入池中。  

---

4. JDK 8 版本中引入的 Lambda 表达式和函数编程的使用和实现  
在  JDK8引入的lambda表达式1.使得代码更加的简洁，开发者可以用更少的代码来表示函数或匿名内部类的实例；2.使Java支持函数式编程范式，可以将函数作为参数或者返回值；3.代码的组织更加简单和值观；4.和Stream API配合使用，可以更容易地实现并行编程。  
使用实例：  
用Function接口将字符串转换成整型数据之后输出
```java
public interface Function<T,R> {
    R apply(T t);
}

```
```java 
import java.util.function.Function;
public class Lambda {
    public static <R>R typeConver(Function<String,R> function){
        String str="66666";
        R result=function.apply(str);
        return result;
    }//定义typeConver方法，将String类型数据转换成泛型R
    public static void main(String[] args) {
        Integer result=typeConver(new Function<String,Integer>(){
            @Override
            public Integer apply(String s){
                return Integer.valueOf(s);
            }
        });//用Function接口创建一个匿名内部类，并重写其中的抽象方法
        System.out.println(result);
    }

}

```
lambda表达式对比
```Java
import java.util.function.Function;
public class Lambda {
    public static <R>R typeConver(Function<String,R> function){
        String str="66666";
        R result=function.apply(str);
        return result;
    }//定义typeConver方法，将String类型数据转换成泛型R
    public static void main(String[] args) {
        Integer result=typeConver((String s)->{
            return Integer.valueOf(s);
        });//利用lambda表达式，省去了直接创建匿名内部类的步骤，只需要写参数和函数体
        System.out.println(result);
    }

}
```

输出：
```java
66666

Process finished with exit code 0
```
可见lambda表达式简化了代码的书写，而且提高了代码的可读性  

---


Stream流函数式编程实践（在两个集合中过滤出前三个名字为三个字的男演员和姓林的女演员且去除第一个，将两个流合并，并生成实例输出姓名）：  

```java
package Stream;
public class Actor {
    private String Name;
    public Actor(String s){
        this.Name=s;
    }
    public String getname(){
        return Name;
    }
    public void setName(String s){
        this.Name=s;
    }
}

```
```Java
package Stream;
import java.util.ArrayList;
import java.util.stream.Stream;
public class StreamDemo {
    public static void main(String[] args) {
        ArrayList<String> manList = new ArrayList<String>();
        manList.add("周润发");
        manList.add("成龙");
        manList.add("刘德华");
        manList.add("吴京");
        manList.add("周星驰");
        manList.add("李连杰");
        ArrayList<String> womanList = new ArrayList<String>();
        womanList.add("林心如");
        womanList.add("张曼玉");
        womanList.add("林青霞");
        womanList.add("柳岩");
        womanList.add("林志玲");
        womanList.add("王祖贤");
        Stream<String> manStream=manList.stream().filter(s->s.length()==3).limit(3);//过滤前三个名字为三个字的男演员
        Stream<String> womenStream=womanList.stream().filter(s->s.startsWith("林")).skip(1);//过滤出姓林的女演员且略去第一个
        Stream<String> all=Stream.concat(manStream,womenStream);//合并两个流
        all.map(Actor::new).forEach(s-> System.out.println(s.getname()));//调用构造方法，输出每个实例的Name

    }
}
```
可见lambda表达式配合Stream API可以很大程度上简化代码，提高代码的可读性，函数式编程也可以编写更易于维护和拓展的代码，更轻松地使用并行操作。  

---


5. Java 中全限定名称相同的两个类的 Class 对象一定 equals() 吗?  
不一定，两个“class”对象是否相同取决于它们的加载器是否相同，全限定名称相同的两个类对象若加载器不同那么也不会equal()
```java
// 自定义类加载器
class CustomClassLoader1 extends ClassLoader {
    // 实现自定义类加载逻辑
}
class CustomClassLoader2 extends ClassLoader {
    // 实现自定义类加载逻辑
}
class ClassA{

}
class ClassB{

}
public class ClassLoder {
    public static void main(String[] args) throws ClassNotFoundException {
        // 使用不同的类加载器加载同一个类
        ClassLoader classLoader1 = ClassA.class.getClassLoader();
        ClassLoader classLoader2 = new CustomClassLoader1();

        Class<?> class1 = classLoader1.loadClass("FuctionalInterface.Lambda");
        Class<?> class2 = classLoader2.loadClass("FuctionalInterface.Lambda");

        System.out.println(class1 == class2); // 可能返回 false
        System.out.println(class1.equals(class2)); // 可能返回 false

    }
}
//尝试了一下好像不行呀
```

---

#### 2.5.3集合

1. 请介绍一下 ArrayList 和 LinkedList 的区别  
ArrayList的底层实现是数组，可以通过索引直接找到元素，遍历上的效率较高，当数组的空间不够时，会再开个原来1.5倍大的新数组，并将原来的数据储存到这个新数组中，这可能会浪费大量的内存，但是可以通过ensureCapacity方法来将容量设置到指定大小，或者通过trimToSize方法来将容量大小设置到当前含的元素的大小。  
LinkedList的底层逻辑是双向链表，所以它不能像数组那样通过索引直接找到元素，相比于LinkedList来说再遍历上的性能较低，由于通过链表实现，LinkedList不需要像ArrayList那样1.5倍扩容，在增减元素上性能较好。  
因此频繁查找和修改元素时，一般使用ArrayList；频繁增减元素时，一般使用LinkedList。  
2. 请介绍一下 HashMap 的实现方式  
HashMap是一种基于哈希表实现的数据结构，它使用一个数组来储存数据，当插入一个键值对是，HashMap会根据键的哈希值计算出在数组中的位置，然后将该键值对添加到相应的链表中，对键值对进行其他操作时，HashMap也会根据键的哈希值找到其在数组中的位置，然后在相应的链表中进行操作，Java8中，链表的长度大于8时会将链表转化为红黑树，以提高查找效率，当红黑树节点数小于6时，会将其转换为链表。

---

#### 并发  
1. 请介绍一下进程/线程/协程的区别  
进程是操作系统中的独立执行单位，有独立的内存空间和资源，进程有较高的隔离性，不能直接共享内存，进程崩溃也不会对其他的进程产生直接的影响。  
线程是进程内的执行单位，共享同一进程的内存和资源，线程之间可以更加轻松地通信，切换线程比切换进程要更加轻量级。
协程是一种轻量级的线程，不依赖于操作系统的进程或线程，由编程语言或库提供支持，通常在单个线程里执行。
2.	请介绍一下你对并发的理解, 以及一些保证线程安全的方法  
并发是指在多核计算机或在多个计算机上同时执行多个任务的能力。并发的目的是让多个进程或线程在同一时间段内执行，同时有效地管理执行线程，以避免数据竞争等并发问题，提高程序的性能和响应性。  
保证线程安全的方法：1.互斥锁：用于保证任何时候都只有一个线程可以访问共享资源，可以通过'synchronized'关键字来创建互斥锁；2.线程池：可以限制并发线程的数量，避免创建过多的线程。  
3. 操作系统中线程的实现方式  
线程在用户空间下实现（用户线程）（多对一）：所有的线程都在用户空间实现，在操作系统看来每个进程只有一个线程，；进行线程切换的速度要远快于在通过操作系统内核切换，同时程序员可以在用户空间实现自己的线程调度算法，当线程数量多时，也不会大量占据操作系统的空间；但是当进程中的一个线程阻塞（如等待输入）时会阻塞整个进程，或者一个线程长时间不释放CPU，会导致其他线程的u到cpu而持续等待。  
线程在操作系统内核实现（内核线程）（一对一）：线程由操作系统内核直接支持和管理，提供了多线程的高度并发性和并行性，可以充分利用多核的处理器，但是线程的切换开销较大。  
混合模式（多对多）：程序员可以自行决定使用多少用户线程和内核线程，结合了前两种方式的优点  
4. jvm中线程的实现方法  
每个Java线程都可以由一个Java线程对象表示，这些对象由jvm管理，jvm的线程对象可以映射到内核线程或者用户线程（即上题说到的三种模型），这取决于jvm的具体实现，jvm负责线程的创建、销毁和调度已经线程同步和线程通信，提供了内置的同步机制，同时还允许开发人员调整线程池大小等。  
5. Java中synchronized关键字的作用和实现方式  
作用:保证同一时刻只有一个线程可以执行某个方法或者某个代码块，保证一个线程的变化可以被其他的线程看到。  
原理：每个线程进入同步代码块（即synchronized修饰的代码块）时，都会尝试获取对象的监视器锁，如果锁被其他线程占用，线程将进入阻塞状态，直到进入同步代码块的线程执行完毕或者调用wait()方法，锁被释放  

---

#### 异常  
1. 为什么要有对异常的处理  
- 可靠性：通过捕获和处理异常，程序可以在发生错误的时候做出正确的处理，而不会因为错误而导致程序崩溃不能运行  
- 有助于问题的诊断，可以从异常信息中了解到错误的类型，位置等信息  
- 兼容性：使得程序可以在不同的环境下更加健壮地运行，可以适用于不同的错误和异常情况
- 可读性：将错误处理代码和正常业务逻辑分开，提高代码的可读性，有助于代码的理解和维护
2. 异常的抛出和捕获方法  
抛出：创建一个异常对象，并使用throw关键字来抛出，例如：
```java
public class Main {
    public static void main(String[] args) {
        throw new IllegalArgumentException("error");

    }
}

```
运行结果
```java
Exception in thread "main" java.lang.IllegalArgumentException: error
	at Main.main(Main.java:3)
```  
捕获：异常被抛出时，可以用try-catch来捕获和处理异常，try包含可能引发异常的代码，catch用于捕获和处理异常，可以在try之后使用多个catch来捕获不同的异常，来进行不同的处理，例如：
```java
public class Main {
    public static void main(String[] args) {
        String s=null;
        try {
            int length=s.length();
            int num=10/0;
        } catch (ArithmeticException e) {
            System.out.println("An error occurred: " + e.getMessage());
        }catch(NullPointerException E){
            System.out.println("空引用");
        }
    }
}
```
运行结果
```java
空引用
```
代码中用到了两个catch，分别捕获算数异常和空引用异常，try包含的代码中，先抛出了空引用的异常，所以被第二个catch捕获并处理。  
3. try-catch-finally模块中finally的执行逻辑  
finally包含的代码会在try和catch中的代码执行后无论是否发生异常都执行。finally通常用来进行资源的释放和清理工作，如在try中打开文件读取，无论是否发生异常都关闭文件。

---

### 设计模式
1. 对设计模式的理解  
设计模式是人间开发人员在开发过程中面临的一般问题的解决方案；是项目迭代的过程中，为了实现一些功能，设计了一些方案，根据这些方案总结出的一些模式体系，并且这些体系被很多开发者接受使用。设计模式广泛地运用于大的项目中，让代码可以更容易被他人理解，保证代码的可靠性。  
2. 单例模式，写一个线程安全的单例模式  
单例模式属于设计模式中的创造型模式，定义是：保证一个类仅有一个实例，并提供一个访问它的全局访问点。单例模式可以减少内存的开销（如网站首页界面的缓存），避免对资源的多重占用（如文件的读写）  
线程安全的单例模式
```java
package com.example.mysql.controller;

public class Singleton {
    private volatile static Singleton single;//声名为volatile，确保多线程之间对single可见

    private Singleton() {
        // 私有构造函数
    }
    public static Singleton getsingle() {
        if (single == null) {  // 第一次检查
            synchronized (Singleton.class) {
                if (single == null) {  // 第二次检查
                    single = new Singleton();//创建对象
                }
            }
        }
        return single;
    }
}

```

3. 生产者消费者模式是一种多线程设计模式，不属于经典的设计模式，用于解决多线程的环境下，生产者和消费者数据的协同问题。在生产者消费者模式中，生产者和消费者共享一个资源池（缓冲区），生产者线程负责生成数据或任务，并将它们放入资源池，消费者从资源池中获取数据或任务，并执行操作。生产者消费者模式有利于实现线程之间的协作和数据共享，确保数据的安全传递。  
使用synchronized、wait、notify实现生产者消费者模式示例
```java 
package com.example.mysql.controller;

import java.util.concurrent.TimeUnit;

//使用 synchronized和wait、notify实现生产者和消费者
//1.定义资源类
class MyCacheResources1 {

    int num = 0;//共享资源：生产和消费数字

    private int count = 0;//资源池中实际存储的数据个数

    private int capacity = 5;//资源池中允许存放的资源数目

    Object obj = new Object();//作为锁

    //生产方法
    public void product() throws InterruptedException {
        //使用代码块，精确加锁，且synchronized会自动释放锁
        synchronized (obj) {
            //当实际元素数量达到总容量是，生产阻塞等待
            if (count == capacity) {
                obj.wait();
            }
            //产生数据
            num++;
            count++;
            System.out.println(Thread.currentThread().getName() +
                    "生产了一个数字" + num + "，资源池剩余数据个数：" + count);
            //唤醒其他所有线程，让他们竞争锁
            obj.notifyAll();
        }
    }

    //消费的方法
    public void consumer() throws InterruptedException {
        synchronized (obj) {
            //当资源池中没有资源时，消费阻塞，等待
            if (count == 0) {
                obj.wait();
            }
            //消费数据
            num--;
            count--;
            System.out.println(Thread.currentThread().getName() +
                    "消费了一个数字" + num + "，资源池剩余数据个数：" + count);
            //唤醒其他所有线程，让他们竞争锁
            obj.notifyAll();
        }
    }
}

public class ProductAndConsumerTest1 {
    public static void main(String[] args) {
        MyCacheResources1 myCacheResources1 = new MyCacheResources1();
        //用lamda表达式来创建线程
        //生产者
        new Thread(() -> {
            for (int i = 1; i <= 10; i++) {//生产10轮
                try {
                    myCacheResources1.product();

                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }

        }, "生产者").start();

        //消费者1
        new Thread(() -> {
            //让生产者先 生产数据
            for (int i = 1; i <= 10; i++) {//消费10轮，

                try {
                    myCacheResources1.consumer();
                    TimeUnit.SECONDS.sleep(1);//模拟消费时间
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
        }, "消费者1").start();
        //消费者2
        new Thread(() -> {
            //让生产者先 生产数据
            for (int i = 1; i <= 10; i++) {

                try {
                    myCacheResources1.consumer();
                    TimeUnit.SECONDS.sleep(1);
                } catch (InterruptedException e) {

                    e.printStackTrace();
                }
            }
        }, "消费者2").start();

    }
}


```
运行结果：
```java
生产者生产了一个数字1，资源池剩余数据个数：1
生产者生产了一个数字2，资源池剩余数据个数：2
生产者生产了一个数字3，资源池剩余数据个数：3
生产者生产了一个数字4，资源池剩余数据个数：4
生产者生产了一个数字5，资源池剩余数据个数：5
消费者2消费了一个数字4，资源池剩余数据个数：4
消费者1消费了一个数字3，资源池剩余数据个数：3
生产者生产了一个数字4，资源池剩余数据个数：4
生产者生产了一个数字5，资源池剩余数据个数：5
消费者2消费了一个数字4，资源池剩余数据个数：4
生产者生产了一个数字5，资源池剩余数据个数：5
消费者1消费了一个数字4，资源池剩余数据个数：4
生产者生产了一个数字5，资源池剩余数据个数：5
消费者2消费了一个数字4，资源池剩余数据个数：4
生产者生产了一个数字5，资源池剩余数据个数：5
消费者1消费了一个数字4，资源池剩余数据个数：4
消费者2消费了一个数字3，资源池剩余数据个数：3
消费者1消费了一个数字2，资源池剩余数据个数：2
消费者2消费了一个数字1，资源池剩余数据个数：1
消费者1消费了一个数字0，资源池剩余数据个数：0

```

## Http
### Http请求
假设前端在一个请求的 URL 中传来了 name 和 type 参数, 请你从前端请求中取出参数, 并将其以 name-type 的形式返回给前端.
用到的类：
```java
package com.cy.receive_param.pojo;
//封装实体类（存放前端数据）
public class User {
    private String username;
    private String type;
    private Cat cat;

    @Override
    public String toString() {
        return "User{" +
                "username='" + username + '\'' +
                ", type='" + type + '\'' +
                ", cat=" + cat +
                '}';
    }

    public Cat getCat() {
        return cat;
    }

    public void setCat(Cat cat) {
        this.cat = cat;
    }

    public String getUsername() {
        return username;
    }

    public void setUsername(String username) {
        this.username = username;
    }

    public String gettype() {
        return type;
    }

    public void settype(String type) {
        this.type = type;
    }


}

```

0. controller中的方法：
```java
//接收RESTful风格的数据
    @RequestMapping("add3/{name}/{type}")
    //占位符和形参相同时用pathvariable给上映射关系会直接传递，不同时这需要注明传递的相应占位符
    public String add3(@PathVariable("name") String username, @PathVariable String type){
        System.out.println("username:"+username);
        System.out.println("type:"+type);
        return username+"-"+type;
    }
```

从url中获得name和type并返回name-type
![Alt text](image.png)
1. controller中的方法
```java
@RequestMapping("add1")
    public String add1(String username,String type){
        System.out.println("username="+username);
        System.out.println("username="+type);
        return username+"-"+type;
    }
```
从body中获得name和type并返回name-type
![Alt text](image-1.png)
2. controller中的方法
```java
@RequestMapping("add7")
    //获取请求头的auth，如果不存在则将authHeader设为null
    public String add7(@RequestHeader(value = "Authorization", required = false) String authHeader,User user) {
        if (authHeader != null && authHeader.equals("Love Star Studio")) {
            // 如果Authorization中的数据是"Love Star Studio"则返回name-type数据
            System.out.println(authHeader);
            return user.getUsername()+"-"+user.gettype();
        } else {
            System.out.println(authHeader);
            // 返回 "Invalid User"
            return "Invalid User";
        }
    }
```
auth存在且为Love Star Studio返回name-type
![Alt text](image-2.png)
auth不存在返回Invalid User
![Alt text](image-3.png)
3. 封装的User类已在上面说明  
controller中的方法：
```java
//参数较多时实体类会更加方便简洁
    //前端提交的参数名称需要和类的属性名称保持一致
    @RequestMapping("add2")
    public String add2(User user){
        System.out.println(user);
        return user.getUsername()+"-"+user.gettype();
    }
```
返回数据
![Alt text](image-4.png)
### 3.3结合数据库一起写在后端应用中
controller包HepanUserController类
```java
package com.example.mysql.controller;

import com.example.mysql.entity.HepanUser;
import com.example.mysql.service.HepanUserService;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

import java.util.List;

@RestController
@RequestMapping("/hepanUser")
public class HepanUserController {
    @Autowired
    HepanUserService hepanUserService;

    //添加帖子
    @PostMapping
    public ResponseEntity<HepanUser> add(@RequestBody HepanUser user) {
        hepanUserService.add(user);
        return new ResponseEntity<>(user, HttpStatus.CREATED);
    }

    //删除帖子
    @DeleteMapping("/{id}")
    public ResponseEntity<String> delete(@PathVariable Integer id) {
        hepanUserService.delete(id);
        return new ResponseEntity<>(id + " deleted", HttpStatus.OK);
    }

    //更改帖子
    @PutMapping
    public ResponseEntity<HepanUser> update(@RequestBody HepanUser user) {
        hepanUserService.update(user);
        return new ResponseEntity<>(user, HttpStatus.OK);
    }

    //获取全部帖子信息
    @GetMapping
    public ResponseEntity<List<HepanUser>> selectAll() {
        List<HepanUser> allinfo = hepanUserService.selectAll();
        return new ResponseEntity<>(allinfo, HttpStatus.OK);
    }

    //获取对应编号帖子的信息
    @GetMapping("/{id}")
    public ResponseEntity<HepanUser> selectById(@PathVariable Integer id) {
        HepanUser user = (HepanUser) hepanUserService.selectById(id);
        if (user == null) {
            return new ResponseEntity<>(HttpStatus.NOT_FOUND);
        }
        return new ResponseEntity<>(user, HttpStatus.OK);
    }

    //获取对应名字用户的信息
    @GetMapping("/{name}")
    public ResponseEntity<List<HepanUser>> getUsersByName(@RequestParam String name) {
        List<HepanUser> userList = hepanUserService.selectByName(name);
        return new ResponseEntity<>(userList, HttpStatus.OK);
    }

    //获取对应用户名和帖子内容的帖子
    @GetMapping("/More")
    public ResponseEntity<List<HepanUser>> getUsersByCriteria(
            @RequestParam(value = "username", required = false) String username,
            @RequestParam(value = "post", required = false) String post) {
        List<HepanUser> userList = hepanUserService.selectByMore(username, post);
        return new ResponseEntity<>(userList, HttpStatus.OK);
    }

    //查找对应模糊信息的帖子
    @GetMapping("/Vaguely")
    public ResponseEntity<List<HepanUser>> searchVaguely(
            @RequestParam(value = "username", required = false) String username,
            @RequestParam(value = "post", required = false) String post) {
        List<HepanUser> userList = hepanUserService.selectVaguely(username, post);
        return new ResponseEntity<>(userList, HttpStatus.OK);
    }
}

```

entity包HepanUser类
```java
package com.example.mysql.entity;

import lombok.Getter;
import lombok.Setter;

import java.util.Date;

@Getter
@Setter
public class HepanUser {
    private Integer id;
    private String username;
    private String post;
    private Date date;

    @Override
    public String toString() {
        StringBuilder sb = new StringBuilder();
        sb.append("id: ").append(id).append("\n");
        sb.append("username: ").append(username).append("\n");
        sb.append("post: ").append(post).append("\n");
        sb.append("date: ").append(date).append("\n");
        return sb.toString();
    }

}


```
service包HepanUserService类
```java
package com.example.mysql.service;

import com.example.mysql.entity.HepanUser;
import com.example.mysql.mapper.HepanUserMapper;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;

import java.util.Date;
import java.util.List;

@Service
public class HepanUserService {
    @Autowired
    HepanUserMapper hepanUserMapper;


    public void add(HepanUser user) {
        Date currentDate = new Date();
        hepanUserMapper.insert(user, currentDate);
    }

    public void delete(Integer id) {
        hepanUserMapper.delete(id);
    }

    public void update(HepanUser user) {
        Date currentDate = new Date();
        hepanUserMapper.update(user, currentDate);
    }

    public List<HepanUser> selectAll() {
        List<HepanUser> list = hepanUserMapper.selectAll();
        return list;
    }

    public HepanUser selectById(Integer id) {
        return hepanUserMapper.selectById(id);

    }

    public List<HepanUser> selectByName(String name) {
        return hepanUserMapper.selectByName(name);

    }

    public List<HepanUser> selectByMore(String username, String post) {
        return hepanUserMapper.selectByMore(username, post);
    }

    public List<HepanUser> selectVaguely(String username, String post) {
        return hepanUserMapper.selectVaguely(username, post);
    }
}

```

mapper包HepanUserMapper类
```java
package com.example.mysql.mapper;

import com.example.mysql.entity.HepanUser;
import org.apache.ibatis.annotations.*;

import java.util.Date;
import java.util.List;

@Mapper
public interface HepanUserMapper {


    @Insert("insert into `hepanuser`(username,post,date) values(#{user.username},#{user.post},#{date})")
    void insert(HepanUser user, Date date);

    @Delete("DELETE FROM `hepanuser` WHERE id=#{id}")
    void delete(Integer id);

    @Update("update `hepanuser` set username=#{user.username},post=#{user.post},date=#{date} where id=#{user.id}")
    void update(HepanUser user, Date date);

    @Select("select * from `hepanuser` order by date desc")
    List<HepanUser> selectAll();

    @Select("select * from `hepanuser` where id=#{id}")
    HepanUser selectById(Integer id);

    @Select("select * from `hepanuser` where username=#{name}")
    List<HepanUser> selectByName(String name);

    @Select("select * from `hepanuser` where username=#{username} and post=#{post} order by date desc")
    List<HepanUser> selectByMore(@Param("username") String username, @Param("post") String post);

    @Select("select * from `hepanuser` where username like concat('%',#{username},'%') and post like concat('%',#{post},'%') order by date desc")
    List<HepanUser> selectVaguely(String username, String post);
}

```



### 3.4思考题
1. RESTful API使用标准的HTTP方法来执行操作，益于理解和使用；同时每个请求都包含了处理请求所需要的所有信息，提高了可拓展性，降低了服务器资源的使用。  
2. 域名是用户访问网站时的文本标识，www.baidu.com；ip即Internet Protocol，是互联网上每个计算机或设备的唯一数字标识，例如我的计算机主系统在无线局域网的ipv4地址为192.168.137.1，由于ipv4的地址空间无法满足增长的设备数量，所以支持更多设备的ipv6正逐渐取代ipv4；端口是设备上运行的特定应用程序的标识符，通常是十六位的整数，例如默认情况下http端口为80，https为443。  
当使用域名访问网站或服务时，DNS将域名解析为相应的IP地址，然后数据包通过IP地址的特定端口路由到应用程序。这三者共同构成了互联网通信的基础。
3. HTTP是用于传输超文本数据的协议，以明文形式传输；HTTPS是HTTP的安全版本，数据在传输过程中经过加密。HTTP和HTTPS的区别主要在于安全性；  
还有HTTP不提供数据完整性验证，而HTTPS提供，这可以检测到数据在传输过程中是否被篡改；  
默认端口方面HTTP默认端口为80，而HTTPS默认端口为443
4. 结构：请求行（request line）-请求头部（header）-空行-请求正文（request body）  
请求行：请求的方法（GET、POST等）/url/http协议版本
请求头：通常以键值对形式组织，包含关于请求的相关信息，如User-Agent、Accept等  
空行：用于分隔头部和正文  
请求正文：包含请求的数据，通常用于POST请求或其他需要在请求中传递数据的请求  
5. 四次挥手指的是TCP链接关闭时的四个步骤，用于确保数据的可靠传输和上方的链接正常关闭。  
第一次：需要关闭连接的一方发送一个TCP报文，包含FIN标志位，表示要求关闭连接，发送后该方进入FIN-WAIT-1状态。  
第二次：被动关闭方收到含FIN的报文后发送一个ACK作为响应，然后进入CLOSE-WAIT状态，此时仍然可以向主动关闭方发送未发送完的数据。  
第三次：被动关闭方完成了数据的发送后，发出一个FIN报文，要求关闭连接，然后进入LAST-ACK状态。  
第四次：主动关闭方收到被动关闭方的FIN报文后，发送一个ACK报文，表示确认，被动关闭方收到后立刻关闭连接，主动关闭方进入TIME-WAIT状态，一段时间后关闭连接，确保网络中的延迟数据包都接收完。 ps:如果被动关闭方没有接收到第四次挥手的ACK报文，会再次发送FIN报文，以确保在网络信道不稳定时可靠地断开连接。  
四次挥手可以确保数据的完整性，确保连接关闭后不会有潜在的数据包的干扰。
6. WebSocket协议是一种用于在客户端和服务器之间建立持久性全双工连接的通信协议。它的出现是为了解决http协议存在的一些限制，如客户端必须发起请求才能收到服务器的响应，WebSocket允许双方建立一个持久且可以双向传输的连接，且可以通过加密来提高数据的安全性。这些减少了频繁创建和关闭连接的性能开销，使应用程序的交互更加实时。但是WebSocket也存在部署的复杂性和兼容性问题。  
应用方面，WebSocket比HTTP更加适合于需要实时通信的程序，比如网页游戏、视频通话等，而HTTPS更加适合于简单的静态内容传输，如资料的查询。
### 3.5文件接收
```java
package com.example.restful_api.Controller;

import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;
import org.springframework.web.multipart.MultipartFile;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
@RestController
public class GetFile {
    @PostMapping("upload")
    //将请求中的名为“file”的参数传递到MultiparFile对象上
    public String getFile(@RequestParam("file") MultipartFile file) {

        if (!file.isEmpty()) {
            try {
                //限定文件格式为png、jpg
                String originalFilename = file.getOriginalFilename();
                if(originalFilename.toLowerCase().endsWith(".png")||originalFilename.toLowerCase().endsWith(".jpg")){
                //限制文件大小在200MB
                if (file.getSize() <= 200 * 1024 * 1024) {
                    //将文件读取到字节组中
                    byte[] bytes = file.getBytes();
                    // 将图片数据保存到指定的目录中,并用原文件名作为文件名
                    Files.write(Paths.get("D:\\HuaweiMoveData\\Users\\86191\\Desktop\\后端笔试", file.getOriginalFilename()), bytes);
                    return "redirect:/success";
                }
                else return "Larger than 200MB";
                }
                else return "Only .png files are allowed";
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
        return "redirect:/failure";
    }
}

```
![Alt text](<屏幕截图 2023-10-21 161838.png>)
![Alt text](<屏幕截图 2023-10-21 161918.png>)
## 数据库
### 4.2数据库基础
![Alt text](Capture_20231021_172901.jpg)
学生表：学号、姓名、性别、班级号；主键：学号  
班级表：班级号、班级名、人数；主键：班级号  
老师表：教师编号、姓名、性别、学科；主键：编号  
老师班级表：学科、教师编号、班级号；主键：班级号、教师编号  
### 4.3操作数据库
![Alt text](image-7.png)
表的创建、数据填写
```sql
-- 创建学生表
CREATE TABLE Students (
    StudentID INT PRIMARY KEY,
    Name VARCHAR(255),
    Sex VARCHAR(10),
    ClassID INT,
    FOREIGN KEY (ClassID) REFERENCES Classes(ClassID)
);

-- 创建班级表
CREATE TABLE Classes (
    ClassID INT PRIMARY KEY,
    ClassName VARCHAR(255),
    NumberOfStudents INT
);

-- 创建老师表
CREATE TABLE Teachers (
    TeacherID INT PRIMARY KEY,
    Name VARCHAR(255),
    Sex VARCHAR(10),
    Subject VARCHAR(255)
);

-- 创建老师班级表
CREATE TABLE TeacherClasses (
    TeacherID INT,
    ClassID INT,
    Subject VARCHAR(255),
    PRIMARY KEY (TeacherID, ClassID),
    FOREIGN KEY (TeacherID) REFERENCES Teachers(TeacherID),
    FOREIGN KEY (ClassID) REFERENCES Classes(ClassID)
);

-- 增
insert into classes values (1,'一班',4);
insert into classes values (2,'二班',5);
insert into classes values (3,'三班',6);
insert into classes values (4,'四班',4);
insert into classes values (5,'五班',5);

insert into Students values(1,'颗粒','f',2);
insert into Students values(2,'有啦','f',2);
insert into Students values(3,'胡桃','f',2);
insert into Students values(4,'雷电将军','f',1);
insert into Students values(5,'审理零花','f',1);
insert into Students values(6,'小工','f',3);
insert into Students values(7,'干预','f',4);
insert into Students values(8,'审核','f',3);
insert into Students values(9,'七七','f',4);
insert into Students values(10,'客情','f',5);
insert into Students values(11,'琴','f',4);
insert into Students values(12,'莫娜','f',5);
insert into Students values(13,'心海','f',1);
insert into Students values(14,'钟离','m',2);
insert into Students values(15,'那维莱特','m',5);
insert into Students values(16,'万叶','m',2);
insert into Students values(17,'小红','m',4);
insert into Students values(18,'小橙','m',5);
insert into Students values(19,'小黄','m',3);
insert into Students values(20,'小绿','m',3);
insert into Students values(21,'小青','m',3);
insert into Students values(22,'小蓝','m',3);
insert into Students values(23,'小紫','m',5);
insert into Students values(24,'小康','m',1);

insert into Teachers values(1,'刘老师','m','数学');
insert into Teachers values(2,'王老师','m','语文');
insert into Teachers values(3,'廖老师','f','英语');
insert into Teachers values(4,'谢老师','f','语文');
insert into Teachers values(5,'李老师','m','英语');

insert into TeacherClasses values(1,1,'数学');
insert into TeacherClasses values(1,2,'数学');
insert into TeacherClasses values(1,3,'数学');
insert into TeacherClasses values(1,4,'数学');
insert into TeacherClasses values(1,5,'数学');
insert into TeacherClasses values(3,1,'英语');
insert into TeacherClasses values(3,2,'英语');
insert into TeacherClasses values(3,3,'英语');
insert into TeacherClasses values(5,4,'英语');
insert into TeacherClasses values(5,5,'英语');
insert into TeacherClasses values(2,1,'语文');
insert into TeacherClasses values(2,2,'语文');
insert into TeacherClasses values(4,3,'语文');
insert into TeacherClasses values(4,4,'语文');
insert into TeacherClasses values(4,5,'语文');
```
删：
```sql
SET SQL_SAFE_UPDATES = 0;
DELETE FROM Students
WHERE Name='小康';
```
改(将小红的Sex改为f)
```sql
update Students
set Sex='f'
where Name='小红';
```

查（查找全部Students数据）
```sql
select * from Students;
```
![Alt text](image-5.png)  
统计每个老师有多少学生：
```sql
SELECT t.Name, COUNT(s.StudentID) AS StudentCount
FROM Teachers t
JOIN TeacherClasses tc ON t.TeacherID = tc.TeacherID
JOIN Students s ON tc.ClassID = s.ClassID
GROUP BY t.TeacherID
ORDER BY StudentCount DESC;
```
将teachserclasses和Teachers关联  
将Students和teacherclasses关联  
根据老师的id分组，分别统计每组的学生数  
根据学生数降序排列  
输出老师的name和学生数  
![Alt text](image-6.png)
### 4.4思考题
ACID分别表示原子性、一致性、隔离性、持久性，这些是确保数据库操作可靠性和一致性的关键特性。  
原子性Atomicity：事务中的每个操作都一个不可分割的工作单位，事务中的操作要么全部成功要么全部失败，每次对数据改动时，都将对应的undolog记录下来，如果某次操作异常，就会反向执行每次操作的undolog，让所以数据回到操作之前。  
隔离性isolation：多个事务并行执行时，每个事务都被隔离开，不能相互干扰，分为写与写隔离和写与读隔离。  
持久性durability:事务一旦成功提交就，结果就永久地保存在数据库中了。  
一致性consistency：确保事务的执行前后，数据库的状态都是一致且稳定的。前三个特性可以说是为一致性服务的。
### 4.5思考题
数据表如下图：  

RBAC0:RBAC0是RABC的核心，定义了能构成RABC控制系统的最小的元素集合，由用户、角色、会话、许可四部分组成。用户和角色、角色和许可都是多对多的关系，用户和会话、会话和角色都是一对一的关系，当角色被指定给用户时，用户就拥有了改角色所包含的许可，用户要通过会话才能设置角色。  
RABC1:是RABC的分层模型，建立在RABC0的基础上，在角色中引入了继承的概念。使用场景：分店的店长有访问自己分店财务数据的权限，老板有访问所有分店的财务数据的权限。  
RABC2:是RABC的约束模型，建立在RABC0的基础上，加入了约束的概念，主要引入了静态职责分离SSD(Static Separation of Duty)和动态职责分离DSD(Dynamic Separation of Duty)。SSD是角色指派给用户阶段加入的，主要有：互斥角色（两个互斥角色只能有一个）、基数约束（用户拥有的角色权限和角色对应的用户数是有限的）、先决条件约束：（要高级角色必须先有低级角色），DSD是会话和角色之间的约束，可以动态约束用户拥有的角色，如一个用户有两个角色但只能激活一个。
使用场景：互斥角色：财务部的会计和审核；基数约束：CEO只能有一个，某人不能同时是COO和CFO；先决条件约束：要是豪华VIP得先是VIP；DSD：用户既有参赛者和评委身份只能用一个，三国杀抽多张武将只能选一个。  
RABC3：是RABC1和RABC2的合集。
## 5.后端应用
### 5.1实践题见3.4
### 5.2
JWT权限认证：用户登入时，生成一个JWT返回给客户端，在客户端的每个请求中包含JWT，服务端验证JWT的签名检查用户的权限声明（如角色标识）是否有权执行相应的操作，有权则执行操作，无权则返回信息告知用户。
### 5.3
1. 利用数据库中主键的唯一性，适用于插入操作。
2. 数据库乐观锁，在表中多加一个字段，作为版本标识，执行更新时不仅验证id还要验证版本，防止重复更新，确定是要更新的内容，使用于更新操作 。
3. 防重Token，客户端先调用接口获取Token，服务端会生成一个Token串，将其作为key储存到Redis数据库中（设置过期时间），再将Token返回到客户端，客户端把Token存入请求的Header中，发送请求，服务端根据请求中的Token到数据库中查找对应的key是否存在，存在且value匹配则删除然后执行业务，否则返回错误信息，适用于插入、更新、删除。


