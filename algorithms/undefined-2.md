---
description: '내용 출처 : 위키 백과'
---

# 소수 구하기

## 에라토스테네스의 체 <a id="firstHeading"></a>

고대 그리스 수학자 에라토스테네스가 발견 소수를 구하는 방법이다.  

1. 2부터 소수를 구하고자 하는 구간의 모든 수를 나열한다. 
2. 2는 소수이므로 소수로 체크해준 후 2의 모든 배수를 지워준다.
3. 남아있는 수 가운데 가장 작은 3을 체크해준다.
4. 2와 같은 방법으로 3의 모든 배수를 지워준다.
5. 남아있는 수 가운데 가장 작은 5를 체크해준다.
6. 2와 같은 방법으로 5의 모든 배수를 지워준다.
7. 위와 같은 방법을 계속 해서 반복해준다.

해당 방법은 구하고자 하는 숫자 N의 제곱근까지만 구해줘도 모든 소수를 구할 수 있다.

```java
import java.util.ArrayList;
import java.util.Scanner;

public class primeNumber {
    public static void main(String[] args) {
    
        // ArrayList로 구현
        ArrayList<Boolean> primeList;

        // 사용자로부터의 콘솔 입력
        Scanner scan = new Scanner(System.in);
        int n = scan.nextInt();

        // n <= 1 일 때 종료
        if(n <= 1) return;

        // n+1만큼 할당
        primeList = new ArrayList<Boolean>(n+1);
        
        // 0번째와 1번째를 소수 아님으로 처리
        primeList.add(false);//0
        primeList.add(false);//1
        
        // 2~ n 까지 소수로 설정
        // true = 소수, false = 소수 아
        for(int i=2; i<=n; i++ )
            primeList.add(i, true);

        // 2 부터  ~ i*i <= n
        // 각각의 배수들을 지워간다.
        for(int i=2; (i*i)<=n; i++){
            if(primeList.get(i)){
                for(int j = i*i; j<=n; j+=i){
                    primeList.set(j, false);
                }
                //i*i 미만은 이미 처리되었으므로 j의 시작값은 i*i로 최적화할 수 있다.
            }
        }
        StringBuffer sb = new StringBuffer();
        sb.append("{");
        for(int i=0; i<=n; i++){
            if(primeList.get(i) == true){
                sb.append(i);
                sb.append(",");
            }
        }
        sb.setCharAt(sb.length()-1, '}');

        System.out.println(sb.toString());
    }
}
```











