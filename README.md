# kimseonghwan

import random
import time
import sys
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt


def recursive_selection_sort(arr):
    # 종료 조건: 리스트의 길이가 1 이하일 경우 정렬할 필요 없음
    if len(arr) <= 1:
        return arr
    
    # 최솟값을 찾아서 맨 앞으로 이동
    min_idx = 0
    for i in range(1, len(arr)):
        if arr[i] < arr[min_idx]:
            min_idx = i
    arr[0], arr[min_idx] = arr[min_idx], arr[0]
    
    # 첫 번째 원소를 제외한 나머지 부분에 대해 재귀적으로 정렬 수행
    sorted_rest = recursive_selection_sort(arr[1:])
    
    # 정렬된 부분과 첫 번째 원소를 합쳐서 반환
    return [arr[0]] + sorted_rest


def recursive_bubble_sort(arr):
    # 종료 조건: 리스트의 길이가 1 이하일 경우 정렬할 필요 없음
    if len(arr) <= 1:
        return arr
    
    # 한 번의 패스 동안 큰 값을 맨 뒤로 이동시키는 과정
    for i in range(len(arr) - 1):
        if arr[i] > arr[i + 1]:
            arr[i], arr[i + 1] = arr[i + 1], arr[i]
    
    # 맨 마지막 원소를 제외한 나머지 부분에 대해 재귀적으로 정렬 수행
    sorted_rest = recursive_bubble_sort(arr[:-1])
    
    # 정렬된 부분과 맨 마지막 원소를 합쳐서 반환
    return sorted_rest + [arr[-1]]


def recursive_insertion_sort(arr):
    # 종료 조건: 리스트의 길이가 1 이하일 경우 정렬할 필요 없음
    if len(arr) <= 1:
        return arr
    
    # 첫 번째 원소를 제외한 나머지 부분에 대해 재귀적으로 정렬 수행
    sorted_rest = recursive_insertion_sort(arr[1:])
    
    # 현재 원소를 적절한 위치에 삽입하여 정렬된 부분 반환
    current_element = arr[0]
    index = 0
    
    # 정렬된 부분에서 현재 원소보다 큰 값을 찾음
    while index < len(sorted_rest) and sorted_rest[index] < current_element:
        index += 1
    
    # 현재 원소를 찾은 위치에 삽입
    sorted_rest.insert(index, current_element)
    
    return sorted_rest

def recursive_merge_sort(arr):
    # 종료 조건: 리스트의 길이가 1 이하일 경우 정렬할 필요 없음
    if len(arr) <= 1:
        return arr
    
    # 리스트를 반으로 나누기 위한 중간 인덱스 계산
    mid = len(arr) // 2
    
    # 중간 인덱스를 기준으로 리스트를 반으로 나눔
    left = arr[:mid]
    right = arr[mid:]
    
    # 재귀적으로 왼쪽과 오른쪽 부분을 정렬
    left_sorted = recursive_merge_sort(left)
    right_sorted = recursive_merge_sort(right)
    
    # 정렬된 두 부분을 병합하여 정렬된 리스트 반환
    return merge(left_sorted, right_sorted)

def merge(left, right):
    merged = []
    left_index = 0
    right_index = 0
    
    # 왼쪽과 오른쪽 리스트를 비교하면서 작은 값을 병합
    while left_index < len(left) and right_index < len(right):
        if left[left_index] <= right[right_index]:
            merged.append(left[left_index])
            left_index += 1
        else:
            merged.append(right[right_index])
            right_index += 1
    
    # 남은 원소들을 병합
    merged.extend(left[left_index:])
    merged.extend(right[right_index:])
    
    return merged

def quick_sort(arr):
    # 종료 조건: 리스트의 길이가 1 이하일 경우 정렬할 필요 없음
    if len(arr) <= 1:
        return arr
    
    # 리스트에서 기준점을 선택 (보통은 첫 번째 원소를 선택)
    pivot = arr[0]
    
    # 기준점보다 작은 값들과 큰 값들을 담을 두 개의 리스트 생성
    less_than_pivot = []
    greater_than_pivot = []
    
    # 기준점을 제외한 나머지 원소들을 비교하여 작은 값은 less_than_pivot에, 큰 값은 greater_than_pivot에 추가
    for num in arr[1:]:
        if num <= pivot:
            less_than_pivot.append(num)
        else:
            greater_than_pivot.append(num)
    
    # 작은 값들과 큰 값들을 재귀적으로 정렬하고, 기준점과 함께 병합하여 정렬된 리스트 반환
    return quick_sort(less_than_pivot) + [pivot] + quick_sort(greater_than_pivot)

def heapify(arr, n, i):
    largest = i
    left = 2 * i + 1
    right = 2 * i + 2

    # 왼쪽 자식과 비교하여 가장 큰 값을 찾음
    if left < n and arr[left] > arr[largest]:
        largest = left

    # 오른쪽 자식과 비교하여 가장 큰 값을 찾음
    if right < n and arr[right] > arr[largest]:
        largest = right

    # 가장 큰 값이 현재 노드(i)보다 크다면 교환
    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i]
        heapify(arr, n, largest)


def heap_sort(arr):
    n = len(arr)

    # 최대 힙 구성 (배열을 힙 구조로 변환)
    for i in range(n // 2 - 1, -1, -1):
        heapify(arr, n, i)

    # 힙 정렬 수행
    for i in range(n - 1, 0, -1):
        arr[i], arr[0] = arr[0], arr[i]  # 최대 값(루트 노드)과 마지막 노드를 교환
        heapify(arr, i, 0)  # 다시 힙 구성

    return arr

def shell_sort(arr):
    # 입력으로 주어진 리스트 arr의 길이를 구함
    n = len(arr)

    # 초기 간격(gap)을 리스트의 길이의 절반으로 설정
    gap = n // 2

    # 간격을 절반으로 줄여가며 정렬을 수행하는 반복문을 실행
    while gap > 0:
        # 간격부터 시작하여 리스트의 끝까지 반복하면서 삽입 정렬을 수행
        for i in range(gap, n):
            temp = arr[i]  # 현재 원소(temp)를 임시로 저장
            j = i

            # 부분 리스트 내에서 삽입 정렬 수행
            # 현재 원소(temp)와 이전 간격만큼 떨어진 원소를 비교하여 정렬 위치를 찾음
            while j >= gap and arr[j - gap] > temp:
                arr[j] = arr[j - gap]  # 간격만큼 떨어진 위치의 원소를 한 칸씩 오른쪽으로 이동
                j -= gap

            arr[j] = temp  # 현재 원소를 정렬 위치에 삽입

        gap //= 2  # 간격을 절반으로 줄임

    return arr






sys.setrecursionlimit(1000000)
listLength = 1000

B = []
for value in range(0, listLength):
    B.append(random.randint(0, 300))

S_average_time = 0
B_average_time = 0
I_average_time = 0
M_average_time = 0
Q_average_time = 0
H_average_time = 0
L_average_time = 0

A = B.copy()  # 리스트 B를 A에 복사

# Selection Sort 시간 측정을 위한 반복문
for i in range(0, 1000):
    start = time.time()  # 시간 측정을 위해 시작 시간을 기록
    recursive_selection_sort(A)  # A 리스트에 대해 재귀적인 Selection Sort를 수행
    end = time.time()  # 시간 측정을 위해 종료 시간을 기록
    S_average_time += end - start  # 수행 시간을 S_average_time에 더함.

A = B.copy()  # 리스트 B를 A에 복사

# Bubble Sort 시간 측정을 위한 반복문
for i in range(0, 1000):
    start = time.time() # 시간 측정을 위해 시작 시간을 기록
    recursive_bubble_sort(A)  # A 리스트에 대해 재귀적인 Bubble Sort를 수행
    end = time.time() # 시간 측정을 위해 종료 시간을 기록
    B_average_time += end - start # 수행 시간을 B_average_time에 더함.

A = B.copy()  # 리스트 B를 A에 복사

# Insertion Sort 시간 측정을 위한 반복문
for i in range(0, 1000):
    start = time.time() # 시간 측정을 위해 시작 시간을 기록
    recursive_insertion_sort(A) # A 리스트에 대해 재귀적인 Insertion Sort를 수행
    end = time.time() # 시간 측정을 위해 종료 시간을 기록
    I_average_time += end - start # 수행 시간을 I_average_time에 더함.

A = B.copy()  # 리스트 B를 A에 복사

# Merge Sort 시간 측정을 위한 반복문
for i in range(0, 1000):
    start = time.time() # 시간 측정을 위해 시작 시간을 기록
    recursive_merge_sort(A) # A 리스트에 대해 재귀적인 Merge Sort를 수행
    end = time.time() # 시간 측정을 위해 종료 시간을 기록
    M_average_time += end - start # 수행 시간을 M_average_time에 더함.

A = B.copy()  # 리스트 B를 A에 복사

# Quick Sort 시간 측정을 위한 반복문
for i in range(0, 1000):
    start = time.time() # 시간 측정을 위해 시작 시간을 기록
    quick_sort(A) # A 리스트에 대해 Quick Sort를 수행
    end = time.time() # 시간 측정을 위해 종료 시간을 기록
    Q_average_time += end - start # 수행 시간을 Q_average_time에 더함.

A = B.copy()  # 리스트 B를 A에 복사

# Heap Sort 시간 측정을 위한 반복문
for i in range(0, 1000):
    start = time.time() # 시간 측정을 위해 시작 시간을 기록
    heap_sort(A)  # A 리스트에 대해 Heap Sort를 수행
    end = time.time() # 시간 측정을 위해 종료 시간을 기록
    H_average_time += end - start # 수행 시간을 H_average_time에 더함.

A = B.copy()  # 리스트 B를 A에 복사

# Shell Sort 시간 측정을 위한 반복문
for i in range(0, 1000):
    start = time.time() # 시간 측정을 위해 시작 시간을 기록
    shell_sort(A) # A 리스트에 대해 Shell Sort를 수행
    end = time.time() # 시간 측정을 위해 종료 시간을 기록
    L_average_time += end - start # 수행 시간을 L_average_time에 더함.

S_average_time /= 1000
B_average_time /= 1000
I_average_time /= 1000
M_average_time /= 1000
Q_average_time /= 1000
H_average_time /= 1000
L_average_time /= 1000

df = pd.DataFrame({
    'Bubble Sort': [B_average_time],  # Bubble Sort의 평균 실행 시간을 데이터프레임에 추가
    'Selection Sort': [S_average_time],  # Selection Sort의 평균 실행 시간을 데이터프레임에 추가
    'Merge Sort': [M_average_time],  # Merge Sort의 평균 실행 시간을 데이터프레임에 추가
    'Insertion Sort': [I_average_time],  # Insertion Sort의 평균 실행 시간을 데이터프레임에 추가
    'Quick Sort': [Q_average_time],  # Quick Sort의 평균 실행 시간을 데이터프레임에 추가
    'Heap Sort': [H_average_time],  # Heap Sort의 평균 실행 시간을 데이터프레임에 추가
    'Shell Sort': [L_average_time]  # Shell Sort의 평균 실행 시간을 데이터프레임에 추가
})

# 막대 그래프로 데이터를 시각화하여 출력
df.plot(kind='bar')
plt.show()
