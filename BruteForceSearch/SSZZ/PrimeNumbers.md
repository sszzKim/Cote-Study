```
package com.test.bruteSearch;

import java.util.HashSet;
import java.util.Iterator;


public class PrimeNumbers {
    /*
     * 주어진 일의자리 숫자들로 조합할 수 있는 수 중에 소수의 개수를 리턴
     * 길이는 1이상 7이하
     */
    HashSet<Integer> numberSet = new HashSet<>(); //HashSet은 중복된 값을 허용하지 않는다, 순서가 보장되지 않는다.

    public void recursive1(String comb, String others){
        if(!comb.equals("")) numberSet.add(Integer.valueOf(comb));

        for(int i=0; i<others.length(); i++){
            recursive1(comb + others.charAt(i), others.substring(0, i) + others.substring(i+1)); //substring(0,0)은 아무것도 나오지 않는다.
        }
    }
    public int solution(String numbers) {
        
        recursive1("",numbers);

        int cnt=0;
        numberSet.remove(0);
        numberSet.remove(1);

        Iterator it = numberSet.iterator();

        while(it.hasNext()){
            int val = Integer.parseInt(it.next().toString());
            int sqrt = (int)Math.sqrt(val);
            //System.out.println("val, sqrt: "+val+" "+sqrt);
            for(int i=2; i<= sqrt; i++ ){
                if(val%i==0) {break;} //소수가 아니야
                if(i==sqrt){cnt++;}//
            }
        }
        
        int answer = cnt;
        return answer;
    }
    public static void main(String[] args) {
        PrimeNumbers ob = new PrimeNumbers();
        System.out.println("답: "+ob.solution("011"));
    }
}

```
