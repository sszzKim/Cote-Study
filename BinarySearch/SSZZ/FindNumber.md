```
package com.test.BinarySearch;

import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.Arrays;

public class FindNumber {
    //public class Main {

    public static int solution(int[] intAAry, int left, int right, int target ){
        if(left <= right){
            //int mid = (right-left)/2+left;
            int mid = (right+left)/2;
            //System.out.println("mid: "+mid+"target: "+target+"ary[mid]: "+intAAry[mid]+"left:"+left+"right:"+right);
            if(target < intAAry[mid]){ //찾는 값이 작으면
                return solution(intAAry, left, mid-1, target);
            } 
            else if(target > intAAry[mid]){ //찾는 값이 크면
                return solution(intAAry, mid+1, right, target);
            }
            //값이 같으면
            return 1;
        }else{
            return 0;
        }
    }


    public static void main(String[] args) throws Exception {
    
        //바이너리 트리 
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

        int N = Integer.parseInt(br.readLine());
        //스트림변환 -> int로 변환 -> 배열로 다시 변환
        int[] intAAry = Arrays.stream(br.readLine().split(" ")).mapToInt(Integer::parseInt).toArray();
        int M = Integer.parseInt(br.readLine());
        int[] intMAry = Arrays.stream(br.readLine().split(" ")).mapToInt(Integer::parseInt).toArray();
        
    
        //오름차순 정렬
        Arrays.sort(intAAry);
        //System.out.println(Arrays.toString(intAAry));

        //System.out.println(Arrays.toString(intAAry));
        //System.out.println(Arrays.toString(intMAry));

        for(int i :intMAry){
            //System.out.println("i: "+i);
            System.out.println(solution(intAAry,0,intAAry.length-1,i));
            //solution(intAAry,0,intAAry.length-1,i);
        }        
    }
    
}

```
