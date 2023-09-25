import java.util.*;
class Solution {
    boolean solution(String s) {
       
        Stack<Character> stack = new Stack<>();
       
        
        for(char ch : s.toCharArray()) {            // toCharArray를 이용해 문자형으로 변환
            
            if(ch =='(') {
                stack.push(ch);                           
            }
            else if(ch ==')') {
                if(stack.isEmpty()) {                       // stack이 빼기도 전에 빈 경우이면 
                    return false;                               // ) 가 더 많은 경우이므로 false
                }
                stack.pop();
            }
        }
            
      

        return stack.isEmpty();              // 다 끝나고 난 후에는 비어있어야 true ( 개수 짝이 맞아야함)
         }
    }
