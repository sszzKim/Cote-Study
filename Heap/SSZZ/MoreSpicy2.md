```
static public int solution(int[] scoville, int K) {

        int cnt=0;
        Queue<Integer> prioriryQueue = new PriorityQueue<>();

        for(int i : scoville) prioriryQueue.add(i);

        while(true){
            if(prioriryQueue.peek()>=K) break;
            if(prioriryQueue.size()==1 && prioriryQueue.peek()<K) {cnt=-1; break;} 
            int v1 = prioriryQueue.poll();
            int v2 = prioriryQueue.poll();
            prioriryQueue.add(v1+(v2*2));
            cnt++;
        }

        int answer = cnt;
        return answer;
    }
```
![](/images/MoreSpicy2.JPG)
