```
package com.test.sorting;

import java.util.*;

public class KthNumber {
    static public int[] solution(int[] array, int[][] commands) {
        /*
         * 첫번째 파라미터인 배열에서
         * 두번째 파라미터 배열의 첫번째 원소부터 두번째 원소까지 잘랐을 때
         * 세번째 원소 자리에 있는 수를 리턴한다.
         */
        int[] answer = new int[commands.length];
        int i,j,k=0;

        List<Integer> list = new LinkedList<>();

        for(int a=0; a<commands.length; a++){
            i=commands[a][0]-1;
            j=commands[a][1]-1; 
            k=commands[a][2]-1; 
            for(i=i; i<=j; i++) list.add(array[i]);
            Collections.sort(list);
            answer[a]=list.get(k);
            list.clear();
        }
        return answer;
    }
    public static void main(String[] args) {
        System.out.println(Arrays.toString(solution(new int[]{1, 5, 2, 6, 3, 7, 4}, new int[][]{{2, 5, 3}, {4, 4, 1}, {1, 7, 3}})));
        
    }
}

```
