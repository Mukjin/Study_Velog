<h1 id="java의-정석-4판-ch2-3-상수와-리터럴">[Java의 정석 4판] ch2-3 상수와 리터럴]</h1>
<h2 id="📌-한줄-요약">📌 한줄 요약</h2>
<blockquote>
<p>자바의 <strong>상수</strong>와 <strong>리터럴</strong>의 개념을 명확히 구분하고, 값의 타입에 따른 <strong>접미사</strong> 규칙, 그리고 직관적인 다중 문자열 처리를 위한 최신 문법인 <strong>텍스트 블록(Text Block)</strong>의 활용법을 학습합니다.</p>
</blockquote>
<h2 id="🧐-배경--왜-배워야-하나">🧐 배경 &amp; 왜 배워야 하나</h2>
<ul>
<li><strong>이 개념이 필요한 이유</strong>: 파이(π)나 최댓값처럼 프로그램이 실행되는 동안 절대로 변하면 안 되는 값들이 있습니다. 이러한 값들을 변수에 실수로 덮어쓰는 것을 방지하기 위해 상수를 사용합니다.</li>
<li><strong>해결하는 문제</strong>: 자바는 타입이 매우 엄격한 언어입니다. 우리가 입력하는 단순한 숫자(리터럴) 하나에도 모두 타입이 존재하며, 이를 컴파일러에게 정확히 알려주기 위해 접미사 규칙을 알아야 에러 없는 안정적인 코드를 작성할 수 있습니다.</li>
</ul>
<h2 id="🗂️-목차">🗂️ 목차</h2>
<ol>
<li>상수(Constant)와 리터럴(Literal)</li>
<li>값의 타입과 접미사 (Suffix)</li>
<li>문자(char)와 문자열(String)의 차이</li>
<li>문자열 결합의 원리</li>
<li>텍스트 블록 (Text Block)</li>
</ol>
<hr />
<h2 id="📚-본문-정리">📚 본문 정리</h2>
<h3 id="1-상수constant와-리터럴literal">1. 상수(Constant)와 리터럴(Literal)</h3>
<ul>
<li><strong>상수(Constant)</strong>: 변수와 동일하게 값을 담는 저장 공간이지만, <strong>한 번만 값을 저장할 수 있는 공간</strong>입니다. 변수 선언 시 앞에 <code>final</code> 키워드를 붙여서 만들며, 관습적으로 이름은 모두 <strong>대문자</strong>로 작성합니다. </li>
<li><strong>리터럴(Literal)</strong>: <code>100</code>, <code>3.14</code>, <code>'A'</code>와 같이 <strong>그 자체로 값을 의미하는 것</strong>을 말합니다. 우리가 수학이나 일상에서 흔히 '상수'라고 부르는 고정된 값들을 프로그래밍에서는 리터럴이라고 부릅니다.</li>
</ul>
<pre><code class="language-java">int score = 100; // score: 변수, 100: 리터럴
final int MAX_VALUE = 200; // MAX_VALUE: 상수, 200: 리터럴
// MAX_VALUE = 300; // ❌ 에러 발생: 상수는 값을 변경할 수 없음</code></pre>
<h3 id="2-값의-타입과-접미사-suffix">2. 값의 타입과 접미사 (Suffix)</h3>
<p><strong>모든 값(리터럴)에는 타입이 있습니다.</strong> 값만 덩그러니 있으면 그것이 어떤 타입인지 명확하지 않기 때문에, 값 뒤에 <strong>접미사</strong>를 붙여 타입을 명시해야 합니다.</p>
<ul>
<li><strong>정수형</strong>: 접미사가 없으면 기본적으로 <code>int</code> 타입입니다. 더 큰 숫자를 다루는 <code>long</code> 타입의 경우 값 뒤에 <strong><code>L</code></strong>을 붙입니다. (소문자 <code>l</code>은 숫자 <code>1</code>과 헷갈리므로 반드시 대문자 <code>L</code>을 권장합니다)</li>
<li><strong>실수형</strong>: 기본 타입은 <code>double</code>이며 접미사 <code>d</code> 또는 <code>D</code>는 생략 가능합니다. 반면, <code>float</code> 타입의 경우 반드시 <strong><code>f</code></strong> 또는 <strong><code>F</code></strong> 접미사를 붙여야 합니다.</li>
</ul>
<pre><code class="language-java">long bigNum = 10000000000L; // L 접미사 필수
float pi = 3.14f;           // f 접미사 필수
double rate = 1.618;        // d 생략 가능 (1.618d 와 동일)</code></pre>
<h3 id="3-문자char와-문자열string의-차이">3. 문자(char)와 문자열(String)의 차이</h3>
<ul>
<li><strong>문자 (<code>char</code>)</strong>: 기본형 타입이며, 홑따옴표 <code>''</code>를 사용합니다. <strong>반드시 단 1개의 문자</strong>가 들어있어야 합니다. 공백 문자는 허용되지만 아예 비워두는 것(빈 문자)은 불가능합니다.</li>
<li><strong>문자열 (<code>String</code>)</strong>: 참조형 타입이며, 쌍따옴표 <code>&quot;&quot;</code>를 사용합니다. 문자의 집합(그룹)이므로 0개 이상의 문자를 담을 수 있어 아예 비워두는 <strong>빈 문자열(<code>&quot;&quot;</code>)</strong>도 허용됩니다.</li>
</ul>
<h3 id="4-문자열-결합의-원리">4. 문자열 결합의 원리</h3>
<p>어떤 타입이든 문자열(<code>String</code>)과 덧셈(<code>+</code>) 연산을 하면 <strong>그 결과는 무조건 문자열</strong>이 됩니다. 이는 수학적인 덧셈이 아니라 두 요소가 합쳐지는 <strong>합집합(Concatenation)</strong>의 개념으로 이해하면 쉽습니다.</p>
<pre><code class="language-java">System.out.println(7 + &quot;&quot;);       // &quot;7&quot; (숫자가 문자열로 변환됨) [00:08:45]
System.out.println(&quot;&quot; + 7 + 7);   // &quot;77&quot; (앞에서부터 차례대로 결합) [00:10:43]
System.out.println(7 + 7 + &quot;&quot;);   // &quot;14&quot; (숫자 7+7이 먼저 계산된 후 문자열과 결합) [00:10:13]</code></pre>
<h3 id="5-텍스트-블록-text-block">5. 텍스트 블록 (Text Block)</h3>
<p>JDK 15부터 도입된 아주 유용한 기능으로, 큰따옴표 3개 <code>&quot;&quot;&quot;</code>를 사용하여 여러 줄의 문자열을 눈에 보이는 형태 그대로 작성할 수 있습니다.</p>
<ul>
<li><strong>주의사항 1</strong>: 시작하는 <code>&quot;&quot;&quot;</code> 바로 옆에는 문자가 오면 안 되고 <strong>반드시 줄바꿈</strong>을 해야 합니다.</li>
<li><strong>주의사항 2</strong>: 닫는 <code>&quot;&quot;&quot;</code>의 위치가 <strong>들여쓰기(공백)의 기준점</strong>이 됩니다. 닫는 따옴표를 왼쪽으로 당기면 그만큼 문자열 앞쪽에 공백이 포함되어 출력됩니다.</li>
</ul>
<pre><code class="language-java">// 기존 방식 (줄바꿈과 이스케이프 문자로 인해 지저분함)
String oldStr = &quot;Hello\n&quot; +
                &quot;World\n&quot;;

// 텍스트 블록 활용 (입력한 형태 그대로 문자열 생성)
String textBlock = &quot;&quot;&quot;
        Hello
        World
        &quot;&quot;&quot;; // 닫는 위치에 따라 들여쓰기가 결정됨</code></pre>
<hr />
<h2 id="💡-핵심-포인트-3가지">💡 핵심 포인트 3가지</h2>
<ol>
<li><strong>상수(<code>final</code>)</strong>는 단 한 번만 값을 저장할 수 있는 공간이며, <strong>리터럴</strong>은 그 저장되는 실제 값 자체를 의미합니다.</li>
<li>모든 리터럴에는 타입이 존재하며, <strong><code>long</code> 타입은 <code>L</code></strong>, <strong><code>float</code> 타입은 <code>f</code></strong> 접미사를 반드시 붙여주어야 오류가 발생하지 않습니다.</li>
<li>여러 줄의 복잡한 문자열을 다룰 때는 기존의 덧셈 방식보다 JDK 15의 <strong>텍스트 블록(<code>&quot;&quot;&quot;</code>)</strong>을 활용하면 코드 가독성이 획기적으로 높아집니다.</li>
</ol>
<h2 id="🔗-참고-자료">🔗 참고 자료</h2>
<ul>
<li>🎥 <a href="http://www.youtube.com/watch?v=REBhttvufUc">남궁성의 정석코딩 - [Java의 정석 4판 2025] ch2-3 상수와 리터럴</a></li>
<li>📘 <a href="https://docs.oracle.com/en/java/javase/15/text-blocks/index.html">Oracle Java Documentation - Text Blocks</a></li>
</ul>