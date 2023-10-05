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
