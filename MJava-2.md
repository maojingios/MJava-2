JavaBasic-2

## 继承

1、继承是Java面向对象编程的一块基石。

2、规范

public class 子类名 extends 父类名{

}

3、特征：

* 子类拥有父类private属性和方法；
* 子类可以拥有自己的属性和方法，即子类可以对父类进行拓展；
* 子类可以用自己的方式实现父类的方法；
* Java的继承是单继承，但可多重继承。单继承就是一个子类只能继承一个父类，多重继承就如A继承B，B继承C这种形式；
* 提高了代码之间的耦合度。


4、关键字

* extends：只能继承一个类；
* implements：此关键字可变相让Java具有多继承特性，可同时继承多个接口。

		public interface A {
		    public void eat();
		    public void sleep();
		}
		 
		public interface B {
		    public void show();
		}
		 
		public class C implements A,B {
		}

5、super和this

* super关键字可实现对父类成员的访问，用来引用当前对象的父类。
* this指向自己的引用。

6、final

final关键字修饰的类不能被继承，为最终类。或修饰方法，该方法不能被子类重写。

7、构造器

子类不能继承父类的构造器，但父类的构造器带参数的，一定要在子类中显式使用super关键字调用父类构造器，并传入适当的参数。若父类的构造器不带参数，在子类中用super调父类构造器不是必须的。


## Override重写和Overload重载

1、重写即子类对父类允许访问的方法的实现过程进行重新定义，但形参和返回值不能变；

2、子类中要调用父类被重写的方法，需使用super关键字：

	class Animal{
	   public void move(){
	      System.out.println("动物可以移动");
	   }
	}
	 
	class Dog extends Animal{
	   public void move(){
	      super.move(); // 应用super类的方法
	      System.out.println("狗可以跑和走");
	   }
	}
	 
	public class TestDog{
	   public static void main(String args[]){
	 
	      Animal b = new Dog(); // Dog 对象
	      b.move(); //执行 Dog类的方法
	 
	   }
	}

3、重载

在同一个类中，方法名相同，参数不同，返回值可以不同，最常用的地方就是重载构造器：
	
	public class Overloading {
	    public int test(){
	        System.out.println("test1");
	        return 1;
	    }
	 
	    public void test(int a){
	        System.out.println("test2");
	    }   
	 
	    //以下两个参数类型顺序不同
	    public String test(int a,String s){
	        System.out.println("test3");
	        return "returntest3";
	    }   
	 
	    public String test(String s,int a){
	        System.out.println("test4");
	        return "returntest4";
	    }   
	 
	    public static void main(String[] args){
	        Overloading o = new Overloading();
	        System.out.println(o.test());
	        o.test(1);
	        System.out.println(o.test(1,"test3"));
	        System.out.println(o.test("test4",1));
	    }
	}

4、总结：
方法的重写和重载是Java多态性的不同表现，重写是父类与子类之间多态性的表现，重载则是java多态性的具体表现。

重载就是同样的一个方法能够根据输入数据的不同，做出不同的处理。
重写就是当子类继承自父类的相同方法，输入数据一样，但要做出有别于父类的响应时，你就要覆盖父类方法。








