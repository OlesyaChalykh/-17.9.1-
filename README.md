def binary_search(arr, val):
    left, right = 0, len(arr)-1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == val:
            return mid
        elif arr[mid] < val:
            left = mid + 1
        else:
            right = mid - 1
    return -1

num_list = input("Введите последовательность чисел через пробел: ").split()
num_list = [int(x) for x in num_list]

num = int(input("Введите любое число: "))

num_list.sort()
index = binary_search(num_list, num)

if index == -1:
    print("Данного числа нет в последовательности.")
elif index == 0:
    print("Данное число меньше всех элементов в последовательности.")
elif index == len(num_list)-1:
    print("Данное число больше всех элементов в последовательности.")
