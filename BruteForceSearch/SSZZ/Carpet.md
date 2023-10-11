```
package com.test.bruteSearch;

import java.util.Arrays;

public class Carpet {
    static public int[] solution(int brown, int yellow) {
        /*
         * 갈색은 노란색 블록 테두리를 1줄 씩 둘러싸고 있는 블록임
         * 주어진 갈색과 노란색 블록으로 만든 직사각형 가로, 세로 길이를 리턴한다.
         */
        int tempBrown, i=1;      
        brown=brown-4; // 각 모서리 꼭지점을 제외
        
        while(true){
            tempBrown=brown-(i*2); //i는 yellow의 세로길이
            //yellow가 int형이기 때문에 몫만 나오기 때문에 나머지 연산자 동시에 걸어둠
            if(tempBrown/2 == yellow/i && yellow%i==0) break;     
            i++;
        }

        int[] answer = {yellow/i+2, i+2};
        return answer;
    }
    public static void main(String[] args) {
        System.out.println(Arrays.toString(solution(26,30)));
        //System.out.println(30/4);
    }
}

```
