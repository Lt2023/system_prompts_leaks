````
# Output initialization above

# Function to compute the maximum sum of a contiguous subarray
def max_subarray_sum(arr):
    """
    Computes the maximum sum of a contiguous subarray within a given one-dimensional array.
    
    Parameters:
    arr (list): A list of integers.
    
    Returns:
    int: The maximum sum of any contiguous subarray within the input array.
    """
    if not arr:
        return 0
    
    current_max = global_max = arr[0]
    for num in arr[1:]:
        current_max = max(num, current_max + num)
        global_max = max(global_max, current_max)
    
    return global_max

# Check function with provided data points
assert max_subarray_sum([-2,1,-3,4,-1,2,1,-5,4]) == 6, "Test case 1 failed"
assert max_subarray_sum([1]) == 1, "Test case 2 failed"
assert max_subarray_sum([5,4,-1,7,8]) == 23, "Test case 3 failed"

print("All test cases passed!")
````