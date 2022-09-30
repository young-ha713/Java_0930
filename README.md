# Java_0930  
  
  
  
  
  
  
포인트  
- 자료형, 변수선언  
-메서드 정의와 활용  
- 클래스와 객체  
-객체를 누가 만들것이며 이런 객체를 어떻게 공유할것인가?  
-알고리즘  
  
  
  
----------------------------  
  
  
클래스란? = 객체를 정의한 것 (내가 개발하려고 하는 세상을 정의해 놓은 것)  
  
인터페이스 = 어떤 문장에 이 단어를 쓰느냐에 따라 그 의미가 다양하게 해석  
지금까지 개발한 사용자와 프로그램간의 인터페이스는 cli (콘솔을 통해)  
업그레이드 cli -> gui(클릭해서 들어가는것)  
  
클래스와 객체, 변수,메서드를 이해해야 위를 이해 할 수 있다.  
  
![image](https://user-images.githubusercontent.com/80766275/193166698-6b1c06bb-bad8-450c-8d32-6d11063fd199.png)
  
gui 사용  
  
-------------------------------------------
상속을 이해하기 위한 키워드  
  
슈퍼클래스, 서브클래스  
  
서브 클래스는 슈퍼클래스의 기능을 확장한다.  
  
비슷한 의미로 서브클래스는 슈퍼클래스의 자원을 사용가능하다.  
  
클래스의 계층화를 표현 할 수 있다. 주 목적은 아님  
  
계층화 팁  
1. 프로그램에서 표현하고자 하는 클래스를 먼저 생각  
클래스를 구성하는 기준을 구체적이면서 실제 표현 가능한것으로 판별  
  
**실제 사용 할때 내가 계층화 할것인가? 새로운 계층을 설계 할 것인가 관점    
계층화된 어떤 기능을 사용할것인가? 관점(예를 들면 만들어진것. 자바에 있는 캔버스등)**  
  
  
  
  
![image](https://user-images.githubusercontent.com/80766275/193170444-1df16a01-c7ab-4fb2-a1bf-ecb885b451f6.png)

  
  
상속은 클래스의 계층화를 위해 사용한다 = 좋지 못한 정리임 ..상속!=클래스 계층화  
상속으로 클래스를 계층화 시킬 수 있다 .(그저 실제 많이 사용하는 이유임)
  
가족 구성원을 클래스로 포현한다  
부모는 하나 자식은 자식1 자식2 자식3  ..이 있을 수 있다. :클래스를 3개 만들 필요가 없음  
왜냐면 자식은 공통된 특성과 메서드를 갖고 저장된 값만 다르면 된다.  
  
컨셉  
부모는 하나 자식은 남자와 여자로 세분화 .남자클래스와 여자 클래스를 따로 만든다  
  
  
부모 클래스  
```
package extends_ex1;

public class Parent {
	String name;
	int age;
	String regNumber;
	int kg;
	int cm; //상속받는 애들도 이 변수 가짐  
    
    
  public void prt() {
		System.out.println(name);
		System.out.println(age);
	} //메서드도 상속 가능하다   
  
}
```  
  
여자자식 클래스  
```
package extends_ex1;

public class Child_W extends Parent{
	
	int money =0; //부모의 자원 플러스 하위클래스의 자원까지 사용 가능
	
	public void eatting() {
		System.out.println("다이어트 음식");
	}
	
	
	
	
	
}
```  
  
남자자식 클래스  
```
package extends_ex1;

public class Child_M extends Parent{
	 
	
	public void eatting() {
		System.out.println("고기고기");
	}
}
```  
  
메인 클래스  
```
package extends_ex1;

import java.util.ArrayList;

public class Main {

	public static void main(String[] args) {
		//남자 2 여자 2 만들기  
		ArrayList<Child_M>cmList=new ArrayList<>();
		ArrayList<Child_W>cwList=new ArrayList<>();
		
		Child_M cm1 = new Child_M();
		Child_M cm2 = new Child_M();
		cm1.name ="kim";
		cm1.prt(); //상속 받은 메서드  
    
    
    
		Child_W cw1 = new Child_W();
		Child_W cw2 = new Child_W();
	


	}

}
```  
  
  

  
  
  
  
  
  

  
  
  
