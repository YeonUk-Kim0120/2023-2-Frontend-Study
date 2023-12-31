----------------------------------------------------------------------------------------------------------------------------------------------
#클로저(Closure)
-클로저는 내부 함수에서 외부 함수의 범위에 대한 접근을 제공한다

예시)
function init() {
  var name = "김연욱";

  function Name() {   //[클로저]
    console.log(name); 
  }
  Name();
}
init();


설명:
내부 함수인 Name()에서 외부 함수인 init()의 변수에 접근할 수 있다.
즉 Name()은 부모 함수인 init()에서 선언된 변수 name에 접근할 수 있기때문에 실행결과는 [김연욱]이 된다.


----------------------------------------------------------------------------------------------------------------------------------------------
#객체(Object)
-객체는 변수이다. 하지만, 데이터와 함수의 집합이라고 할 수 있다.

예시)

var YEONUK = {
  name: "YEONUK_KIM",
  school: "홍익대",
  address: "시흥시"
};

var Name = YEONUK.name;
var School = YEONUK.school;
var address = YEONUK.address;

console.log(Name); 
console.log(School);
console.log(address);

실행결과:
YEONUK_KIM
홍익대
시흥시


설명:
YEONUK 이라는 변수를 생성한 후 name, school, address라는 데이터를 넣어준 후 다시 접근하였다.

----------------------------------------------------------------------------------------------------------------------------------------------

#프로퍼티(Property)
- 프로퍼티는 속성이라는 뜻이고, 객체 내부의 속성을 의미한다.

설명:

var YEONUK = {
  name: "YEONUK_KIM",
  school: "홍익대",
  address: "시흥시"
};

위 객체를 보면 YEONUK이라는 객체 안에 name, school, address라는 key가 있는데, 이를 프로퍼티라고 한다.

----------------------------------------------------------------------------------------------------------------------------------------------
#네임스페이스(Namespace)
-네임스페이스는 단어 뜻 그대로 이름이 존재하는 공간이다. 
-프로그램 개발을 하다보면 전역 범위에 이름이 같은 변수나 함수 등을 정의하는 경우가 발생한다. 이러한 경우에 충돌을 방지하기 위해 이름이 존재하는 공간을 정의한다.

예시)
var NS = {};
var value = 1;
 
function Hi() {
    console.log('Hi');
}
 
NS.value = 2;
NS.Hi = function () {
    console.log('NS_Hi');
}
 
window.onload = function () {
    console.log(value);
    console.log(NS.value);
    Hi();
    NS.Hi();
}

실행결과:
1
2
Hi
NS_Hi

설명: 35번 줄에서 NS라는 네임스페이스를 갖는 value라는 변수를 선언, 2라는 값을 할당. 
      36번 줄에서 Hi()라는 함수도 NS라는 네임스페이스를 갖도록 선언하였다.
      그래서 value 값이랑 NS.value 값이 다르고, Hi()랑 NS_Hi()도 다르다.\

----------------------------------------------------------------------------------------------------------------------------------------------
