# kimseonghwan

import sys
input = sys.stdin.readline

left = list(input().strip())
right = []
a = int(input())

for _ in range(a):
    b = input().split()

    if b[0] == "L":
        if left:
            right.append(left.pop())
    elif b[0] == "D":
        if right:
            left.append(right.pop())
    elif b[0] == "B":
        if left:
            left.pop()
    elif b[0] == "P":
        left.append(b[1])

print("".join(left + right[::-1]))
