一、 进程与线程的区别

1.进程有独立的进程空间，进程中的数据
存放空间（堆空间和栈空间）是独立的。

2.线程的堆空间是共享的，栈空间是独立
的，线程消耗的资源也比进程小，相互之间可
以影响的。

二、创建线程的方法一（继承）

1． 子类覆写父类中的run方法，将线程运行
的代码存放在run中。

2． 建立子类对象的同时线程也被创建。

3． 通过调用start方法开启线程
  ```
class PrimeThread extends Thread {
long minPrime;
PrimeThread(long minPrime) {
this.minPrime = minPrime;
}
public void run() {
// compute primes larger than minPrime
. . .
}
}
  ```
然后，下列代码会创建并启动一个线程：
PrimeThread p = new PrimeThread(143);
p.start();

三、创建线程的方法二（实现）
实现Runnable接口

1． 子类覆盖接口中的run方法。

2． 通过Thread类创建线程，并将实现了
Runnable接口的子类对象作为参数传递给
Thread类的构造函数。

3． Thread类对象调用start方法开启线程。
可使用匿名内部类来写

四、线程中的一些方法

currentThread()：返回对当前正在执
行的线程对象的引用。

getName()：获取线程名称。

setName()设置线程名字;
