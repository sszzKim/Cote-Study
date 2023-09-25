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

```
