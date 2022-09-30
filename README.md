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
(자원을 구분하는 키워드는 this,super)  
클래스의 계층화를 표현 할 수 있다. 주 목적은 아님  
상속은 클래스의 계층화를 위해 사용한다 = 좋지 못한 정리임 ..상속!=클래스 계층화    
상속으로 클래스를 계층화 시킬 수 있다 .(그저 실제 많이 사용하는 이유임)  
  
키워드 : this_자신의 객체의 주소  
	super_슈퍼클래스 객체의 주소  
![image](https://user-images.githubusercontent.com/80766275/193181474-833330aa-9206-493c-aebc-2399b9d3077f.png)

  
  
  
  
계층화 팁  
1. 프로그램에서 표현하고자 하는 클래스를 먼저 생각  
클래스를 구성하는 기준을 구체적이면서 실제 표현 가능한것으로 판별  
저장:전역변수  기능 :메서드로 정의하고 구현  
  
  
삼성핸드폰 클래스 구성 : 모델명 ,수량, 가격,기능,전화걸기,전화받기  
아이폰 // :모델명 ,수량, 가격,기능,전화걸기,전화받기,차단번호 관리  
  
  
  
  
**실제 사용 할때 내가 계층화 할것인가? 새로운 계층을 설계 할 것인가 관점(내가 클래스 만들어 상속)    
계층화된 어떤 기능을 사용할것인가? 관점(예를 들면 만들어진것. 자바에 있는 캔버스등)**  
  
  
  
  
![image](https://user-images.githubusercontent.com/80766275/193170444-1df16a01-c7ab-4fb2-a1bf-ecb885b451f6.png)

  
  

  
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
  
  
  
-----------------------
  
  
  
  
### 추상 메서드와 추상 클래스  
  
  
추상메서드 - 선언만 하고 구현을 하지 않은 메서드ex)public abstract void call();뒤{}선언 안해준다    
추상클래스 - 선언메서드가(추상메서드) 한 개 이상이면 추상 클래스로 선언 해야 한다  
추상 클래스는 객체로 만들 수 없다(메서드가 정확하게 기능이 구현안된 상태이니 당연히 객체가 되면 안된다. 객체는 실제 사용하려는 목적이 있기 때문이다.)  
  
팁 : 공통된 전역변수와 메서드로 슈퍼클래스의 메서드를 정의하고 구현했는데  
서브 클레스가 공통으로 메서드의 기능이 필요하지만(메서드의 이름이 필요하지만) 실제 동작 방법이 다를 수 있다  
이때는 슈퍼 클레스가 구현하지 않고 서브클래스가 구현하는것이 더 적당하다..  
  
>> 도대체 기능을 이해하려면 뭘 이해해야 하나?? 답은 메서드명  
  
  
메서드명의 통일은 매우매우 중요하다.  
예를 들어 삼송핸퐁에 전화거는 기능이 callsm으로 정의되어 있고  
아이폰에서는 calltoyou라고 정의되어있다면  
이 두개를 컨트롤 하는 개발자는 각각 클래스별 서로 다른 기능으로 정의된 이름을 다 알아야 하니  
헷갈릴 수 있고 실수 할 수 있다.그래서 둘 다 call로 바꾸는게 좋다...  
  
  
  
  
  
정리  
  
슈퍼 클래스는 추상 메서드를 정의 할 수 있고  
이를 상속받은 서브 클래스에서는 추상메서드를 반드시 재정의(오버라이드)해야 한다  
슈퍼클래스의 추상 메서드가 아닌것도 재정의가 가능하지만 차이점은 필수이냐 아니냐이다..  
  
  
  
메서드 오버라이딩 정의 : 메서드를 재정의 하는것..!  
예를 들면 상속받은 서브 클래스가 슈퍼클래스의 메서드를 재구현 할 수 있다.  
이것을 메서드 오버라이딩이라고 한다. 추상메서드는 반드시 오버라이딩을 구현해야 하지만 일반 메서드는 선택입니다..!  
  
상속에서 사용하는 기능중 하나는 아니다..!!!!  
  
  
  
  
 ----------------------------------------  
   
   
   
 ### 다형성 - 객체 지향 언어의 특징  
 다형성은 하나의 변수로 서로 다른 자료형의 값을 가질 수 있다 ..
  
  
***다형성은 상속에서 사용하는것이다 (오답)  
***상속으로 계층화 된 구조에서 다형성을 이용하면 코드가 더 단순해지고 유연해진다 (정답가능)  
  
  
  
  
```
import java.util.ArrayList;

public class Pmain {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		MobP hp;
		//자료형 변수 : hp라는 변수를 선언한다.이 변수의 값은 몹피의 객체 주소  
		
		//다형성코드
		ArrayList<MobP> ssList = new ArrayList<>();
		MobP hp1 = new MobS();
		hp1.name = "k9";
		ssList.add(hp1);
		hp1 = new MobI();
		hp1.name ="i12";
		ssList.add(hp1);
		
		for(MobP hs : ssList) {
			System.out.println(hs.name);
			hs.callto();
		}
		
		//일반코드
//		ArrayList<MobS> sList = new ArrayList<>();
//		ArrayList<MobI> iList = new ArrayList<>();
//
//		MobI i1 = new MobI();
//		MobS s1 = new MobS();
//		
//		i1.name ="아이폰 13 미니";
//		i1.callto();
//		s1.callto();
	}

}
```  
  
  
  
  
  
  
  
  
  
  

  
  
  
