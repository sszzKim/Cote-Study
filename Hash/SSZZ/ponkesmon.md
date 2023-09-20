```
package com.test.hash;

import java.util.HashMap;
import java.util.Map;

public class Ponkesmon {

    public int solution(int[] nums) {
        //0.문제 단순화
        //가져갈 수 있는 폰켓몬의 종류의 가지수를 구하는 것
        //N개의 폰켓몬이 있을 때 N/2까지 가질 수 있다.
        //다만 폰켓몬 종류가 중복되어 있을 수 있다.

        //1. 단순하게 N/2 최대값 구하기
        int max1 = nums.length/2;

        //2. 해쉬리스트 생성 후 종류 갯수를 구한다.
        Map<String,Integer> map = new HashMap<>();
        for(int i : nums){
            String key = Integer.toString(i);
            if(map.containsKey(key)) map.put(key, map.getOrDefault(key,0)+1);
            else map.put(key,1);
        }


        //3. 해쉬 Key값(종류)이 N/2보다 작을 경우 해당 값을 리턴한다.
        int answer =  (max1 > map.size()) ?  map.size() : max1;
        return answer;

    }

    public static void main(String[] args) {
        int[] nums = {3,3,3,2,2,2};
        Ponkesmon pk = new Ponkesmon();
        System.out.println(pk.solution(nums));
    }
    
}

```
