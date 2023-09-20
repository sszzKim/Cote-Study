<a href="https://www.notion.so/Cote-HashMap-54f61a71ca2347619628ef094c0cd53d?pvs=4" target="_blank"> https://www.notion.so/Cote-HashMap-54f61a71ca2347619628ef094c0cd53d?pvs=4 </a>

```
import java.util.HashMap;

class Solution {
    public String solution(String[] participant, String[] completion) {
        String answer = "";
        
        //1. Hash map을 만든다.(Participant)
        HashMap<String, Integer> map = new HashMap<>();
        for(String player : participant){
            map.put(player, map.getOrDefault(player,0) + 1);
        }
        //2. Hash map을 뺀다.(completion)
        for(String player:completion){
            map.put(player, map.get(player)- 1);
        }
        //3. Value가 0이 아닌 마지막 주자를 찾는다.
        for(String key : map.keySet()){
            if(map.get(key) !=0 ){
                answer = key;
                break;
            }
        }
        
        return answer;
        
        
        /***** Other Solution ***** 
        
        Iterator<Map.Entry<String,Integer>> iter = map.entrySet().iterator();

        while(iter.hasNext()){
            Map.Entry<String, Integer> entry = iter.next();
            if(entry.getValue() !=0 ){
                answer = entry.getKey();
                break;
            }
        }
        */
        
    }
}
/*
정확성: 58.3
효율성: 41.7
합계: 100.0 / 100.0
*/
```
