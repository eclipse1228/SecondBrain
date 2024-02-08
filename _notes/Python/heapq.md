### 리스트를 heap으로

```Python
heap = [1,2,3,4,5]
heapify(heap)

print(heap)
```

### 원본리스트 유지

```Python
nums=[1,2,3,4,5]

heap = nums[:]
heapify(heap)

print(nums)
print(heap)
```

### 몇번째 작은 값 찾기

```python
def nth_smallest(nums, n):
	heap = []
	for num in nums:
		heapq.heappush(heap,num)
	nth_min = None
	
	for _ in range(n):
		nth_min = heappop(heap)
	
	return nth_min

print(nth_smallest([4,1,7,8,5,1],2))

```

