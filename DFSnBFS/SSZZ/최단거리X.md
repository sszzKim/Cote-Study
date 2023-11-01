```
package com.test.dfsbfs;

import java.util.LinkedList;
import java.util.Queue;

public class Shortestdistance {

    //자바는 Pair 클래스를 제공하지 않는다. 다양한 방법 중 하나는 사용자가 직접 구현하는 것
    class Pair{

        public int x; public int y;

        public Pair(int x, int y)
        {
            this.x = x;
            this.y = y;
        }
    }

    Queue<Pair> que = new LinkedList<>();
    int[][] visited = new int[5][5]; //방문했던 곳

    public int checkCanNext(int[][] maps,int i, int j, int curcnt){

        if(i<0 || j<0){return -1;} //무대를 벗어나면
        if(i>4 || j>4){return -1;} //무대를 벗어나면
        if(maps[i][j]==0){return -1;} //벽이 있으면
        if(i==4 && j==4){
            maps[i][j]=curcnt+1;
            return 1;
        } //도착하면


        if( visited[i][j]!=-1){
        que.add(new Pair(i,j));
        maps[i][j]=curcnt+1;
        } 
        //갈 수 있으면 큐에 넣기
        return -1;
    }


    public int solution(int[][] maps) {

        int distanceCnt=0;

        que.add(new Pair(0, 0)); //첫 시작점
        distanceCnt++;

        while(!que.isEmpty()){

            Pair p = que.peek();
            //System.out.println("p.x.y"+p.x+" "+p.y);
            visited[p.x][p.y]=-1;
            int curcnt = maps[p.x][p.y];

            if(checkCanNext(maps, p.x-1, p.y, curcnt) == 1) break;//상
            if(checkCanNext(maps, p.x+1, p.y, curcnt) == 1) break;//하
            if(checkCanNext(maps, p.x, p.y-1, curcnt) == 1) break;//좌
            if(checkCanNext(maps, p.x, p.y+1, curcnt) == 1) break;//우  
            que.poll();

        }

        int answer = maps[4][4];
        if(answer==1){answer=-1;}
        return answer;
    }

    public static void main(String[] args) {
        Shortestdistance ob = new Shortestdistance();
        System.out.println(ob.solution(new int[][]{{1,0,1,1,1},{1,0,1,0,1},{1,0,1,1,1},{1,1,1,0,1},{0,0,0,0,1}}));
    }
}


```
