# The-Kraken-s-Last-Dam

A harbour engineer is designing a seawall. She has n vertical pillars arranged in a line, each with a given height. She wants to choose two pillars to form the walls of a water barrier — the barrier can hold water up to the height of the shorter pillar, and its capacity equals that shorter height multiplied by the horizontal distance between the two pillars.

Find the maximum water capacity any such pair of pillars can hold.

Input
The first line contains 
n
n. The second line contains 
n
n space-separated non-negative integers — the heights of the pillars.

Output
A single integer — the maximum water capacity.

Constraints
2≤n≤100000
0≤heighti≤10000


n = int(input())
heights = list(map(int, input().split()))

left = 0
right = n - 1

max_area = 0

while left < right:

    height = min(heights[left], heights[right])
    width = right - left

    area = height * width

    max_area = max(max_area, area)

    if heights[left] < heights[right]:
        left += 1
    else:
        right -= 1

print(max_area)
