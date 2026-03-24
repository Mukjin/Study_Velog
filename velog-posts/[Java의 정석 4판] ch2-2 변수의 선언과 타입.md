<h1 id="java의-정석-4판-ch2-2-변수의-선언과-타입">[Java의 정석 4판] ch2-2 변수의 선언과 타입</h1>
<h2 id="📌-한줄-요약">📌 한줄 요약</h2>
<blockquote>
<p>자바에서 변수를 선언하는 방법과 명명 규칙을 익히고, 단일 값을 저장하는 <strong>8가지 기본형(Primitive Type)</strong>과 <strong>참조형(Reference Type)</strong>의 차이를 이해합니다.</p>
</blockquote>
<h2 id="🧐-배경--왜-배워야-하나">🧐 배경 &amp; 왜 배워야 하나</h2>
<ul>
<li><strong>이 개념이 필요한 이유</strong>: 변수는 데이터를 담는 '그릇'입니다. 밥그릇에 밥을, 국그릇에 국을 담듯, 우리가 다루려는 데이터의 형태(정수, 실수, 문자, 논리값 등)에 따라 알맞은 모양과 크기의 메모리 공간(타입)을 지정해 주어야 합니다.</li>
<li><strong>해결하는 문제</strong>: 자바의 엄격한 타입 체계를 이해하면 메모리 낭비를 막을 수 있으며, 타입 불일치로 인한 컴파일 에러를 사전에 방지하여 안정적인 애플리케이션을 개발할 수 있습니다.</li>
</ul>
<h2 id="🗂️-목차">🗂️ 목차</h2>
<ol>
<li>변수의 선언과 타입 추론(<code>var</code>)</li>
<li>변수 이름 명명 규칙 (Naming Rules)</li>
<li>변수의 타입: 기본형 vs 참조형</li>
<li>자바의 8가지 기본형 (Primitive Type)</li>
</ol>
<hr />
<h2 id="📚-본문-정리">📚 본문 정리</h2>
<h3 id="1-변수의-선언과-타입-추론var">1. 변수의 선언과 타입 추론(<code>var</code>)</h3>
<p>변수를 만들기(선언) 위해서는 반드시 <strong>변수의 타입(Type)</strong>과 <strong>변수의 이름(Name)</strong>을 적어주어야 합니다. 변수 이름은 수많은 메모리 공간 중 특정 공간을 식별하기 위해 필요하며, 의미 있고 알기 쉬운 이름으로 짓는 것이 좋습니다.</p>
<p><strong>💡 타입 추론 (JDK 10+ 추가 기능)</strong>
최신 자바에서는 변수의 타입을 직접 명시하지 않고 <code>var</code> 키워드를 사용할 수 있습니다.</p>
<pre><code class="language-java">int a = 10; // 기존 방식: 정수를 담을 변수라고 직접 명시
var b = 10; // 타입 추론: 대입되는 값(10)을 보고 컴파일러가 알아서 int형으로 짐작(추론)함</code></pre>
<h3 id="2-변수-이름-명명-규칙-naming-rules">2. 변수 이름 명명 규칙 (Naming Rules)</h3>
<p>변수 이름을 지을 때는 자바의 문법적 규칙을 반드시 따라야 합니다.</p>
<ul>
<li><strong>대소문자 구별</strong>: <code>True</code>와 <code>true</code>는 완전히 다른 변수로 인식됩니다.</li>
<li><strong>예약어(Keyword) 사용 불가</strong>: <code>if</code>, <code>for</code>, <code>static</code> 등 자바 문법에서 이미 사용 중인 단어는 변수명으로 쓸 수 없습니다.</li>
<li><strong>숫자로 시작 불가</strong>: <code>7up</code>처럼 숫자가 맨 앞에 올 수 없습니다.</li>
<li><strong>특수문자 제한</strong>: 언더바(<code>_</code>)와 달러 기호(<code>$</code>) 두 가지만 허용됩니다.</li>
</ul>
<h3 id="3-변수의-타입-기본형-vs-참조형">3. 변수의 타입: 기본형 vs 참조형</h3>
<p>자바의 데이터 타입은 크게 두 가지로 나뉩니다.</p>
<ul>
<li><p><strong>기본형 (Primitive Type)</strong></p>
<ul>
<li>자바에서 기본적으로 제공하는 타입입니다.</li>
<li>오직 <strong>단 1개의 실제 값</strong>만 저장할 수 있습니다.</li>
<li>총 <strong>8개</strong>로 개수가 고정되어 있습니다.</li>
</ul>
</li>
<li><p><strong>참조형 (Reference Type)</strong></p>
<ul>
<li>여러 개의 값을 묶어서 다루기 위한 타입(객체, 그룹)입니다.</li>
<li>실제 값이 아닌, 데이터가 저장된 메모리의 <strong>주소</strong>를 저장합니다.</li>
<li>사용자가 직접 클래스를 만들어 추가할 수 있으므로 개수가 <strong>무한대</strong>입니다.</li>
<li><em>예: 여러 문자를 묶어서 저장하는 <code>String</code>은 기본형이 아닌 참조형입니다.</em></li>
</ul>
</li>
</ul>
<h3 id="4-자바의-8가지-기본형-primitive-type">4. 자바의 8가지 기본형 (Primitive Type)</h3>
<p>기본형 8가지는 메모리 크기(Byte)와 담는 데이터의 종류에 따라 분류됩니다. <strong>(★표시는 각 계열의 기본 타입입니다)</strong></p>
<ul>
<li><strong>논리형 (1 byte)</strong>: 참(<code>true</code>)과 거짓(<code>false</code>)만 저장. (조건식에 주로 사용)<ul>
<li><code>boolean</code></li>
</ul>
</li>
<li><strong>문자형 (2 byte)</strong>: 단 하나의 문자만 저장. (예: 'A', '가')<ul>
<li><code>char</code></li>
</ul>
</li>
<li><strong>정수형</strong>: 정수 숫자를 저장.<ul>
<li><code>byte</code> (1 byte)</li>
<li><code>short</code> (2 byte)</li>
<li><strong><code>int</code> (4 byte) ★</strong> : 정수형의 가장 기본 타입 (약 20억까지 표현 가능)</li>
<li><code>long</code> (8 byte) : <code>int</code>보다 훨씬 큰 숫자를 다룰 때 사용</li>
</ul>
</li>
<li><strong>실수형</strong>: 소수점이 있는 숫자를 저장.<ul>
<li><code>float</code> (4 byte)</li>
<li><strong><code>double</code> (8 byte) ★</strong> : 실수형의 기본 타입 (오차가 적어 더 정밀함)</li>
</ul>
</li>
</ul>
<blockquote>
<p><strong>실습 꿀팁</strong>: 코드를 단순히 따라 치는 것에 그치지 말고, <code>char</code>에 문자를 여러 개 넣어보거나, <code>int</code> 범위를 넘는 숫자를 넣어보는 등 일부러 에러를 내보고 왜 안 되는지 경험해 보는 것이 실력 향상에 큰 도움이 됩니다!</p>
</blockquote>
<hr />
<h2 id="💡-핵심-포인트-3가지">💡 핵심 포인트 3가지</h2>
<ol>
<li>변수를 선언할 때는 밥그릇, 국그릇을 고르듯 저장할 데이터에 맞는 <strong>타입(Type)</strong>을 지정해야 합니다.</li>
<li>자바의 타입은 1개의 실제 값을 저장하는 8가지 <strong>기본형</strong>과, 여러 값을 묶어서 다루며 주소를 저장하는 <strong>참조형</strong>으로 나뉩니다.</li>
<li>정수형의 기본 타입은 <strong><code>int</code></strong> (4바이트)이며, 실수형의 기본 타입은 오차가 적은 <strong><code>double</code></strong> (8바이트)입니다.</li>
</ol>
<h2 id="🔗-참고-자료">🔗 참고 자료</h2>
<ul>
<li>🎥 <a href="https://youtu.be/Nz-9FPkARcU">남궁성의 정석코딩 - [Java의 정석 4판 2025] ch2-2 변수의 선언과 타입</a></li>
<li>📘 <a href="https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html">Oracle Java Tutorials - Primitive Data Types</a></li>
</ul>