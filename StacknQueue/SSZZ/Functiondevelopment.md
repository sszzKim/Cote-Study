```
package com.test.StacknQueue;

import java.util.ArrayList;
import java.util.LinkedList;
import java.util.List;
import java.util.Queue;

public class Functiondevelopment {

    public int[] solution(int[] progresses, int[] speeds) {
        /*
         * 문제: 날짜별 배포되는 프로그램 갯수를 출력 
         */
       
        // 진도율이 100%가 되는 날짜 계산
        Queue<Integer> que = new LinkedList<>();

        int[] ss = new int[3];

        for(int i=0; i<progresses.length; i++){
            int days_left = 100-progresses[i];
            if (0 != days_left%speeds[i]){ //나머지가 0이 아니면 하루를 더함
                que.add(days_left/speeds[i]+1);
            }else{
                que.add(days_left/speeds[i]);
            }
            //que.add((int)Math.ceil((100.0-progresses[i])/speeds[i]));    
        }

        List<Integer> list =  new ArrayList<>();

        // Queue 순서대로 첫번째 값보다 큰값이 나올 때까지 count를 올린다. 
        while(!que.isEmpty()){
            
            int peek = que.poll();//첫번째 값 삭제 후 값 리턴
            int cnt=1;
            
            while(!que.isEmpty() && peek>=que.peek()){
                que.poll(); //peek값보다 같거나 작으면 삭제
                cnt++;
            }

            list.add(cnt);                
        }


        int[] answer = list.stream().mapToInt(Integer::intValue).toArray();
        //Integer::intValue = Returns the value of this Integer as an int.
        return answer;
    }

    public static void main(String[] args) {
        Functiondevelopment ob = new Functiondevelopment();
        int[] as = ob.solution(new int[]{93, 30, 55}, new int[]{1, 30, 5});
        for(int i : as){
            System.out.print(i+" ");
        }
    }
}

``
