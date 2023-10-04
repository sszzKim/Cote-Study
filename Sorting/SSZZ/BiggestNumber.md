```
package com.test.sorting;

import java.util.Arrays;
import java.util.Comparator;

public class BiggestNumber {
    static public String solution(int[] numbers) {
        /*
         * 주어진 수를 나열하여 가장 큰 수를 반환한다.
         */

        String answerTemp = "";
        String[] transArr = Arrays.stream(numbers).mapToObj(String::valueOf).toArray(String[]::new);
        //Arrays.stream(numbers) return IntStream
        //IntStream.mapToObj: 원시타입 -> Wrapper 타입 / Object로 
        //Stream.toArray()=> <A> A[] toArray(IntFunction<A[]> generator)

        //내림차순 정렬 후
        //첫번째 char부터 비교해서 같으면 다시 비교
        //

        String answer = "";
        return answer;
    }
    public static void main(String[] args) {
        System.out.println(solution(new int[]{3, 30, 34, 5, 9}));
    }
}

```
