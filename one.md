# javascript_definitive_guide
The JavaScript Definitive Guide

## 자바스크립트 소개
- 객체지향 프로그래밍을 지원하는 인터프리터 방식의 프로그램이다.
- 변수의 타입을 명시할 필요가 없는 타입 제약이 약한 언어이다.
- 범용 프로그램 언어이므로 특별한 환경에서만 사용되지 않는다.
- 리터럴(literal)은 프로그램에 직접 나타나는 데이터 값이다.
- 식별자는 이름이다. 변수나 함수에 이름을 붙이거나 루프(loop) 문에 레이블을 붙이는데 사용된다.
---
## 데이터 타입과 값
- 프로그램 언어로 표현할 수 있고 조작할 수 있는 값의 종류를 데이터 타입이라고 한다.
- 세가지 기본 데이터 타으로는 숫자(number), 문자열(string), 진리 값(boolean)이 있다.
- 또한 두 개의 단순 데이터 타입인 null과 undefined를 정의한다.
- 이외에도 객체(object)라는 복합 데이터 타입을 지원한다.
- 객체는 이름 붙은 값들의 순서 없는 값들을 나타낸다.
- 번호가 붙은 순서 있는 값들의 모임을 배열(array)이라 한다.
### 숫자 (number)
- 정수 값과 실수 값을 구별하지 않고 모든 숫자는 실수로 표현한다.
- 산술연산자로는 +,-,*,/가 있다.
- 기본 산술연산자 이외에도 많은 수의 수리 함수를 사용해 복잡한 수리 연산을 수행할 수 있다.
- 0을 0으로 나누는 등 정의되지 않은 결과를 산출하거나 에러를 발생시킬 경우 특수한 값 NaN을 출력한다.
- NaN은 어떤 숫자와 비교해도 동일하지 않으며 심지어 NaN과 NaN을 비교해도 동일하지 않다.
### 문자열 (string)
- 문자열 리터럴은 한 줄을 넘지 말아야 하며, 줄바꿈(new line)을 포함시키고 싶다면 \n을 사용한다.
- 숫자를 문자열로 변홚나려면 빈 값을 더하거나(1 + ""), 명시적으로 변환하려면 String() 함수를 사용한다.
- 문자열 "120"을 숫자로 명시적으로 변환하려면 Number() 생성자를 함수처럼 호출한다.
### 불리언 값 (boolean)
- 오직 두개의 값만 가질 수 있다. (true, false)
- 일반적으로 비교의 결과로 생성된다. (제어 구조 내에서 사용)
- 명시적 타입변환은 Boolean() 함수를 사용할 수 있다.
### 함수 (function)
- 전달인자(agument), 매개변수(parameter)
- 함수가 어떤 객체의 프로퍼티로 할당되면 해당 객체의 메서드(method)라고 부른다.
- 일반적인 함수 정의 방법은 아래와 같다.
<pre><code>function foo(x){
    return x+x;
}</code></pre>
- 또한 아래와 같이 함수 리터럴 문법도 제공한다.
<pre><code>var foo = function(x){
    return x+x;
}</code></pre>
- 위와 같이 함수를 리터럴 형태로 포함시킬 수 있게 한 함수를 람다함수(lambda function)라 부른다.
### 객체 (object)
- 객체는 이름 붙은 값들의 모음이다. 보통 이 이름 붙은 값들을 객체의 프로퍼티(property)라고 부른다.
- 객체 프로퍼티를 참조하려면 아래와 같이 작성한다. (image라는 객체의 width프로퍼티를 참조)
<pre><code>var image = {
    "width":300
}
image.width; //300</code></pre>
- 객체의 프로퍼티는 배열, 함수, 객체 등 어떠한 타입의 값도 담을 수 있다.
- boolean 문에서 사용되면 'true'로 변환된다.
### 배열 (Array)
- 배열도 객체처럼 데이터 값들의 모음이지만, 데이터 값의 이름 대신 번호, 즉 인덱스(index)가 있다.
- 배열은 다른 배열이나 객체, 또는 함수를 포함한 어떤 데이터 타입의 데이터도 담을 수 있다.
- boolean 문에서 사용되면 'true'로 변환된다.
### null
- 아무런 값도 나타내지 않는 특수한 값이다.
- null은 보통 객체 타입의 특수한 값, 즉 어떠한 객체도 나타내지 않는 값으로 취급된다.
- 다른 모든 값들과 구분되는 고유한 값이다.
- boolean 문에서 사용되면 'false'로 변환된다.
### undefined
- null과는 구분되는 특수한 값이다.
- undefined는 선언이 되었지만 값이 할당되지 않은 변수, 존재하지 않는 객체 프로퍼티에 접근할 경우 반환되는 값이다.
- null과 undefined값은 서로 구별되는 값이지만 동등 연산자(==)는 둘을 같은 것으로 본다. **(undefined == null // true)**
- boolean 문에서 사용되면 'false'로, 숫자 문맥에서는 NaN, 문자열 문맥에서는 "undefined"로 변환된다.
### 값에 의한 vs 참조에 의한
- 데이터 타입 조작 요약 표

| 타입 | 복사  | 전달  | 비교  |
| ---- | ---- | ---- | ---- |
| 숫자  |  값  |  값  |  값  |
| 불리언 |  값  |  값  |  값  |
| 문자열 | 불변 | 불변  |  값  |
| 문자열 | 참조 | 참조 | 참조 |

---

## 변수
### 변수 타입
- 다른 프로그래밍 언어와 달리 타입이 고정되어 있지 않다.
### 가비지 컬렉션
- 자바스크립트 인터프리터는 어떤 객체가 어느 시점부터 프로그램에서 더이상 접근할 수 없다고 판명되면 해당 객체가 더이상 필요 없다 판단하여 할당했던 메모리를 해제하여 재활용 될 수 있게 한다.

---

## 표현식과 연산자
### 조건부 연산자 (?:)
- 유일한 3항 연산자 (피연산자가 3개)이다.
<pre><code>x > 0 ? x*y : x+y</code></pre>
- 첫 번째 피 연산자는 불리언 값 또는 불리언 값으로 변환될 수 있어야 한다.
- 첫번째 피 연산자의 값이 true이면 두 번쨰 피 연산자의 값이 된다. false이면 세 번째 피연산자의 값이 된다.
### typeof 연산자
- 단일 피연산자 앞에 위치하는 단항 연산자로, 이 연산자의 값은 피연산자의 데이터 타입을 가리키는 문자열이다.
- null값에 대해서는 "object"를 반환한다.
### delete 연산자
- 단항 연산자이며 피연산자로 지정된 객체의 프로퍼티, 배열의 원소 또는 변수의 삭제를 시도한다. 성공적으로 삭제되었을 경우에는 true를, 실패하였을 때는 false를 반환한다.
- 사용자가 var문으로 정의한 변수는 삭제할 수 없다.
- 존재하지 않는 프로퍼티에 대해 delete를 호출할 경우 true가 반환된다.
### 배열과 객체 접근 연산자
- 배열원소에 접근은 대괄호([])를 사용하며, 객체의 원소에 접근은 마침표(.)를 사용한다.
<pre><code>arr[0] //arr배열의 첫번재 원소에 접근
obj.name //obj객체의 name식별자(property)에 접근</code></pre>
- []와 . 모두 연산자로 취급된다.

## 문장
### switch
- if문은 프로그램이 실행되는 흐름에 분기(branch)를 일으킨다.
- 여러개의 if문(else if)을 사용해서 다중 분기를 수행할 수 있지만, 모든 분기가 단 하나의 변수 값에 의해 결정될 때에는 낭비이다. 이때 switch문을 사용하면 효율적이다.
<pre><code>switch(표현식){
    문장
}</code></pre>
- switch문이 실행되면 "표현식"의 값을 계산하고 이에 매칭되는 case 레이블을 찾고, 올바른 레이블을 찾으면 해당 case 코드블록을 실행한다. 만약 매칭되는 레이블이 없다면 default 레이블의 코드블록을 실행하며, defalut; 레이블도 없으면 모든 코드블록을 skip한다.
<pre><code>switch(n){
    case 1 :
        // n이 1이면 실행
        break;
    case 2 :
        // n이 2면 실행
        break;
    default :
        //모든 case에 해당하지 않는 경우 실행
}</code></pre>
- break문은 코드 실행을 중지하고 switch문이나 루프의 끝으로 건너뛰는 역할을 한다.
- 함수 내에서 switch문을 사용할 때는 break대신 return을 사용할 수도 있다.
- case문에서는 동등 연산자(==)가 아닌 일치 연산자(===)가 사용된다.
### while
- 기본적인 반복문. 표현식을 평가 후 그 값이 true이면 실행된 후, 다시 표현식을 평가한다. 표현식이 false가 될때까지 반복된다. false가 되면 while문이 종료된다.
<pre><code>while(표현식){
    문장
}</code></pre>
### do/while
- while문과 많은 점에서 비슷하다. 차이점은 루프 표현식이 루프의 처음이 아니라 마지막이다. 때문에 한 번은 루프의 몸체가 실행된다.
<pre><code>do{
    문장
}while(표현식);</code></pre>
### for
<pre><code>for(초기화; 평가; 증가(감)){
    문장
}</code></pre>
### for/in
<pre><code>for(변수 in 객체){
    문장
}</code></pre>
### 레이블
- switch문에서 쓰이는 case와 default; 레이블은 특별한 레이블 문이다.
<pre><code>parser:
    while(token != null){
    //문장
}</code></pre>
- 어떤 문장에 레이블을 붙이면 다른 곳에서 그 문장을 참조할 수 있는 이름이 생기는 셈이다. 레이블은 어떤 문장에라도 붙일 수 있지만 흔히 while, do/while, for, for/in과 같은 루프에 붙인다.
### break
- break의 역할은 루프나 switch에서 빠져 나오게 하는 것으로 break키워드 뒤에 레이블 이름이 따라올 수 있다.
<pre><code>break;
break 레이블 이름;</code></pre>
### continue
- continue문은 break문과 유사하지만 루프를 빠져나오지 않고 새로운 시작을 하는점에서 차이가 있다.
<pre><code>continue;
continue 레이블 이름;</code></pre>
- continue문은 while, do/while, for, for/in 루프의 몸체 내부에서만 사용되어야 한다. 그 외 사용시 에러가 발생하며, continue문이 실행되면 루프의 현재 반복을 종료하고 다음 반복을 시작한다. 이때, 루프의 종류에 따라 다르게 실행된다.
- while 루프에서는 루프의 시작부분에 지정된 '표현식' 다시 테스트한다.
- do/while 루프에서는 루프의 끝 부분까지 건너뛴 뒤 루프 조건을 테스트한다.
- for 루프에서는 '증가' 표현식을 평가한 후 '테스트' 표현식을 테스트 하여 다음 반복을 수행할지 여부를 판단한다.
- for/in 루프에서는 다음 차례의 프로퍼티 이름을 루프 시작에서 지정된 변수에 할당 후 루프를 다시 시작한다.
- **while 루프는 루프 조건으로 곧장 귀환하는 반면, for 루프는 일단 '증가' 표현식을 평가한 후 루프 조건으로 귀환한다.**
<pre><code>for(var i = 0; i < data.length; i++){
    //오류를 만나면 반복문을 빠져나와 증가 > 테스트를 거친다.
    if(data[i] == null){
        continue;
    }
    total += data[i];
}</code></pre>
###var
- var문은 명시적으로 하나 또는 그 이상의 변수를 선언하는데 사용된다.
- var문에 의해 생성되는 프로퍼티는 delete 연산자로 삭제될 수 없다.
###function
<pre><code>function 함수명(전달인자1, 전달인자2..){
    문장
}</code></pre>
- 함수정의는 문장이 아닌 구조를 나타낼 뿐이다. 문장은 실행 시간에 실행되는 반면, 함수는 코드가 실행되기 이전의 파싱(parsing) 또는 컴파일 단계에서 정의된다.
###return
- 함수 호출 표현식의 값, 함수에서 반환되는 값을 지정하는데 쓰인다.
<pre><code>return 표현식;
function square(x){ return x*x; }</code></pre>
- 또한, 값을 반환하지 않고 단지 함수의 실행을 종료할 목적으로 "표현식" 없이 return문만 사용할 수 있다.
<pre><code>function display_obj(obj){
    //전달인자가 유효하지 않으면 건너뛴다.
    if(obj == null){
        return;
    }
    문장..
}</code></pre>
- "표현식"이 없는 return문을 실행하거나 함수가 반환되면, 해당 함수 호출 표현식의 값은 undefined가 된다.
###throw
- "예외"란 무언가 예외적인 상황이나 에러가 발생했음을 가리키는 신호이다. throw는 예외상황을 알린다는 것을, catch는 그것을 처리한다는 것을 의미한다.
<pre><code>function factorial(x){
    // 입력 전달 인자가 유효하지 않으면 예외를 발생시킨다.
    if (x < 0) {
        throw new Error('x must not be negative');
    }
    // 유효하면 값을 계산, 반환한다.
    문장
    return f;
}</code></pre>
- 예외가 발생하면 프로그램 실행을 즉시 중단하고 가장 가까운 예외 처리기로 넘어간다. 해당 코드블록이 catch 절과 연결되어 있지 않으면 바로 상위 코드 블록이 catch절과 연결되어 있는지 반복한다. 예외 처리기를 찾을때까지 이 과정을 반복하고 아무런 예외 처리기도 찾을 수 없으면 이 예외는 에러로 취급, 사용자에게 보고된다.
###try/catch/finally
- 자바스크립트의 예외 처리 기법
- try 절은 예외가 발생할지도 모르는 코드 블록을 정의하는 역할을 한다.
- try 블록 다음 이어지는 catch절은 try 블록 내부에서 예외가 발생할 경우 호출되는 문장 블록이다.
- catch 절 다음 이어지는 finally 블록에는 try 블록과 무관하게 항상 실행이 보장되어야 할 뒷정리용 코드도 포함된다.
<pre><code>try{
    //문제가 없을 시 블록의 시작부터 끝까지 수행된다.
    //상황에 따라 예외가 발생할 수 있다. (throw 문에 의한 직접 호출 또는 예외를 발생시키는 메서드의 호출에 의해 발생)
}catch(e){
    //catch 블록은 오직 try 블록에서 예외가 발생한 경우에만 실행
    //이 문장에선 지역 변수 e를 사용하여 Error 객체 또는 다른 값을 참조할 수 있다.
    //예외를 처리할 수도, 무시할 수도, throw를 사용하여 다른 예외를 발생시킬 수도 있다.
}finally{
    //try블록이 종료되면 무조건 실행된다.
    //try블록이 종료되는 상황
    //1.정상적으로 블록의 끝에 도달했을 때
    //2.break, continue 또는 return 문에 의해서
    //3.예외가 발생했지만 앞의 catch 절에서 처리 했을 때
    //4.예외가 발생했고 그것이 잡히지 않은 채 퍼져나갈 때
}</code></pre>
<pre><code>try{
    //사용자에게 입력 요청
    var n = prompt('enter');
    alert(n);
}catch(e){
    //만일 사용자 입력이 유효하지 않으면 catch블록 실행
    //지역변수 e를 참조하여 어떤 에러인지 알린다.
    alert(e);
}</code></pre>
###with
- with문은 유효범위체인을 임시로 변경하려 할 때 쓰인다.
<pre><code>with (객체) {
    문장
}</code></pre>
<pre><code>//html폼에서 어떤 엘리먼트에 접근하려면 아래와 같이 접근한다.
frames[1].document.forms[0].address.value;
//위의 폼을 여러번 접근해야 한다면 with문을 사용하여 유효 범위 체인에 위 폼을 추가하는 것이 편하다.
with(frames[1].document.forms[0]){
    //여기선 폼 엘리먼트에 직접 접근이 가능하다.
    name.value ="";
    address.value ="";
    email.value ="";
}</code></pre>
- 코드 최적화가 어렵고, with문 내부에서 함수 정의나 변수 초기화를 했다면 비직관적이고 예기치 않은 작동을 불러올 수 있기 때문에 **with문 사용은 지양**한다.

---

##객체와 배열
- 객체는 이름 붙은 값들의 집합, 배열은 숫자가 붙은 값들의 순서 있는 집합이다.
- 객체 프로퍼티 값에 접근하기 위해서는 마침표(.) 연산자를 사용한다.
<pre><code>//obj객체의 x프로퍼티를 변수 x에 담는다.
var x = obj.x;</code></pre>
### 객체 생성하기
<pre><code>var empty = {};
var point = {x:200, y:200};
var person = {
    "name" : "bk",
    "age" : 24,
    "hobby" : ["soccer", "baseball"]
}</code></pre>
### 객체 프로퍼티
#### 프로퍼티 존재 확인
- in 연산자를 사용하여 객체 프로퍼티의 존재 여부를 확인할 수 있다.
<pre><code>//객체 obj에 "x"프로퍼티가 있으면 alert()을 실행한다.
if("x" in obj){
    alert();
}</code></pre>
- 하지만 객체에 없는 프로퍼티에 접근하려 하면 undefined 값이 반환되기 때문에 in 연산자보다는 아래와 같이 표현할 수 있다.
<pre><code>if(obj.x !== undefined){
    alert();
}</code></pre>
#### 프로퍼티 삭제
- 객체의 프로퍼티를 삭제하기 위해서는 delete 연산자를 사용한다.
<pre><code>delete obj.x;</code></pre>
- 객체의 프로퍼티에 접근하기 위해서 마침표(.) 연산자를 사용하는데 [] 연산자를 사용해도 객체의 프로퍼티에 접근할 수 있다.
<pre><code>if(obj.x === obj["x"]) //true</code></pre>
- 마침표 연산자에서는 프로퍼티 이름을 식별자로 지정했지만, [] 연산자에서는 이름을 문자열로 표현했다는 점에서 자바스크립트의 타입 제약의 느슨함, 유연성이 드러난다.
### 공통적으로 나타나는 객체 프로퍼티와 메서드
#### constructor 프로퍼티
- 모든 객체는 객체를 초기화하는데 사용되는 생성자 함수인 constructor프로퍼티를 지니고 있다.
<pre><code>var d = new date();
d.constructor == Date;  //true</code></pre>
- 생성자 함수는 객체의 범주 즉 클래스를 정의하므로, constructor 프로퍼티는 객체의 타입을 판단하는데 사용될 수 있다.
<pre><code>if((typeof o == "object") && (o.contructor == Date)){
    문장
}
//instanceof 연산자는 constructor프로퍼티의 값을 사용한다. 따라서 아래와 같이 작성할 수 있다.
if((typeof o == "object") && (o instanceof Date)){
    문장
}</code></pre>
#### toString() 메서드
- toString() 메서드는 별도의 전달 인자 없이 호출되며, 메서드를 호출한 객체의 값을 어떠한 방식으로든 표현하는 문자열을 결과로 반환한다.
<pre><code>var x = {x:100, y:function(){ return x; }}
x.y.toString(); //"function(){ return x; }"</code></pre>
#### toLocaleString() 메서드
- 이 메서드의 목적은 객체의 지역화(localized)된 문자열 표현을 제공하기 위함이다.
- ?
#### valueOf() 메서드
- 객체를 문자열이 아니라 숫자 같은 다른 기본 타입으로 변환하려 할 때 호출된다.
#### hasOwnProperty() 메서드
- 이름을 담는 한 개의 문자열 전달인자를 받아서 객체가 이 프로퍼티를 소유하고 있는지 검사한다. 프로퍼티가 상속받은 것이 아니고 객체 안에 지역적으로 정의되어 존재한다면 true를 반환한다.
<pre><code>var o = {}
o.hasOwnProperty("name");   //false
o.hasOwnProperty("toString");   //false; toString은 상속받은 프로퍼티다.
Math.hasOwnProperty("cos");     //true; Math객체에 cos프로퍼티가 있다.</code></pre>
#### propertyIsEnumerable() 메서드
- hasOwnProperty와 마찬가지로 프로퍼티의 이름을 담은 문자열 전달 인자를 하나 받아, 해당 인자의 이름을 가진 프로퍼티가 상속받지 않고 직접 지역적으로 정의했는지 검사한다. 나아가 for/in 루프를 사용하여 열거될 수 있는 것인지 검사 후 조건이 충족되면 true를 반환한다.
####isPrototypeOf() 메서드
- 해당 메서드의 객체가 전달 인자로 주어진 객체의 프로토타입 객체라면 true를 반환한다.
- ?
### 배열
- 배열은 추가 기능을 조금 지닌 객체에 지나지 않는다. (typeof 연산자를 사용하여 확인할 수 있다. => "object")
<pre><code>var empty = [];  //빈 배열
var primes = [2, true, "true", 3];  //서로 다른 타입을 원소로 구성
//아래와 같이 임의의 표현식도 사용할 수 있다.
var year = 2018;
var table = [year, year+1, year+2];
//배열 리터럴은 객체 리터럴이나 또다른 배열 리터럴을 포함할 수 있다.
var b = [[1, {x:2, y:3}, [3, {x:4, y:5}]]];
//Array() 생성자를 사용하여 생성할 수도 있다.
var a = new Array();    //빈 배열 생성
var a = new Array(5,4,3,"test");    //각각 다른 4개의 원소 생성
//1개의 숫자값만 인자로 넘길 시 10개의 원소를 가진 배열이 생성된다. [,,,,]
//이때 각 원소의 값은 undefined이며 length 프로퍼티의 값은 생성자의 전달 인자에 명시된 수와 동일하다.
//이 방법은 배열에 저장될 원소의 개수를 미리 알 수 있을 때(알릴 때) 사용된다.
//이 경우에는 배열 리터럴은 적합치 않다.
var a = new Array(5);</code></pre>
#### 배열 원소 읽고 쓰기
- 배열의 인덱스에는 반드시 0보다 크거나 같고 정수를 사용해야만 한다.
#### 배열에 새로운 원소 추가하기
- 배열에 새로운 원소를 추가하려면 그 값을 할당하기만 하면 된다.
<pre><code>a[10] = 10;</code></pre>
- 배열의 인덱스는 연속적이지 않아도 된다. **자바스크립트는 배열에 실제로 저장된 원소들에 대해서만 메모리를 할당하도록 구현할 수 있다.**
<pre><code>//0부터 9,999개의 인덱스에 대해서는 메모리를 할당하지 않는다.
a[10000] = "this number : 10,000";</code></pre>
- 또한 배열원소는 객체에도 추가될 수 있다.
<pre><code>//객체에 "0"이라는 이름의 프로퍼티를 추가할 뿐이지 객체가 배열이 되지는 않는다.
var a = {x:200,y:200};
a[0] = "text";
console.log(a);    // {0:"text", x:200, y:200};</code></pre>
#### 배열 원소 삭제하기
- delete 연산자를 사용하면 배열 원소의 값을 undefined값으로 설정할 수 있지만 배열 원소 자체는 사라지지 않고 존재한다.
#### 배열의 길이
- 배열에는 원소의 수를 알려주기 위한 length라는 특별한 프로퍼티가 있다. 배열은 정의되지 않은 원소도 가질 수 있기 때문에 length 프로퍼티는 배열의 가장 큰 인덱스 값보다 언제나 하나 큰 값이다.
#### 배열 순회
<pre><code>var arr = [1,2,3,4,5];
for(var i = 0; i < arr.length; i++){
    console.log(i);
}
//배열 원소가 정의되어 있는지 검사하려면 아래와 같이 작성..
for(var i = 0; i < arr.length; i++){
    if(arr[i]){
        console.log(i);
    }
}</code></pre>
#### 다차원 배열
- 엄밀히 따지면 자바스크립트는 다차원 배열을 지원하지 않는다. 하지만 배열의 배열을 사용하여 효과적으로 다차원배열을 **흉내** 낼 수 있다.
- **구구단 표 만들기**
<pre><code>//다차원 배열 생성
var tbl = new Array(10);    //구구단표의 10개 행
for(var i = 0; i < tbl.length; i++){
    tbl[i] = new Array(10);     //각 행에는 열 개의 열이 있다.
}
//배열 초기화
for(var row = 0; row < tbl.length; row++){
    for(var col = 0; col < tbl[row].length; col++){
        tbl[row][col] = row * col;
    }
}
//5*7계산
var prdt = tbl[5][7];   //35</code></pre>
### 배열 메서드
#### join() 메서드
- 모든 배열의 원소를 문자열로 변환, 이어 붙여서 반환한다. 결과로 반환되는 문자열에서 배열워 원소들을 구분하기 위해 구분자 문자열이 사용되는데, Array.join()에 전달인자를 넘겨 구분자 문자열을 지정할 수 있으며 별도로 지정하지 않으면 콤마(,)가 기본값으로 사용된다.
<pre><code>var a = [1,2,3];
var str = a.join();     //"1,2,3"
var str2 = a.join('/');     //"1/2/3"</code></pre>
#### reverse() 메서드
- 배열 안의 원소 순서를 반대로 정렬하여 반환한다. 이 작업은 해당 배열 안에서 직접 수행된다.
<pre><code>var a = new Array(1,2,3);
var str = a.join();     //"1,2,3"
a.reverse();
var str2 = a.join();     //"3,2,1"</code></pre>
#### sort() 메서드
- 배열 안의 원소들을 정렬하여 반환한다. reverse() 메서드와 마찬가지로 배열 안에서 직접 수행된다. 별도의 전달인자 없이 호출하면, 배열 안의 원소들을 알파벳순으로 정렬한다. (정의되지 않은 원소들이 존재하면 이 원소들은 배열의 끝 부분으로 정렬된다.)
<pre><code>var a = new Array("apple", "cherry", "banana" );
a.sort();
var fin = a.join(', ');     //"apple, banana, cherry"

//알파벳 순으로 정렬하면 첫번째 숫자만 가지고 비교하기 때문에 아래와 같은 경우 의도치 않은 결과가 나올 수 있다.
var b = [332,112223,4,222222];
b.sort();    //[112223,222222,332,4];

숫자 크기순으로 정렬하려면 비교 함수를 sort()의 전달인자로 명시한다.
b.sort(function(a, b){
    return a-b;     //[4,332,112223,222222];
});

//전달인자 a가 b보다 먼저 나와야하면 비교 함수는 0보다 작은 숫자를 return한다.
//전달인자 a가 b보다 뒤에 나와야 한다면 0보다 큰 숫자를 return한다.</code></pre>
#### concat() 메서드
- 본래 배열의 모든 원소에 concat() 메서드의 전달인자들을 전부 이어붙인 배열을 **새롭게 생성**하여 반환한다.
<pre><code>var a = [1,2,3];
var b = a.concat(4,5);
console.log(a);     //[1,2,3]
console.log(b);     //[1,2,3,4,5]</code></pre>
#### slice() 메서드
- 배열의 일부분(slice) 혹은 부분 배열(subarray)을 반환한다. slice()메서드는 전달인자를 두 개 받는데, 각 인자는 반환될 부분의 처음과 끝을 각각 명시한다. 이때 반환되는 배열은 첫 번째 전달인자가 지정하는 위치부터 두번째 전달인자가 지정하는 위치를 제외한 그 사이의 모든 원소를 포함한다.
<pre><code>var a = [1,2,3,4,5];
a.slice(0, 3);  //[1,2,3]
a.slice(3);     //[4,5]
a.slice(1, -1);     //[2,3,4]
a.slice(-3, -2);    //[3] //?</code></pre>
#### splice() 메서드
- 배열에 원소를 삽입하거나 원소를 제거하려 할 때에 범용적으로 사용할 수 있다. 이런 작업은 배열 안에서 직접 수행된다. (slice(), concat()과 다르다.)
- splice()의 첫 번째 전달인자는 배열 상에서 삽입 혹은 삭제 작업이 시작하게 될 위치를 지정하며, 두 번째 전달인자는 배열에서 삭제할(잘라낼) 원소들의 개수를 지정한다. 두 번째 전달인자를 지정하지 않으면 첫번째 전달인자 위치에서 배열의 마지막 원소까지를 전부 잘라낸다.
<pre><code>var a = [1,2,3,4,5,6,7,8];
a.splice(4);    //[5,6,7,8]
console.log(a);     //[1,2,3,4]
a.splice(1,2);      //[2,3]
console.log(a);     //[1.4]
a.splice(1,1);      //[4]
console.log(a);     //[1]</code></pre>
- 만약 세 개 이상의 전달인자를 넣을 경우 세 번째 전달인자부터는 배열에 새롭게 이어 붙일 원소들을 지정한다.
<pre><code>var a = [1,2,3,4,5];
a.splice(2, 0, "a", "b");   //[]를 반환한다.
console.log(a);     //[1,2,"a","b",3,4,5]</code></pre>
a.splice(2,2,[1,2],3);  //["a","b"]를 반환한다.
console.log(a);     //[1,2,[1,2],3,3,4,5];
#### push(), pop() 메서드
- push(), pop() 메서드를 사용하면 배열을 마치 스택인 것처럼 조작할 수 있다. 두 메서드 모두 새로운 배열을 만들어 반환하는 것이 아닌, 배열 그 자체를 변화시킨다.
- push() 메서드는 하나 이상의 원소들을 배열의 끝 부분에 이어 붙이고 배열의 새로운 길이를 반환한다.
- pop() 메서드는 push()와 반대로 작동한다. 배열의 마지막 원소를 제거하고 배열의 길이를 감소시킨 후 배열에서 제거한 원소를 반환한다.
<pre><code>var stack = [];
stack.push(1,2);    //2를 반환한다.
console.log(stack);     //[1,2]
stack.pop();        //2를 반환한다.
console.log(stack);     //[1]
stack.push[3]   //2를 반환한다.
console.log(stack);     //[1,3]
stack.pop();    //3을 반환한다.
console.log(stack);     //[1]</code></pre>
#### unshift(), shift() 메서드
- unshift(), shift() 메서드는 push(), pop() 메서드와 매우 유사하게 작동하는데, 배열의 끝이 아니라 배열의 맨 앞에서 원소를 삽ㅇ비하고 제거한다는 점이 다르다.
- unshift() 메서드는 이미 배열에 들어있는 원소들을 인덱스가 높은 방향으로 옮겨 새로운 원소들을 삽ㅇ비할 공간을 만들고, 삽입 작업을 수행 후 배열의 새로운 길이를 반환한다.
- shift() 메서드는 배열의 첫 번째 원소를 제거, 반환한다. (제거되면서 생긴 빈 공간은 배열의 원소들이 앞으로 옮겨져 메꾼다.)
<pre><code>var a = [];
a.unshift(1);   //1을 반환한다.
console.log(a);     //[1]
a.unshift(22);     //2를 반환한다.
console.log(a);     //[22,1];
a.shift();  //22를 반환한다.
console.log(a);     //[1]</code></pre>
- unshift()의 전달인자로 여러 개의 원소를 한번에 추가하면 예상치 못한 결과를 얻을 수 있다.
<pre><code>var a = [1,2,3];
a.unshift(4,5,6);
console.log(a);     //[4,5,6,1,2,3];
var b = [1,2,3];
b.unshift(4);
b.unshift(5);
b.unshift(6);
console.log(b);     //[6,5,4,1,2,3];</code></pre>
#### toString() 메서드
- 배열의 toString() 메서드는 우선 배열의 모든 원소를 문자열로 변형하고, 이 문자열들을 콤마(,)로 분리한 목록을 반환한다.
<pre><code>[1,2,3,"bar","f"].toString();    //"1,2,3,bar,f"
[1, [2,"c"]].toString();    //"1,2,c"</code></pre>

***

## 함수
- 함수란 일단 한 번 정의되면 여러 횟수에 걸쳐 호출되거나 실행될 수 있는 코드 블록이다.
- 함수는 매개변수(parameter) 혹은 전달인자(agument)라 불리는 지역변수를 가질 수 있는데 이러한 변수의 값은 함수가 호출되는 시점에 주어진다.
- 객체 상에서 호출되는 함수는 메서드라 칭하며 이때 객체는 암묵적 전달인자(implicit agument)로 전달된다.
### 함수 정의와 호출
- 함수는 임의개수의 전달인자를 가질 수 있으며 return 문을 반드시 사용할 필요는 없다.
<pre><code>//함수 선언
function msg(txt){
    document.write(txt);
}
//함수 호출(이 함수는 return 문이 없기 때문에 undefined 값을 반환한다.)
msg("hello");</code></pre>
- 함수에 return 문이 없으면 함수 몸체를 이루는 문장들을 하나씩 실행한 뒤에 undefined 값을 호출자에게 반환한다.
- 일반적으로 매개변수는 실행되는 함수의 몸체 안에서만 유효하며 함수 밖에서 또는 함수가 반환한 후에는 접근할 수 없다.
### 중첩된 함수
- 자바스크립트 함수는 중첩되어 사용될 수 있다.
<pre><code>function(a, b){
    function square(x){return x*x;}
    return Math.sqrt(square(a) + square(b));
}</code></pre>
### 함수 리터럴
- 함수 리터럴은 이름 없는 함수를 정의하는데 수용되는 표현식이다.
<pre><code>function f(x){ return x*x; };    //function 문
var f = function(x){ return x*x; };     /함수 리터럴</code></pre>
- 함수 리터럴은 문장이 아니라 표현식으로 생성된다. 이름 붙이지 않아도 되는 일회용 함수를 정의하는데 적합하다. 변수에 저장될 수 있고 다른 함수에 전달인자로써 전달될 수 있으며 곧바로 호출될 수도 있다.
<pre><code>var f = function(){ return x*x };     //함수를 정의하여 변수에 저장한다.
a.sort(function(a,b){return a - b;});   //함수를 정의하여 다른 함수에 전달한다.
var tensquared = (function(x){return x*x;})(10)     //정의하여 바로 호출한다.</code></pre>
### 함수 이름 붙이기
- 함수 이름은 일반적으로 동사 혹은 동사로 시작하는 구절이다.
<pre><code>// 관습적으로 함수 이름은 소문자로 시작한다.
like();
fnc();
//두 단어 이상을 포함할 때는 밑줄 또는 카멜표기법으로 연결
like_this();
likeThis();
//내부적으로만 사용하거나 숨겨진 함수로 사용하려면 밑줄 문자로 함수이름을 시작한다.
_likeThis();</code></pre>
### 함수 전달인자
#### 생략 가능한 전달인자
- 함수가 정의 당시에 선언된 전달인자의 개수보다 적은 수의 전달인자와 함께 호출되면 호출 시점에 지정되지 않은 전달인자들의 값은 undefined가 된다.
- 생략 가능한 전달인자를 사용하여 함수를 작성할 때는 생략 가능한 것들을 전달인자 목록의 끝에 위치하게 하여, 호출할때 임의로 생략할 수 있게 하는 것이 중요하다.
#### 가변 길이 전달인자 목록 : 전달인자 객체
- 함수는 고정된 개수의 이름 붙은 전달인자로 정의되지만 호출 시점에서는 고정된 개수와 상관없이 임의 개수의 전달인자들을 건네받을 수 있다.
- 만약 함수 f를 두 개의 전달인자와 함께 호출한다면 첫번째 전달인자는 매개변수 이름이나 arguments[0]으로 접근할 수 있다. 또한 arguments에는 실제 배열처럼 length프로퍼티가 있다.
<pre><code>//함수가 올바른 개수의 전달인자들과 함께 호출되었는지 검사한다.
function f(x,y,z){
    //전달인자 개수 검사
    if(arguments.length !=3){
        throw new Error("전달인자가 " + arguments.length + "개 밖에 없다. 3개의 전달인자를 포함해라");
    }
}</code></pre>
#### callee 프로퍼티
- Arguments 객체는 배열 원소 뿐만 아니라 현재 실행되고 있는 함수를 가리키는 callee 프로퍼티를 추가로 정의한다.  (잘 사용되지 않음)
### 객체 프로퍼티를 전달인자로 사용하기
- 함수의 전달인자가 세 개 이상 필요하다면, 함수를 호출할 때 전달할 전달인자들의 순서를 기억하는 일이 어려워진다. 이 때는 전달인자를 순서에 관계없이 이름과 값의 쌍으로 전달하여 주는 방법을 제공해주면 된다.
<pre><code>//이름, 성별, 나이, 직업, 몸무게
//아래 함수는 문자열과 숫자가 들어가야하는 인자의 위치를 기억하고 있어야 한다.
function exam(name, gender, age, job, weight){
    //문장
}
exam("찰수", "남자", 23, "농부", 82);
//아래와 같이 수정 가능하다.
function exam(args){
    args.name;
    args.gender;
    args.age;
    //...
    //문장
}
var person = {
    name : "찰수",
    gender : "남자",
    age : 23,
    job : "농부",
    weight : "82"
}
exam(person);</code></pre>
### 전달인자 데이터 타입
- 자바스크립트 함수의 전달인자들은 데이터 타입이 선언되지 않고, 함수에 값을 전달할 때도 데이터 타입 검사를 수행하지 않는다.
- 때문에 전달인자의 데이터 타입을 주석으로 적어 넣어 코드 자체를 문서화하면 도움이 된다.
<pre><code>function max(/* number */){
    문장
}</code></pre>
### 데이터로서의 함수
- 함수의 가장 중요한 특징은 프로그램 상에서 정의되고 또 호출될 수 있다는 점이다.
- 자바스크립트에서 함수는 문법일 뿐만 아니라 데이터이기도 하다. 즉, 변수에 할당되거나 객체 프로퍼티와 배열 원소들에 저장될 수 있고 전달인자 등으로도 사용될 수 있다.
<pre><code>function square(x){ return x*x; }
var a = square(4);      //변수 a에는 숫자 16이 저장된다.
var b = square;     // b는 square와 같은함수이다.
var c = b(4);   //변수 c에는 숫자 16이 저장된다.</code></pre>
- 함수는 전역변수 뿐만 아니라 객체 프로퍼티에도 할당될 수 있는데, 이를 메서드라 부른다.
<pre><code>var o = new Object();
o.square = function(x){ return x*x; }   //함수 리터럴
y = o.square(4);    //변수 y에는 숫자 16이 저장된다.</code></pre>
- 배열 원소에 함수를 할당하는 경우에는 함수명도 필요가 없다.
<pre><code>var a = new Array();
a[0] = function(x){ return x*x; }
a[1] = 4;
a[2] = a[0](a[1]);      //a[2]에는 숫자 16이 저장된다.</code></pre>
> **함수를 데이터로서 사용하기**
<pre><code>//간단한 함수를 몇 개 정의한다.
function add(x,y){ return x + y; }
function subtract(x,y){ return x - y; }
function multiply(x,y){ return x * y; }
function divide(x,y) { return x / y; }

//아래 정의되는 함수는 위 연산자 함수 중 하나를 전달인자로 받아
//두 개의 피연산자와 함께 호출한다.
function operate(operator, operand1, operand2){
    return operator(operand1, operand2);
}
//(2+3) + (4*5) 같은 수식을 계산하기 위해 아래와 같이 함수를 호출한다.
var i = operate(add, operate(add, 2, 3), operate(multiply, 4, 5));\
//최초 정의한 연산 함수들을 함수 리터럴을 사용해 재 정의한다.
//함수 리터럴들은 객체 리터럴안에 둔다.
var operators = {
    add: function(x,y){ return x + y; },
    subtract: function(x,y){ return x - y; },
    multiply: function(x,y){ return x * y; },
    divide: function(x,y) { return x / y; },
    pow: Math.pow   //이미 정의되어 있는 함수도 사용 가능하다.
}
//아래 함수는 연산자 함수의 이름을 전달인자로 받아 작동한다.
//객체 안에서 연산자 함수를 검색한 후, 주어진 피연산자들과 함께 호출한다.
function operate2(op_name, operand1, operand2){
    if(typeof operators[op_name] == "function"){
        return operators[op_name](operand1, operand2);
    }else{
        throw "unknown operator";
    }
}
//("hello +" "+ "world") 같은 표현식의 값을 계산하기 위하여,
//아래와 같이 호출할 수 있다.
var i = operate2("add", "hello", operate2("add", " ", "world"))</code></pre>
### 메서드로서의 함수
- 메서드는 객체 프로퍼티에 저장되어 객체를 통해 호출할 수 있는 함수에 지나지 않는다.
- 메서드에는 중요한 프로퍼티가 하나 있다. 호출된 메서드가 속하여 있는 객체는 메서드 몸체 안에 this라는 키워드의 값으로 저장된다. o.f() 메서드를 호출할 때 메서드의 몸체 안에서는 객체 o를 this키워드로 가리킬 수 있다.
<pre><code>var calculator = {
    operand: 1,
    operand2: 1,
    compute: function(){
        this.result = this.operand + this.operand2;
    }
}
calculator.compute();
console.log(calculator.result);     //2</code></pre>
- 대체로 메서드는 그 메서드가 속해 있는 객체에 대해 무엇인가 연산을 수행하기 때문에 메서드 형태로 함수를 호출하는 구문은 그 함수가 객체와 관련하여 자동한다는 사실을 표현하는 세련된 방법이다.
<pre><code>//아래 가상 함수(메서드)는 객체 rec위에서 완전히 동일한 연산을 수행한다.
//첫 번째 메서드 호출이 이 연산의 주요 초점이 객체 rect임을 명확히 나타낸다.
rect.setSize(width, height);
setRectSize(rect, width, height);</code></pre>
- 만약 함수를 메서드로서가 아니라 함수로 호출했다면 this 키워드는 전역 객체를 가리킨다.
- this가 변수 이름이나 프로퍼티 이름이 아니라 키워드임을 주의해야한다. this에는 절대 다른 값을 할당할 수 없다.
### 생성자 함수
- 생성자 함수는 객체의 프로퍼티들을 초기화하는 함수이며 new 연산자와 함꼐 사용될 의도로 작성된다.
- new연산자는 새로운 객체를 생성, this 키워드의 값으로 하여 생성자 함수를 호출한다.
### 함수 프로퍼티와 메서드
#### length 프로퍼티
- Function 객체의 length 프로퍼티는 함수에 선언된 매개변수가 정확히 몇 개 인지 명시한다. arguments.lengthd와는 달리 length 프로퍼티는 함수 몸체의 안과 밖에서 모두 사용할 수 있다.
<pre><code>//함수가 기대하는 것과 같은 개수의 전달인자를 건네받았는지 검사하는 함수
function argCheck(args){
    //실제 건내받은 전달인자 수
    var actual = args.length;
    //함수가 기대하는 전달인자 수
    var expected = args.callee.length;
    //두 수가 일치하지 않으면 예외 발생
    if(actual != expected){
        throw new Error('error!'+ actual + '개의 전달인자를 넘겼습니다. ' + expected + '개의 전달인자만 넘겨주세요.');
    }
}
function f(x,y,z){
    //메서드가 기대하는 개수의 전달인자를 실제로 전달 받았는지 검사
    //그렇지 않다면 예외 발생
    argCheck(arguments);
    //나머지 문장
    return x+y+z;
}</code></pre>
#### prototype 프로퍼티
- 모든 함수에는 미리 정의된 prototype 객체를 가리키는 prototype 프로퍼티가 있다. 이 prototype 객체는 함수가 new 연산자를 통해 생성자로 사용될 때, 새 객체를 정의하는 과정에서 매우 중요한 역할을 수행한다.
#### 나만의 함수 프로퍼티 정의
- 함수 호출의 경계를 넘어 존재가 유지되는 변수를 사용해야 할 때가 있다. 이땐 전역 변수를 정의하여 네임스페이스를 지저분하게 하는 대선 Function객체의 프로퍼티를 사용하는 것이 유용하다.
<pre><code>//'정적' 변수를 생성, 초기화한다.
//함수 선언은 코드가 실행되기 전 처리된다. 따라서 아래와 같은 할당 연산을
//함수 선언 이전에 실제로 수행할 수 있다.
uniqueNum.counter = 0;
//아래 선언된 함수는 호출될 때마다 서로 다른 고유한 값을 반환한다.
//마지막으로 반환한 값에 대한 정보를 기록하기 위해 '정적' 프로퍼티를 사용한다.
function uniqueNum(){
    //'정적' 변수를 증가시키고 반환한다.
    counter : 0;
}</code></pre>
#### apply()와 call() 메서드
- ECMAScript는 모든 함수에 대하여 call()과 apply() 메서드를 정의한다. 이 메서드를 사용하면 함수가 마치 다른 어떤 객체의 메서드인 것처럼 호출 될 수 있다.
<pre><code>obj = new Array;
function f(x,y){ return x + y; }
f.call(obj, 1, 2);

//위 표현은 아래와 유사하다.
obj.m = f;
obj.m(1, 2);
delete obj.m;</code></pre>
- apply() 메서드는 call()메서드와 유사하지만 함수로 건네줄 전달인자들을 배열로 지정한다는 점이 다르다.
<pre><code>f.apply(obj, [1,2]);</code></pre>
### 유용한 함수들
#### 객체용 함수들
<pre><code>//객체 obj의 열거 가능한 프로퍼티들의 이름을 담은 배열을 반환한다.
function getPropertyNames(/* object */ obj){
    var r = [];
    for(name in obj){ r.push(name); }
    return r;
}

//객체 form의 열거 가능한 프로퍼티들을 객체 to로 복사한다.
//만약 to가 null이면 새로운 객체를 생성한다. 아래 함수는 객체 to를 반환하거나
//새로 생성한 객체를 반환한다.
function copyProperties(/* object */ from, /* optional object */ to){
    if(!to){ to = {}; }
    for(p in from){
        to[p] = from[p];
    }
    return to;
}

//객체 from의 열거 가능한 프로퍼티들을 객체 to로 복사하되,
//to에 의해 정의되지 않은 프로퍼티만 복사한다.
//아래 함수는 to에 미리 정의되어 있지 않은 값들에 대해 from에 저장해 둔
//기본값들을 사용하려 할 때 유용하다.
function copyUndefinedProperties(/* object */ from, /* object */ to){
    for(p in from){
        if(!p in to) {
            to[p] = from[p];
        }
    }
}</code></pre>
#### 배열을 위한 함수
<pre><code>//배열 a의 각 원소를 지정된 술어(predicate) 함수로 전달한다.
//술어 함수가 true를 반환한 원소들로 이루어진 배열을 결과로서 반환한다.
function filterArray(/* array */a, /* Boolean function */ predicate){
    var results = [];
    //술어 함수가 배열의 길이를 반환할 경우에 대비하여
    var length = a.length;
    for(var i = 0; i < length; i++){
        var element = a[i];
        if(predicate(element)){
            result.push(element);
        }
    }
    return results;
}

//배열 a의 각 원소를 지정된 함수 f로 전달하여 얻은 결과들을 원소로 하는
//배열을 반환한다.
function mapArray(/* array */ a, /* function */ f){
    var r = [];
    //함수 f가 배열 길이를 반환할 경우를 대비
    var length = a.length;
    for(var i = 0; i < length; i++){
        r[i] = f(a[i]);
    }
    return r;
}</code></pre>
#### 함수용 함수 ~~??~~
- 아래 함수들은 중첩된 함수를 사용하고 반환한다. 이렇게 반환되는 중첩된 함수들은 때때로 **클로저(closure)**라 불린다.
<pre><code>//함수 f를 객체 o의 메서드로 하여 호출하는 독립형 함수를 반환한다.
//이것은 메서드를 함수에 전달하려 할 때 유용하다. 만약 함수를 그 함수의 객체와
//연결하지 않으면, 그 연관 관계는 소실되며 전달한 메서드는 일반 함수처럼
//호출된다.
function bindMethord(/* object */ o, /* function */ f){
    return function(){ return f.apply(o, arguments) }
}
???
//함수 f를 지정된 전달인자와 함께 호출해 주는 함수를 반환한다.
//이렇게 반환된 함수는 또한 추가적인 전달인자들과 함께 호출될 수 있다.
//(때때로 'currying'이라 불린다.)
function bindArguments(/* function */f, /* initial arguments */){
    var boundArgs = arguments;
    return function(){
        //전달인자들로 구성된 배열을 만든다. 이 배열은 이전에 건네받은
        //전달인자를 원소로 시작하여, 지금 추가로 건네받은 전달인자까지
        //포함한다.
        var args = [];
        for(var i = 1; i < boundArgs.length; i++){
            args.push(boundArgs[i]);
        }
        for(var i = 0; i < arguments.length; i++){
            args.push(arguments[i]);
        }
        //전달인자들과 함께 함수를 호출한다.
        return f.apply(this, args);
    }
}
???</code></pre>
## 함수 유효 범위와 클로저
- 자바스크립트 함수의 몸체는 전역 유효 범위와는 다른 지역 유효 범위 상에서 실행된다.
### 어휘적 유효 범위(Lexical Scoping)
- 자바스크립트의 함수는 동적이라기보다 어휘적으로 유효 범위가 정해진다. 이는 함수가 실행되는 유효범위가 아니라 함수가 정의되어 있는 유효범위 안에서 실행됨을 의미한다.
- 최상위 레벨에서 유효범위 체인은 단순히 전역 객체들로 구성되며 어휘범위는 특별히 의미를 지니지 않는다. 그러나 중첩된 함수를 정의하면 유효 범위는 함수를 포함한다. 이는 중첩된 함수가 그 함수를 포함하는 함수의 모든 전달인자와 지역 변수들에 접근할 수 있음을 의미한다.
- 함수가 정의될 당시의 유효범위 체인은 고정되어 있을지라도 그 유효범위 체인안에 정의되어 있는 프로퍼티들은 변할 수 있다. 즉 **함수는 함수가 호출되는 시점을 기준으로, 연결되어 있는 모든 것들에 접근할 수 있다.**
### 호출 객체
- 자바스크립트 인터프리터가 함수를 호출할 때엔 먼저 유효 범위를 함수가 정의될 당시의 효력을 지니는 유효 범위 체인으로 설정한다. 그 후에 호출 객체(activation 객체)로 알려진 새로운 객체를 생성, 유효범위 체인의 맨 앞에 추가한다.
- ~?? 213p~
### 네임스페이스로서의 호출 객체
- 때로는 전역 네임스페이스를 어지럽히는 대신 임시 네임스페이스로 작동할 수 있는 호출 객체를 생성하여, 이 안에 원하는 변수를 정의하고 프로퍼티를 생성하기 위한 용도로 함수를 정의하는 것이 유용할 수 있다.
<pre><code>function init(){
    //코드
    //선언된 모든 변수는 전역 네임 스페이스를 어지럽히는 대신
    //호출 객체의 프로퍼티가 된다.
}
init();     //함수 호출 필수</code></pre>
- 위 코드는 함수를 가리키는 단 한 개의 프로퍼티 init을 전역 네임스페이스에 추가한다. 또 다른 방법으로는 아래와 같이 익명(anonymous)함수를 정의하고 호출하는 방법이 있다.
<pre><code>(function(){
    //코드
    //선언된 모든 변수는 전역 네임 스페이스를 어지럽히는 대신
    //호출 객체의 프로퍼티가 된다.
})();       //함수 리터럴을 종결하고 이를 즉시 호출한다.</code></pre>
### 클로저로서의 중첩된 함수
- ~??215 - 220 클로저??~
### Function() 생성자
- Function() 생성자를 사용하는 것은 보통 함수 리터럴을 사용하는 것보다 난해하기 때문에 널리 쓰이지는 않는다.
<pre><code>var f = new Function('x', 'y', 'return x*y;');
//위 코드는 아래와 같다
function f(x,y) { return x*y; }</code></pre>
- 생성자의 가장 중요한 점은 생성된 함수가 어휘적 유효범위를 사용하지 않는다는 것이다. 대신 Function() 생성자에 의해 생성된 함수는 마치 최상위 레벨의 함수인 것처럼 컴파일된다.
<pre><code>var y = 'global';
function constructFunction(){
    var y = 'local';
    return new Function('return y');
}
console.log(constructFunction());
// 위 코드는 'global'을 출력한다. 이는 Function() 생성자에 의해 변환된 함수가
// 지역 유효 범위를 사용하지 않기 때문이다.
// 만약 함수 리터럴을 대신 사용했다면 'local'을 출력할 것이다.

// ??정상적으로 출력이 안된다.</code></pre>

---

## 클래스, 생성자, 프로토타입
- 자바스크립트는 자바, C++, C#이 제공하는 것과 같은 실제 클래스를 지원하지 않는다. 대신 프로토타입 객체나 생성자 함수를 사용하여 모조클래스를 정의할 수 있다.
### 생성자
<pre><code>new Object();
var array = new Array(10);
var today = new Date();</code></pre>
- 위와 같이 new 연산자 뒤에는 항상 함수 호출이 따라와야 한다. new 연산자는 아무 프로퍼티도 없는 새 객체를 생성한 후 new 연산자 뒤에 있는 함수를 호출하고, this 키워드가 새로 생성된 객체를 가리키게 한다. 이런식으로 new 연산자와 함께 사용되도록 설계된 함수를 **생성자 함수 또는 간단하게 생성자**라고 부른다.
- 자바스크립트에서는 간단하게 this가 가리키는 객체에 몇 가지 프로퍼티들을 추가하는 생성자 함수를 정의할 수 있다.
<pre><code>//생성자 정의
//'this'와 연관되어 있는 객체를 초기화 한다.
function Rectangle(w, h){
    this.width = w;
    this.height = h;
}

//Rectangle 객체를 두 개 만들기 위해 생성자를 호출한다.
//생성자가 새 객체를 각각 초기화할 수 있게 너비와 높이를 인자로 넘긴다.
var rect1 = new Rectangle(2,4);     // rect1 = { width:2, height:4 }
var rect2 = new Rectangle(8.5, 11);     // rect2 = { width:8.5, height:11 }</code></pre>
### 프로토타입과 상속
- 메서드는 객체의 프로퍼티이자 호출 가능한 함수이다. 메서드를 호출하면, 메서드 내의 this 키워드는 메서드가 속한 객체를 가리킨다.
<pre><code>//Rectangle의 객체로 표현된 사각형의 넓이를 계산
function computeAreaOfRectangle(r){ return r.width * r.height; }
//위 함수는 정상적으로 작동을 하지만, 객체지향적 방법은 아니다.
//객체를 함수의 인자로 넘겨주는 방법보다는 메서드를 사용하는 것이 좋다.

//Rectangle객체 생성
var r = new Rectangle(8.5, 11);
//메서드 추가
r.area = function(){ return this.width * this.height; }
//넓이를 구하기 위하여 메서드 호출
var a = r.area();

//아래는 계산하는 함수를 생성자 내부에서 연결시키는 방법이다.
function Rectangle(w, h){
    this.width = w;
    this.height = h;
    this.area = function(){ return this.width * this.height; }
}
var r = new Rectangle(8.5, 11);
var a = r.area();
</code></pre>
227 ~ 228?
#### 상속받은 프로퍼티의 읽기와 쓰기
229 ~ 230?
#### 내장형 타입의 확장
231 ~ 233?
### 자바스크립트의 클래스 시뮬레이션
- 자바스크립트가 객체라는 데이터 타입을 지원하기는 하지만, 클래스를 구체적으로 표현할 수 있는 방법은 제공하지 않는다. 때문에 생성자와 프로토타입 객체를 통해 클래스를 흉내 낸다.
- 한 클래스에 속하는 여러개의 객체가 있을 수 있는데 이 객체들을 클래스의 인스턴스라 부르기도 한다. 즉, 클래스는 여러 개의 인스턴스를 가질 수 있으며, 객체(클래스의 인스턴스)를 생성하는 과정을 '인스턴스화'라고 표현하기도 한다.
- 보편적으로 클래스의 이름은 대문자로 시작하며, 객체의 이름은 소문자로 시작하여 클래스와 객체를 구분한다.
#### 인스턴스 프로퍼티
- 모든 객체에는 자신만의 인스턴스 프로퍼티 사본이 있다. 예를 들어 한 클래스에 속하는 객체가 열 개 있다면 인스턴스 프로퍼티 사본이 열 개 만들어진다. 예를 들어 Rectangle 클래스의 모든 객체에는 사각형의 너비를 나타내는 width 프로퍼티가 있다. 이때, width는 인스턴스 프로퍼티이다. 각 객체에는 자신만의 인스턴스 프로퍼티 사본이 있기 때문에 이 프로퍼티는 객체가 개인적으로 접근한다.
<pre><code>//r이 Rectangle 클래스의 인스턴스라면 r의 width는 아래와 같은 방법을 사용하여 참조된다.
r.width;</code></pre>
- 자바스크립트에서 객체의 프로퍼티는 기본적으로 인스턴스 프로퍼티가 되지만, 자바스크립트에서의 인스턴스 프로퍼티는 생성자 함수가 생성하고 초기화시키는 프로퍼티라고 하겠다.
#### 인스턴스 메서드
- 인스턴스의 메서드는 데이터 값이 아니라 메서드라는 점을 제외하면 인스턴스 프로퍼티와 상당히 비슷하다.
<pre><code>//Rectangle 클래스의 area() 메서드는 하나의 인스턴스 메서드이다.
//이 메서드는 아래와 같이 Rectangle의 객체 r이 호출한다.
a = r.area();</code></pre>
- 자바스크립트에서 클래스의 인스턴스 메서드는 생성자의 프로토타입 객체가 가진 프로퍼티에 함수 값을 넣어주는 방법을 통해 정의된다. 이 생성자를 통해 생성되는 모든 객체는 함수에 대한 참조를 상속받고 이를 공유한다.
#### 클래스 프로퍼티
236 ~ 237?
#### 클래스 메서드
- 클래스 메서드는 클래스의 인스턴스보다 클래스 자체와 연관이 있다. 특정 인스턴스를 통해 호출되는 것이 아닌 클래스 자체를 통해 호출된다.
- 클래스 프로퍼티와 마찬가지로 클래스 메서드도 전역에서 접근할 수 있다. 특정한 메서드에서 작동하는 것이 아니기 때문에, 쉽게 클래스를 통해 호출되는 함수라고 생각할 수 있다.
- 함수와  클래스를 연관시키면 네임스페이스에서 보호 영역을 제공받을 수 있으며 이를 통해 네임스페이스의 충돌을 방지할 수 있다.
#### 클래스 예
- 아래 코드는 원을 표현하기 위한 객체를 생성할 생성자 함수와 프로토 타입 객체에 대한 것이다. 인스턴스 프로퍼티와 인스턴스 메서드, 클래스 프로퍼티, 클래스 메서드가 포함되어 있다.
<pre><code>//생성자 함수 정의
function Circle(radius){
    //r은 인스턴스 프로퍼티이며, 생성자 안에서 정의되고 초기화된다.
    this.r = radius;
}
//Circle.PI는 클래스 프로퍼티다. 이는 생성자 함수의 프로퍼티다.
Circle.PI = 3.14159;

//아래는 원의 넓이를 계산하기 위한 인스턴스 메서드가 정의되어 있다.
Circle.prototype.area = function(){ return Circle.PI * this.r * this.r; }

//아래 클래스 메서드는 Circle의 두 객체들을 받아서 더 큰 반지름을 가진 것을
//반환한다.
Circle.max = function(a,b){
    a.r > b.r ? return b : return a;
}

//아래는 위 정의된 필드를 사용하는 예이다.
var c = new Circle(1,0);        //Circle 클래스의 인스턴스를 하나 만든다.
c.r = 2.2;                      //인스턴스 프로퍼티 r의 값을 지정한다.
var a = c.area();               //인스턴스 메서드인 area()를 호출한다.
var x = Math.exp(Circle.PI);    //클래스 프로퍼티인 PI를 사용하여 계산을 한다
var d = new Circle(1,2);        //또 다른 Circle 인스턴스를 만든다.
var bigger = Circle.max(c,d);   //클래스 메서드 max()를 사용한다.</code></pre>
#### private 멤버
- 객체지향 언어들의 공통점은 클래스의 프로퍼티를 클래스 외부의 다른 코드에서 조작할 수 없고 클래스의 메서드만 사용할 수 있게 private으로 선언할 수 있다는 것이다.
- '데이터 캡슐화'라는 기술은 프로퍼티를 private화 하고 특별한 메서드를 통해서만 이들을 읽거나 쓸 수 있게 한다.
- 자바스크립트는 클로저를 사용하여 이를 흉내 낼 수 있지만 이를 위해서는 인스턴스 마다 접근 메서드가 저장되어 있어야 한다.
- 아래 코드는 자바스크립트에서 어떻게 구현되는지 보여준다. Rectangle은 width와 height의 값이 바뀌지 않으며, 접근 메서드를 통해서만 이 프로퍼티들을 사용할 수 있다.
<pre><code>function ImmutableRectangle(w, h){
    //이 생성자는 초기화시킬 객체의 width와 height 프로퍼티를 저장하지 않는다.
    // 대신 객체 접근 메서드들을 정의해준다.
    //이 메서드들은 클로저이며, width와 height의 값은 메서드의 유효 범위 체인 안에 있다.
    this.getWidth = function(){ return w; }
    this.getWHeight = function(){ return h; }
}

//클래스의 프로토타입 객체에 일반 메서드가 올 수 있다.
ImmutableRectangle.prototype.area = function(){
    return this.getWidth() * this.getHeight();
}</code></pre>
- http://www.crockford.com/javascript/private.html
### 공통적인 객체 메서드
- 새로운 자바스크립트 클래스를 정의할 때 항상 염두에 두고 정의해야 하는 메소드가 몇가지 있다.
#### toString() 메서드
- toString()에 깔려있는 기본 아이디어는 객체의 각 클래스가 자신을 문자열로 표현할 수 있게 만드는 것이다. 하나의 클래스를
정의하면 클래스의 신스턴스가 문자열로 변환될 수 있게 반드시 toString() 메서드를 정의해야 한다. 이 문자열에는 변환되는 객체의 대한 정보가 들어있어야 한다.
또한, 이렇게 해두면 디버깅 시 유용하게 사용된다. 문자열이 적당하게 구성되면 그 자체만으로 프로그램 내 유용한 정보가 될 수 있다.
<pre><code>Circle.prototype.toStirng = function(){
    return "[Circle of radius " + this.r + ", centered at (" + this.x + ", " + this.y + ").]";
}
//"[Circle of radius 1, conterd at (0,0).]"</code></pre>
#### valueOf() 메서드
- valueOf() 메서드는 toString()과 상당히 유사하지만, 자바스크립트가 객체를 Number 같은 문자열 외의 기본 타입으로 변환하려 할때 호출한다.
#### 비교 메서드
- 자바스크립트의 동등 연산자는 값이 아닌 참조를 통해 객체를 비교한다. 직접 만든 클래스의 인스턴스들이 서로 동등한지를 검사할 수 있게 하려면 equals()라는 인스턴스
메서드를 정의하면 된다.
244~265?
## 모듈과 네임스페이스
- 자바스크립트는 언어 자체적으로 모듈을 생성하거나 관리하기 위한 기법을 제공하지 않기 때문에, 이식할 수 있으며 재사용 할 수 있는 자바스크립트 코드를 작성하는 것은 기본적인
관심과 관련된 문제이다.
- 가장 중요한 관습은 두 모듈이 같은 이름을 가진 전역 프로퍼티를 정의했을 때 발생할 수 있는 이름 충돌을 피하기 위해 네임스페이스를 사용하는 것이다.
- 다른 한가지 방법은 모듈 초기화 코드를 사용하는 것이다.
### 모듈과 네임스페이스 생성
- 내가 작성한 코드가 어디서나 사용될 수 있고, 어떤 모듈과도 함께 사용될 수 있게 작성하고 싶다면 가장 중요한 규칙은 전역변수를 정의하지 않는 것이다. 전역 변수를 정의하면, 모듈을 사용하는 다른 개발자 혹은 다른 모듈이 그 변수를 덮어쓸 위험이 항상 존재한다.
- 해결책은 모듈에서 사용할 모든 메서드와 프로퍼티를, 그 모듈을 위해 특별히 생성한 네임스페이스 안에 정의하면 된다.
<pre><code>//네임스페이스로서 빈 객체를 생성한다.
//이 단일 전역 심벌은 다른 심벌들을 가지고 있게 된다.
var Class = {};
//네임스페이스 안에서 함수를 정의한다.
Class.define = function(data){ /* code */ }
Class.provides = function(o, c){ /* code */ }</code></pre>
- 위 코드에는 모듈의 첫 번째 규칙인 '모듈은 전역 네임스페이스에 절대로 두 개 이상의 심벌을 추가해서는 안된다.'라는 것이 나타나 있다. 아래 목록은 이 규칙을 보강하는데 좋다고 알려진 생각이다.
  - 만약 모듈이 전역 네임스페이스에 심벌을 추가한다면, 문서에 그 심벌이 무엇인지 명확하게 기술되어야 한다.
  - 만약 모듈이 전역네임스페이스에 심벌을 추가한다면, 그 심벌의 이름과 모듈이 작성되어 있는 파일 이름 간에 명확한 관계가 있어야 한다.
- 클래스 모듈이라면 Class.js라는 파일에 코드를 집어넣고 파일 상단에 아래와 같이 주석을 넣을 수 있다.
<pre><code>/**
* Class.js : 클래스와 함께 작동하기 위한 유틸리티 함수의 모듈
*
* 이 모듈은 'Class'라는 단일 전역 심벌을 정의
* Class는 네임스페이스 객체를 참조하며,
* 모든 유틸리티 함수는 이 네임스페이스의 프로퍼티로 저장된다.
**/</code></pre>

269
