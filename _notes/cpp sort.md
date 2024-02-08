algorith 헤더파일
void sort(T start, T end, Compare comp);

3번째 인자를 넣지 않으면 default로 오름차순으로 정렬이 됩니다.

- sort(v.begin(), v.end(), greater자료형());    //내림차순 (Descending order)
    
- sort(v.begin(), v.end(), less<자료형>());        //오름차순 (default = Ascending order)

# CountingSort

