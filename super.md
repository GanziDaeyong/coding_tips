Java
==========



super
---------

* super는 부모 생성자를 불러올 때 사용한다.

* super()는 기본 생성자를 불러온다.

* 당연히 super() 괄호 안에 인자를 채워넣어주면, 사용자 정의 생성자를 호출하는 효과가 있다.

* 그래서 배울때도 부모 클래스의 기본 생성자를 명시 + super() 을 사용하는 방법 / 부모 클래스의 정의 생성자를 + super(인자) 를 사용하는 방법 순으로 배운다.

* 인스턴스 변수를 건들지 않을 것이라면 굳이 쓸 필요 없다. 상속만으로 해결 가능한 일이니.

<pre><code>
{

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


}
</code></pre>