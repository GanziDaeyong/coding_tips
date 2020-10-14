Java
==========


---------
super
---------

* super는 부모 생성자를 불러올 때 사용한다.

* super()는 기본 생성자를 불러온다.

* 당연히 super() 괄호 안에 인자를 채워넣어주면, 사용자 정의 생성자를 호출하는 효과가 있다.

* 그래서 배울때도 부모 클래스의 기본 생성자를 명시 + super() 을 사용하는 방법 / 부모 클래스의 정의 생성자를 + super(인자) 를 사용하는 방법 순으로 배운다.

* 인스턴스 변수를 건들지 않을 것이라면 굳이 쓸 필요 없다. 상속만으로 해결 가능한 일이니.

<pre><code>

class Food{
	int bal;
	int price;
	String sellerName;
	Food(int price, String sellerName) {
		this.price = price;
		this.sellerName = sellerName;
	}
}

class Potato extends Food {
	Potato(int bal, int price, String sellerName) {
		super(price, sellerName);
		this.bal = bal;
	}
}

</code></pre>

------------
upcasting
------------

* 뜻) 상속 후 객체 생성 시, 부모의 클래스 모형으로 자식의 객체를 생성하는 것이다.
explicit type : parent / actual content : children.

* 이유) 상속받는 클래스들이 많아질수록, 클래스들로 각각 선언해주면 통일성과 가독성 모두 떨어진다. 
또한, 부모 클래스의 메서드 외에 각각의 클래스들이 갖는 메서드들을 쓰기 시작하면 부모 클래스가 하나의 큰 추상 클래스 역할을 하지 못한다. (실제로 추상클래스는 아니지만)
따라서 이 경우 업캐스팅하면, 부모 클래스의 꼴에 맞추면서, 내용적으로는 각자 오버라이딩 한 메서드를 깔끔히 구현할 수 있다.
물론 업캐스팅 해버리면 자신의 고유한 메서드는 실행하지 못한다. 부모 꼴에 맞춤을 전제하기 때문이다.

* 개인적으로는 다형성을 가장 잘 보여주는 특징이라 생각한다.

* 인스턴스 변수를 자식 클래스에서 새로이 정의해줬다면 당연히 새로 정의된 변수를 따라가고, 아니라면 상속에 의해 부모의 것을 그대로 받게 된다.
