```
package com.test.sorting;

import java.util.Arrays;
import java.util.Comparator;

public class BiggestNumber {
    static public String solution(int[] numbers) {
        /*
         * 주어진 수를 나열하여 가장 큰 수를 반환한다.
         */
        String answer = "";
        // 문자열 배열로 변환
        String[] number = Arrays.stream(numbers).mapToObj(String::valueOf).toArray(String[]::new);
        
        // 내림차순 정렬
        Arrays.sort(number, new Comparator<String>(){
            public int compare(String a, String b){
                return (b+a).compareTo(a+b);
            }
        });
        // 정렬에서, x.compareTo(y)의 리턴값이 음수라면, x가 y보다 앞에 온다는 의미가 됩니다. 양수라면 x가 y보다 뒤에 온다는 것이고 0이면, 어떤 정렬이냐에 따라서 앞에 오는지, 뒤에 오는지가 달라집니다.
        
        // 배열에 0 만 있는 경우(정렬배열 맨처음이 0) "0" 리턴
        if(number[0].equals("0")) return "0";
        
        // 문자열 합치기
        for(String n : number)
            answer+=n;
        return answer;
    }
    public static void main(String[] args) {
        System.out.println(solution(new int[]{3, 30, 34, 5, 9}));
    }
}

```
