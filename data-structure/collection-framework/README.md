---
description: '출처 : 명품 자바 에센셜(황기태)'
---

# Collection Framework

Java의 JDK는 프로그램 개발에 필요한 기초적인 자료 구조들을 거의 대부분 컬션\(collection\)으로 만들어 제공한다. 배열은 여러 개의 데이터를 다루는 데 매우 편리한 자료 구조이지만, 삽입/삭제가 빈번하고, 데이터의 크기를 예측할 수 없는 응용프로그램에 사용하기에 불편하다.

### 컬렉션

서로 연관성 있는 객체들을 그룹화하여 다량의 데이터를 쉽게 처리할 수 있도록 제공하는 자료구조의 개념이 적용된 API이다.  

컬렉션은 고정 크기의 배열이 가지는 단점을 극복하고, 요소\(element\)라고 불리는 객체들의 삽입, 삭제, 검색 기능을 갖춘 가변 크기의 컨테이너\(container\)이다. 

### 컬렉션 인터페이스와 클래스 

![Collection Framwork](../../.gitbook/assets/1.png)

#### Set 계열

* 동일한 데이터를 중복해서 저장할 수 없다. 동일한 데이터를 여러 번 저장해도 하나로 인식한다. 
* 데이터를 저장한 순서를 기억하지 않는다. 저장 순서로 데이터를 검색해야 할 때는 사용할 수 없다. 
* HashSet, LinkedHashSet, TreeSet 
* LinkedHashSet 클래스는 저장 순서를 기억하게 되어 있다. 
* SortedSet 계열은 정렬, 처음/끝 데이터, 상하 관계 등을 관리하는 method가 있다.

#### List 계열 

* 동일한 데이터를 저장할 수 있다.
* 인덱스를 사용하여 데이터를 차례로 저장한다. 저장 순서를 알 수 있으며 특정 위치에 대해 데이터를 추출하거나 삽입할 수 있다.
* Vector, ArrayList, LinkedList

#### Map 계열

* key와 value의 조합으로 데이터를 저장한다.
* 값으로는 동일한 데이터를 저장할 수 있지만, 키는 유일해야 한다.
* 데이터를 저장한 순서를 기억하지 않는다.
* Hashtable, HashMap, LinkedHashMap, TreeMap
* LinkedHashMap 클래스는 저장 순서를 기억하게 되어 있다.
* SortedMap 계열은 정렬, 처음/끝 데이터, 상하 관계 등을 관리하는 method가 있다.  

#### 기타 계열

* Queue 계열: 일반적으로 FIFO 방식으로 다량의 데이터를 관리하며, 데이터 추출 전에 Queue에 추가와 검사가 가능하다. 
* Deque 계열: FIFO 방식과 LIFO 방식을 모두 사용할 수 있다. 데이터 추출 전에 Deque의 앞쪽이나 뒤쪽 어디든 데이터를 추가할 수 있다. 

<table>
  <thead>
    <tr>
      <th style="text-align:left">List</th>
      <th style="text-align:left">Set</th>
      <th style="text-align:left">Map</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#xC21C;&#xC11C;&#xAC00; &#xC788;&#xB294; &#xB370;&#xC774;&#xD130;&#xC758;
        &#xC9D1;&#xD569;, &#xB370;&#xC774;&#xD130;&#xC758; &#xC911;&#xBCF5;&#xC744;
        &#xD5C8;&#xC6A9;</td>
      <td style="text-align:left">&#xC21C;&#xC11C;&#xB97C; &#xC720;&#xC9C0;&#xD558;&#xC9C0; &#xC54A;&#xB294;
        &#xB370;&#xC774;&#xD130;&#xC758; &#xC9D1;&#xD569;, &#xB370;&#xC774;&#xD130;&#xC758;
        &#xC911;&#xBCF5;&#xC744; &#xD5C8;&#xC6A9;&#xD558;&#xC9C0; &#xC54A;&#xC74C;</td>
      <td
      style="text-align:left">
        <p>&#xD0A4;(key)&#xC640; &#xAC12;(value)&#xC758; &#xC30D;&#xC73C;&#xB85C;
          &#xC774;&#xB8E8;&#xC5B4;&#xC9C4; &#xB370;&#xC774;&#xD130;&#xC758; &#xC9D1;&#xD569;</p>
        <p>&#xC21C;&#xC11C;&#xB294; &#xC720;&#xC9C0;&#xB418;&#xC9C0; &#xC54A;&#xC73C;&#xBA70;
          &#xAC12;&#xC758; &#xC911;&#xBCF5;&#xC740; &#xD5C8;&#xC6A9;&#xB418;&#xC9C0;&#xB9CC;
          &#xD0A4;&#xC758; &#xC911;&#xBCF5;&#xC740; &#xD5C8;&#xC6A9;&#xD558;&#xC9C0;
          &#xC54A;&#xC74C;</p>
        </td>
    </tr>
    <tr>
      <td style="text-align:left">ArrayList, LinkedList, Stack, Vector...</td>
      <td style="text-align:left">HashSet, TreeSet, SortedSet...</td>
      <td style="text-align:left">HashMap, TreeMap, HashTable, LinkedHashMap, SortedMap, Properties...</td>
    </tr>
  </tbody>
</table>

### 컬렉션의 특징 

* 컬렉션은 제너릭\(generics\)이라는 기법으로 구현되어 있다. 클래스나 인터페이스에 &lt;E&gt;, &lt;K&gt;, &lt;V&gt;등으로 표현된 타입 매개 변수들이 있고 컬렉션의 요소를 일반화시킨 타입이다.
* 컬렉션의 요소는 객체들만 가능하다. int, char, double등의 기본 타입의 테이터는 컬렉션의 요소로 불가능하다.

### 

