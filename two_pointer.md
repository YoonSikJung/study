### two pointer

two pointer 혹은 sliding window라고도 불린다.

두 개의 포인터를 가지고 조건에 맞는 로직에 따라 리스트를 따라 이동한다. 

리스트 내에서 pair의 검색이 필요할 때 주로 사용된다.

```python
data = [1,2,3,2,5,1]
target = 5

size = len(data)
end = 0
tempSum =0
answer = 0

for start in range(size) :
    while tempSum < target and end < size :
        tempSum += data[end]
        end+=1
    if tempSum == target :
        answer+=1
    tempSum -= data[start]

print(answer)
```