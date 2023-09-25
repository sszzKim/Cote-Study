```
public int[] solution(int []arr) {
        //1.문제
        /*
        * 1차원 배열에서 연속된 숫자를 제거하여 출력
        * */

        List<Integer> arrayList = new ArrayList<>(); //중복제거한 값을 담을 LIST 선언
        for(int i=0; i< arr.length;i++){
            if(arrayList.size() == 0) arrayList.add(arr[0]); //첫번째 값은 비교할게 없음
            else{
                if(!(arr[i] == arrayList.get(arrayList.size()-1)))
                    arrayList.add(arr[i]);
            }
        }

        int[] answer = arrayList.stream()
                //.mapToInt(Integer::intValue)//스트림을 IntStream으로 변환
                .mapToInt(Integer::intValue)
                .toArray(); //liist를 배열로 변환
        return answer;
    }
```
