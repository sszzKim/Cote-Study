```
package com.test.StacknQueue;

import java.util.Stack;

public class CorrectParentheses {
    boolean solution(String s) {
        /*
         * 문제: 괄호가 주어지고 연만큼 잘 닫았는지 체크 후
         * 올바른 괄호이면 true
         * 올바지 않다면 false 리턴
         */
        boolean answer = true;

        //")()(" 열렸으면 닫히면 되나
        // ((())((()))))
        // (((
        Stack<String> st = new Stack<>();
        String[] arr = s.split("");
        
        for( int i=0; i<arr.length; i++){
            
            if(i==0 && arr[0].equals(")")) {answer=false; break;} //첫번째가 ")"로 시작되면 정상값이 아니므로 false
            if(arr[i].equals("(")) st.push(arr[i]);
            else{
                if(st.size()==0) {answer=false; break;} 
                else st.pop();
            }
            
        }

        if(st.size()!=0) answer=false;

        return answer;
    }
    public static void main(String[] args) {
        CorrectParentheses correctParentheses = new CorrectParentheses();
        System.out.println(correctParentheses.solution("(()("));   
    }
}

```
