```
import java.util.Stack;
class Solution {
    boolean solution(String s) {
      boolean answer = true;

        Stack<String> st = new Stack<>();
        String[] arr = s.split("");
        
        for( int i=0; i<arr.length; i++){
            if(arr[i].equals("(")) st.push(arr[i]);
            else if(arr[i].equals(")")){
                if(st.isEmpty()) {return false;} 
                st.pop();
            }
        }
        return st.isEmpty();
    }
}
//split으로 문자열 반복문을 사용 할 경우, 효율성에서 통과하지 못하고, 자바 버전에 따라 문제가 생기기도 하니, charAt()을 사용하자!
//탐색할 때 String 보다 char 타입이 시간복잡도 측면에서 유리하다.
```
