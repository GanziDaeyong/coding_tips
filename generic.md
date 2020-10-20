Generic
======================================

Q) 다른 타입을 하나의 array에 넣을 수 있나?

A) 그렇다. array의 인풋 타입을 Object로 지정해주면 된다.
자바의 모든 클래스는 Object를 상속하기에 Integer, Double, String 같은 wrapper 또한 Object를 상속하기 때문이다.

<pre><code>
Integer intNum = 40;
Double douNum = 40.40;
String str = "potato";
		
if (intNum instanceof Object && douNum instanceof Object && str instanceof Object) System.out.println("o");
else System.out.println("x");
</code></pre>

위와 같이 instance of 를 통해 확인해볼 수 있다. 


<pre><code>
ArrayList<Object> anyType = new ArrayList<Object>();
				
anyType.add(1);
anyType.add(2);
anyType.add("potato");

int rst = (Integer) anyType.get(0) + (Integer) anyType.get(1);
		
System.out.println(rst);
</code></pre>


해당 리스트의 요소간 연산을 진행하려면 앞에 명시적으로 타입을 입력해주어야 한다.
아직까지 자바는 얘가 Object 객체라는 것만 알 뿐, 타입에 대한 단서가 없기 때문이다.