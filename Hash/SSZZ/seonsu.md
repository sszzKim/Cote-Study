```
import java.util.Arrays;

class Solution {
    public String solution(String[] participant, String[] completion) {
        String answer = "";
        //1.두 배열을 정렬한다.
        Arrays.sort(participant);
        Arrays.sort(completion);
        
        //2.두 배열이 다를 때까지 찾는다.
        
        for(int i=0; i<completion.length; i++){
            if(!participant[i].equals(completion[i])) return participant[i];
        }
        //3.여기까지 왔다면, 마지막 주자가 완주하지 못한 선수다. 
        return participant[participant.length-1];
        
        
        /***** Other Solution *****
        int i=0;
        for(;i<completion.length; i++){
            if(!participant[i].equals(completion[i])) break;
        }
        return participant[i];
        
        채점 결과
        정확성: 58.3
        효율성: 33.3
        합계: 91.7 / 100.0
        
        */
        
    }
}
/*
정확성: 58.3
효율성: 33.3
합계: 91.7 / 100.0
*/
```
