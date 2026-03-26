<h2 id="java의-정석-4판-ch2-4-화면-입력과-출력---printf와-scanner">[Java의 정석 4판 ch2-4 화면 입력과 출력 - printf()와 Scanner</h2>
<h2 id="📌-한줄-요약">📌 한줄 요약</h2>
<blockquote>
<p><code>printf()</code>를 활용한 형식화된 문자열 출력 방법과 <code>Scanner</code>를 이용한 화면 콘솔 입력 처리 방법을 학습합니다.</p>
</blockquote>
<h2 id="🧐-배경--왜-배워야-하나">🧐 배경 &amp; 왜 배워야 하나</h2>
<ul>
<li><p><strong>이 개념이 필요한 이유</strong>: 단순한 <code>println()</code> 출력만으로는 소수점 자릿수를 제한하거나 문자열의 좌우 정렬을 원하는 대로 제어하기가 어렵습니다. 또한, 프로그램이 사용자와 상호작용하기 위해서는 키보드를 통한 입력이 필수적입니다.</p>
</li>
<li><p><strong>해결하는 문제</strong>: <code>printf()</code>의 형식 지시자(Format Specifier)를 사용하면 데이터의 출력 포맷을 자유롭게 지시할 수 있으며, <code>Scanner</code> 클래스를 통해 사용자가 입력한 문자열이나 숫자를 손쉽게 읽어 들일 수 있습니다.</p>
</li>
</ul>
<h2 id="🗂️-목차">🗂️ 목차</h2>
<ol>
<li><code>printf()</code>란? (형식화된 출력)</li>
<li>자주 쓰이는 형식 지시자 4가지</li>
<li>자릿수 지정 및 정렬 방법</li>
<li><code>Scanner</code>를 이용한 화면 입력</li>
</ol>
<hr />
<h2 id="📚-본문-정리">📚 본문 정리</h2>
<h3 id="1-printf란-형식화된-출력">1. <code>printf()</code>란? (형식화된 출력)</h3>
<p><code>println()</code>이 변수의 값을 있는 그대로 출력한다면, <code>printf()</code>에서 'f'는 <strong>Formatted(형식화된)</strong>를 의미합니다. 출력 형식을 우리가 원하는 대로 자유롭게 변환하여 화면에 보여줄 수 있는 강력한 메서드입니다.</p>
<ul>
<li><strong>주의사항</strong>: <code>printf()</code> 내부에 작성된 지시자의 개수와, 뒤에 따라오는 변수(값)의 개수는 <strong>반드시 일치</strong>해야 에러가 발생하지 않습니다.</li>
</ul>
<h3 id="2-자주-쓰이는-형식-지시자-4가지">2. 자주 쓰이는 형식 지시자 4가지</h3>
<p>모든 지시자를 외울 필요는 없으며, 가장 실무에서 많이 쓰이는 4가지만 기억하면 됩니다.</p>
<ul>
<li><strong><code>%d</code></strong> : 10진수 정수(Decimal)</li>
<li><strong><code>%f</code></strong> : 실수(Float)</li>
<li><strong><code>%c</code></strong> : 문자(Character)</li>
<li><strong><code>%s</code></strong> : 문자열(String)</li>
</ul>
<h3 id="3-자릿수-지정-및-정렬-방법">3. 자릿수 지정 및 정렬 방법</h3>
<p>지시자 사이에 숫자를 넣어 출력할 공간의 자릿수를 확보하거나 정렬 방향을 지시할 수 있습니다. 
특히 소수점이 있는 실수를 다룰 때 유용하게 쓰입니다. (단, 출력된 숫자는 연산이 아닌 단순 '문자열' 형태로 화면에 뿌려집니다)</p>
<pre><code class="language-java">double d = 1.23456789;
// %전체자릿수.소수점아래자릿수f
System.out.printf(&quot;%14.10f\n&quot;, d); // 전체 14자리 확보, 소수점 아래 10자리까지 출력
String str = &quot;Hello&quot;;
System.out.printf(&quot;%20s\n&quot;, str);  // 20자리 공간 확보 (기본 우측 정렬)
System.out.printf(&quot;%-20s\n&quot;, str); // 20자리 공간 확보 후 좌측(-) 정렬</code></pre>
<h3 id="4-scanner를-이용한-화면-입력">4. Scanner를 이용한 화면 입력</h3>
<p>자바에서 화면 입력을 받는 방법은 여러 가지가 있지만, 가장 편리하고 대중적인 것이 Scanner 클래스입니다.</p>
<pre><code class="language-java">import java.util.Scanner; // Scanner 사용을 위한 필수 선언

public class Main {
    public static void main(String[] args) {
        // 1. 시스템의 화면(System.in)으로부터 입력을 받을 Scanner 객체 생성
        Scanner scanner = new Scanner(System.in); 

        System.out.print(&quot;숫자를 입력하세요: &quot;);
        // 2. 사용자가 한 줄을 통째로 입력할 때까지 대기 (엔터를 치면 입력 종료)
        String input = scanner.nextLine(); 

        // 3. 입력받은 순수 '문자열'을 '정수(int)' 형태로 변환
        int num = Integer.parseInt(input); 

        // (참고) 문자를 정수로 바꾸는 과정을 생략하고 곧바로 정수로 입력받는 메서드도 있습니다.
        // int num2 = scanner.nextInt(); 
    }
}</code></pre>
<h3 id="💡-핵심-포인트-3가지">💡 핵심 포인트 3가지</h3>
<p>printf()는 <strong>지시자(%d, %f 등)</strong>를 사용하여 데이터의 자릿수나 정렬 등 출력 형식을 자유롭게 지정할 수 있습니다.</p>
<p>printf() 사용 시 지시자의 개수와 콤마(,) 뒤에 전달되는 값의 개수는 무조건 일치해야 합니다.</p>
<p>콘솔 화면에서 사용자의 입력을 받을 때는 <strong>Scanner 객체(new Scanner(System.in))</strong>를 생성하여 nextLine()이나 nextInt() 등을 활용합니다.</p>
<h3 id="🔗-참고-자료">🔗 참고 자료</h3>
<p>🎥 남궁성의 정석코딩 - <a href="https://youtu.be/LzQKnBpNESI?si=euXkw1V1esz4Oj4-">[Java의 정석 4판 2025] ch2-4 화면 입려과 출력 - printf()와 Scanner</a></p>
<p>📘 <a href="https://docs.oracle.com/javase/8/docs/api/java/util/Scanner.html">Oracle Java Documentation - Scanner</a></p>