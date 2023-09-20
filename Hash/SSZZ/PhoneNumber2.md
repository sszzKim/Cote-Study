```
package com.test.hash;

import java.util.*;

class PhoneNumber {
    public boolean solution(String[] phone_book) {
        
        //1.정렬
        Arrays.sort(phone_book);

        //2. HashMap 생성
        Map<String, Integer> map = new HashMap<>();
        for(String s :phone_book) map.put(s,0);
    
        //3. substr으로 key값이 있는지 비교하기
        //map.keySet() key값을 배열로 리턴
        //map.containsKey 이 함수를 써보자
        for( String s : map.keySet() ){
            for(int j=1; j<s.length();j++){
                if(map.containsKey(s.substring(0, j))) return false; //java.lang.String.substring(포함,불포함)
            }
        }

        boolean answer = true;
        return answer;
    }
    public static void main(String[] args) {
        PhoneNumber phoneNumber = new PhoneNumber();
        String[] phone_book = {"18","119", "97674223", "1195524421"};
        System.out.println(phoneNumber.solution(phone_book));
    }
}
/*
 정확성: 83.3
효율성: 16.7
합계: 100.0 / 100.0
 */
```
