# make-bignumber-2
#python
# Find the largest number that can be made by concatenating numbers in a list. 리스트안에 있는 숫자들을 이어 붙여서 만들수 있는 가장 큰수를 구하기
# This code is taking too long.
from itertools import permutations # itertools 모듈의 permutations 패키지를 import 한다.
# permutations함수에 리스트와 조합하고자 하는 원소개수를 인자로 넣어준다 : permutation( 리스트, r ) 순열 조합 객체가 반환된다. 
# ('A', 'B'), ('A','C'), ('B','A'), ('B','C'), ('C','A'), ('C','B) 

def solution(numbers):
    permute = list(permutations(numbers,len(numbers)))
    list_permute = [''.join(map(str,i)) for i in permute]   
    answer = max(list_permute)
    return answer
numbers=[3,30,34,5,9]
a=solution(numbers)
print(a)

# This cod is correct.
def solution(numbers):
    
    numbers = list(map(str, numbers))
    numbers.sort(key = lambda x : x*3, reverse = True) # lambda x : x*3은 num 인자 각각의 문자열을 3번 반복한다는 뜻이다. 
# x*3 이유? 1000자리 이하로 3자리수로 맞춘 뒤, 비교하겠다는 뜻.
    return str(int(''.join(numbers)))
numbers=[3,30,34,5,9]
a=solution(numbers)
print(a)
# result--> "9534330"
