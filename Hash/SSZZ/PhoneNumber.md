```
package com.test.hash;

import java.util.*;

class PhoneNumber {
    public boolean solution(String[] phone_book) {
        
        //배열 소팅
        Arrays.sort(phone_book);

        //배열을 하나씩 꺼내서 비교 접두어인지 확인
        for(int i=0; i<phone_book.length-1; i++){
            if(phone_book[i+1].startsWith(phone_book[i])) return true;
        }

        boolean answer = false;
        return answer;
    }
    public static void main(String[] args) {
        PhoneNumber phoneNumber = new PhoneNumber();
        String[] phone_book = {"119", "97674223", "1195524421"};
        System.out.println(phoneNumber.solution(phone_book));
    }
}
/*
채점 결과
정확성: 83.3
효율성: 16.7
합계: 100.0 / 100.0
*/

```
