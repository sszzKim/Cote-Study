```
import java.util.*;
import java.util.stream.*;

class Solution {
    public int solution(int[] people, int limit) {
        List<Integer> list = Arrays.stream(people).boxed().collect(Collectors.toList());
        Collections.sort(list);

        int max=list.size()-1, min=0, cnt=0;

        while(min <= max){
            if(list.get(min)+list.get(max) <= limit){
                min++; max--;
                cnt++;
            }else{
                max--;
                cnt++;
            }
        }
        int answer = cnt;
        return answer;
    }
}
```
![캡처](/images/fail1024.JPG)
