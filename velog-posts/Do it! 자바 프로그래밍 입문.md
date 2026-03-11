<h3 id="03-자바의-여러-가지-연산자">03. 자바의 여러 가지 연산자</h3>
<ul>
<li>항과 연산자
: <strong>항</strong>은 표현식의 구성 요소로, 값이나 객체를 나타낸다. 자바에서 항은 다음과 같은 형태로 나뉜다.</li>
</ul>
<ol>
<li><p>리터럴(Literal): 직접 값을 나타내는 항이다.</p>
<p> 정수 리터럴: 5, 100
 실수 리터럴: 3.14, 2.718
 문자 리터럴: 'A', 'b'
 문자열 리터럴: &quot;Hello&quot;, &quot;World&quot;
 불리언 리터럴: true, false</p>
</li>
<li><p>변수(Variable): 값을 저장하는 공간으로, 값을 참조할 수 있다.</p>
<p> int x = 10;
 String name = &quot;Alice&quot;;
 상수(Constant): 한 번 값이 설정되면 변경되지 않는 변수입니다. 자바에서는 final 키워드로 정의한다.
 final int MAX_VALUE = 100;</p>
</li>
<li><p>객체(Object): 클래스의 인스턴스로, 클래스의 구조체를 통해 생성된다.
 Person person = new Person();</p>
</li>
</ol>
<p><strong>연산자 **
: **연산자</strong>는 항을 대상으로 연산을 수행하는 기호나 키워드이다. 자바에서 제공하는 연산자는 다음과 같이 분류된다.</p>
<ol>
<li><p>산술 연산자(Arithmetic Operators): 기본적인 산술 연산을 수행합니다.</p>
<p> 덧셈: +
 뺄셈: -
 곱셈: *
 나눗셈: /
 나머지: %</p>
<pre><code>int a = 10;
int b = 5;
int sum = a + b; // 15
int difference = a - b; // 5
int product = a * b; // 50
int quotient = a / b; // 2
int remainder = a % b; // 0
</code></pre></li>
</ol>
<pre><code>
2. 비교 연산자(Relational Operators): 두 항을 비교하여 관계를 평가합니다.

    같음: ==
    같지 않음: !=
    큼: &gt;
    작음: &lt;
    크거나 같음: &gt;=
    작거나 같음: &lt;=
</code></pre><p>int a = 10;
int b = 5;
boolean isEqual = (a == b); // false
boolean isNotEqual = (a != b); // true
boolean isGreater = (a &gt; b); // true
boolean isLess = (a &lt; b); // false
boolean isGreaterOrEqual = (a &gt;= b); // true
boolean isLessOrEqual = (a &lt;= b); // false</p>
<pre><code>
3. 논리 연산자(Logical Operators): 논리 값을 결합하여 논리식을 구성합니다.

    논리 AND: &amp;&amp;
    논리 OR: ||
    논리 NOT: !
</code></pre><p>boolean a = true;
boolean b = false;
boolean andResult = a &amp;&amp; b; // false
boolean orResult = a || b; // true
boolean notResult = !a; // false</p>
<pre><code>4. 대입 연산자(Assignment Operators): 값을 변수에 대입합니다.

    대입: =
    더해서 대입: +=
    빼서 대입: -=
    곱해서 대입: *=
    나누어서 대입: /=
    나머지를 대입: %=
</code></pre><p>int x = 10;
x += 5; // x = x + 5; -&gt; x는 15
x -= 3; // x = x - 3; -&gt; x는 12
x *= 2; // x = x * 2; -&gt; x는 24
x /= 4; // x = x / 4; -&gt; x는 6
x %= 5; // x = x % 5; -&gt; x는 1</p>
<pre><code>
5. 비트 연산자(Bitwise Operators): 비트 단위로 연산을 수행합니다.

    비트 AND: &amp;
    비트 OR: |
    비트 XOR: ^
    비트 NOT: ~
    왼쪽 시프트: &lt;&lt;
    오른쪽 시프트: &gt;&gt;
    부호 없는 오른쪽 시프트: &gt;&gt;&gt;
</code></pre><p>int a = 5; // 0101 in binary
int b = 3; // 0011 in binary
int andResult = a &amp; b; // 0001 in binary, 1 in decimal
int orResult = a | b; // 0111 in binary, 7 in decimal
int xorResult = a ^ b; // 0110 in binary, 6 in decimal
int notResult = ~a; // 1010 in binary (2's complement), -6 in decimal
int leftShift = a &lt;&lt; 1; // 1010 in binary, 10 in decimal
int rightShift = a &gt;&gt; 1; // 0010 in binary, 2 in decimal
int unsignedRightShift = a &gt;&gt;&gt; 1; // 0010 in binary, 2 in decimal</p>
<pre><code>
6. 기타 연산자:

    삼항 연산자: 조건 ? 값1 : 값2
    인스턴스 확인: instanceof
    메서드 참조: ::
</code></pre><p>int a = 10;
int b = 20;
int max = (a &gt; b) ? a : b; // 20</p>
<p>String str = &quot;Hello&quot;;
boolean isString = str instanceof String; // true</p>
<pre><code>이러한 항과 연산자를 통해 자바에서 다양한 표현식과 로직을 구성할 수 있다.</code></pre>