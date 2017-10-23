---
layout: post
title:  "JavaSE高级"
date:   2017-10-19
comments: true
---

* [1、多线程](#multithreading)
* [2、经典多线程问题](#threadProblems)
* [3、GUI图形用户界面](#gui)
* [4、网络编程](#internet)
* [5、反射](#reflection)
* [6、复杂设计模式](#complexDesign)

<h1 id="multithreading">一：多线程</h1>

* ### 一：线程的生命周期及五种基本状态  

![image](http://images.cnitblog.com/i/426802/201406/232002051747387.jpg)

* #### <font color="red">线程的五种基本状态</font>
* **新建状态（New）：**当线程对象被创建后，即进入了新建状态，如：Thread t = new MyThread();
* **就绪状态（Runnable）：**当调用线程对象的start()方法（t.start();），线程即进入就绪状态。处于就绪状态的线程，只是说明此线程已经做好了准备，随时等待CPU调度执行，并不是说执行了t.start()此线程立即就会执行；
* **运行状态（Running）:**当CPU开始调度处于就绪状态的线程时，此时线程才得以真正执行，即进入到运行状态。注：就绪状态是进入到运行状态的唯一入口，也就是说，线程要想进入运行状态执行，首先必须处于就绪状态中；
* **阻塞状态（Blocked）:**处于运行状态中的线程由于某种原因，暂时放弃对CPU的使用权，停止执行，此时进入阻塞状态，直到其进入到就绪状态，才有机会再次被CPU调用以进入到运行状态。根据阻塞产生的原因不同，阻塞状态又可以分为三种：

* * **等待阻塞：**运行状态中的线程执行wait()方法，使本线程进入到等待阻塞状态；

* * **同步阻塞：**线程在获取synchronized同步锁失败(因为锁被其它线程所占用)，它会进入同步阻塞状态；

* * **其他阻塞：**通过调用线程的sleep()或join()或发出了I/O请求时，线程会进入到阻塞状态。当sleep()状态超时、join()等待线程终止或者超时、或者I/O处理完毕时，线程重新转入就绪状态。

* **死亡状态（Dead）:**线程执行完了或者因异常退出了run()方法，该线程结束生命周期。

* ### 二：Java多线程的创建及启动  

* Java中线程的创建常见有三种基本形式

- - 1、继承Thread类，重写该类的run()方法。

```
  class MyThread extends Thread{
    private int i = 0;
    @override
    public void run(){
      for(i = 0; i < 100; i++){
        System.out.println(Thread.currentThread().getName()+" "+i);
      }
    }
  }
```

```
  public class ThreadTest{
    for(int i = 0; i < 100; i++){
      System.out.println(Thread.currentThread().getName()+" "+ i);
      if(i == 30){
        //创建一个新的线程 myThread1 此线程进入新建状态
        Thread myThread1 = new MyThread
        //创建一个新的线程 myThread2 此线程进入新建状态
        Thread myThread2 = new MyThread();
        //调用start()方法使得线程myThread1进入就绪状态
        myThread1.start();
        //调用start()方法使得线程myThread2进入就绪状态
        myThread2.start();
      }
    }
  }
```

- - 2、实现Runnable接口，并重写该接口的run()方法同样是线程执行体，创建Runnable实现类的实例，并以此实例作为Thread类的target来创建Thread对象，该Thread对象才是真正的线程对象。

```
  class MyRunnable implements Runnable{
    private int i = 0;
    @override
    public void run(){
      for(i = 0; i < 100; i++){
        System.out.println(Thread.currentThread().getName() +　“　”　＋ i）
      }
    }
  }
```
```
  public class ThreadTest{
    public static void main(String[] args){
      System.out.println(Thread.currentThread().getName()+ " " + i);
      if(i == 30){
        //创建一个Runnable实现类的对象
        Runnable myRunnable = new Runnable();
        //将myRunnable作为Thread target创建新的线程
        Thread thread1 = new Thread(myRunnable);
        Thread thread2 = new
        Thread(myRunnable);
        //调用start()方法使得线程进入就绪状态
        thread1.start();
        thread2.start();
      }
    }
  }
```

- - 3、使用Callable和Future接口创建线程。具体是创建Callable接口的实现类，并实现call()方法。并使用FutureTask类中来包装Callable实现类的对象，且以此FutureTask对象作为Thread对象的target来创建线程。

```
  public class ThreadTest{
    public static void main(String[] args){
      //创建MyCallable对象
      Callable<Integer> myCallable = new MyCallable();
      //使用FutureTask来包装MyCallable对象
      FutureTask<Integer> ft = new FutureTask<Integer>(myCallable);
      for(int i = 0; i < 100; i++){
        System.out.println(Thread.currentThread.getName() + " "+ i);
        if(i == 30){
          //FutureTask对象作为Thread对象的target创建新的线程
          Thread thread = new Thread(ft);
          //线程进入到就绪状态
          thread.start();
        }
      }
      System.out.println("主线程for循环执行完毕..");
      try {
        //取得新创建的新线程中的call()方法返回的结果
        int sum = ft.get();
        System.out.println("sum = " + sum);
      } catch (IntegetuptedException e) {
        e.printStackTrace();
      } catch (ExecutionException e) {
        e.printStackTrace();
      }
    }
  }
```
```
  class MyCallable implements Callable<Integer>{
    private int i = 0;
    //与run()方法不同的是，call()方法具有返回值
    @Override
    public Integer call(){
      int sum = 0;
      for(; i < 100; i++){
        System.out.println(Thread.currentThread().getName() + " " + i);
        sum += i;
      }
      return sum;
    }

  }
```
* ### 三：Java多线程的就绪、运行和死亡状态

* - 就绪状态转换为运行状态：当此线程得到处理器资源;

* - 运行状态转换为就绪状态：当此线程主动调用yield()方法或在运行过程中失去处理器资源。

- - 运行状态转换为死亡状态：当此线程执行体执行完毕或发生了异常。


- - **<font color="red">注意：</font>当调用线程的yield()方法时，线程从运行状态转换为就绪状态，但接下来CPU调度就绪状态中的哪个线程具有一定的随机性，因此，可能会出现A线程调用了yield()方法后，接下来CPU仍然调度了A线程的情况。**

- - 由于实际的业务需要，常常会遇到需要在特定时机终止某一线程的运行，使其进入到死亡状态。目前最通用的做法是设置一boolean型的变量，当条件满足时，使线程执行体快速执行完毕。如：


```
public class ThreadTest {
    public static void main(String[] args) {
        MyRunnable myRunnable = new MyRunnable();
        Thread thread = new Thread(myRunnable);
        for (int i = 0; i < 100; i++) {
            System.out.println(Thread.currentThread().getName() + " " + i);
            if (i == 30) {
                thread.start();
            }
            if(i == 40){
                myRunnable.stopThread();
            }
        }
    }
}
class MyRunnable implements Runnable {

    private boolean stop;

    @Override
    public void run() {
        for (int i = 0; i < 100 && !stop; i++) {
            System.out.println(Thread.currentThread().getName() + " " + i);
        }
    }

    public void stopThread() {
        this.stop = true;
    }

}
```

* ### 四：Java多线程的阻塞状态与线程控制

* 1、join()
*  join——让一个线程等待另一个线程完成才继续执行。如A线程线程执行体中调用B线程的join()方法，则A线程被阻塞，直到B线程执行完为止，A才能得以继续执行。

```
  public class ThreadTest{
    public static void main(String[] args){
      MyRunnable myRunnable = new MyRunnable();
      Thread thread = new Thread(myRunnable);
      for(int i = 0; i < 100; i++){
        System.out.println(Thread.currentThread().getName() + " " + i);
        if(i == 30){
          thread.start();
          try {
            //main线程需要等待thread线程执行完后才能继续执行
            thread.join();
          } catch (InterruptedException e) {
            e.printStackTrace();
          }
        }
      }
    }
  }

  class MyRunnable implements Runnable{
    @Override
    public void main run(){
      for(int i = 0 ;i < 100; i++){
        System.out.println(Thread.currentThread().getName() + " " + i);
      }
    }
  }
```

* 2、sleep()
* sleep——让当前的正在执行的线程暂停指定的时间，并进入阻塞状态。在其睡眠的时间段内，该线程由于不是处于就绪状态，因此不会得到执行的机会。即使此时系统中没有任何其他可执行的线程，处于sleep()中的线程也不会执行。因此sleep()方法常用来暂停线程执行。

```
public class ThreadSleep {
public static void main(String[] args) {
  MyRunnable myRunnable = new MyRunnable();
  Thread thread = new Thread(myRunnable);
  for(int i = 0; i < 100; i++){
    System.out.println(Thread.currentThread().getName()+ " " + i);
    if(i == 30){
      thread.start();
      try {
        //使得thread能够马上执行
        Thread.sleep(1);
      } catch (InterruptedException e) {
        e.printStackTrace();
      }
    }
  }
}
}
class MyRunnable implements Runnable{
@Override
public void run() {
  for(int i = 0; i < 100; i++){
    System.out.println(Thread.currentThread().getName()+" " + i);
  }
}

}
```

<h1 id="threadProblems">二：经典多线程问题</h1>
<h1 id="gui">三：GUI图形用户界面</h1>
<h1 id="internet">四：网络编程</h1>
<h1 id="reflection">五：反射</h1>
<h1 id="complexDesign">六：复杂设计模式</h1>
