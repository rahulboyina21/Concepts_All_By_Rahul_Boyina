# SubArrays

### A subarray is a continous block of memory where the data from the given index's satisfies given criteria.

#### I have read this important formulae from one of the best resources in the interner that is how many total number of sub arrays are possible the answer is simple as n*(n+1)/2

EX: for 4 elements array the number of sub arrays possible are 10 simple 

ok so far so good then what can you do that is different in terms of what makes it stand out from array and sub array

like let's start with a basic example 

find the maximum sum of the subarray for the given array.

[1,2,-3,4,5] The obvious answer is 4,5 = 9 but how can you design the algorithm to do that ?

Think think think rahul 

lol i got it 

like brute force is 
if we move two loops in a different speed may be we can find the sub array with max sum
like if we find a element that is decrementing the value then we avoid the iteration till there
keeping track of the sum formulated so far then we go dive into the next remaining part of the elements
then we can explore furthur combinations which could be better than the given element.

Optimal approach would be 

Why two loops bruh just use one loop "Which Loop" don't say do-while go for the while for the time being 
then we have two pointer variables pointing at the 2 differnt blocks at the same time 

Confusing right i felt the same but there is a better way that is breaking it down let's do this 

ALGO:

Steps:
1. we need 2 pointers Q) Where do you keep those pointers -> They begin at the same index at start / adjacent depending on the problem as of now consider they begin at the adjacent.
2. then what now did we got the answer ? Lol not yet genius remember "Wakanda Forever" LOL now we need to do an activity and validate is it satisying our requirement or in the process of satisfying the requirements and we take action.
   1. Add those 2 numbers then we get the sum is it satisfing the required value if no go for the next element.
   2. if satisfies stop and return
   3. if we are trying to find the indefinate answer like MAX/Min etc... we need to traverse all of the array.
   4. 
3. Now when we encounter the value which doesn't coincide with the progression and breaks the chain LOL -> Mark the progress till then make it as a metric for the comparsion of the values then we need to progress ahead.
4. When we progress ahead we need to compare the existing value with the previous one like is my current max sum till index 5 to 9 is max then 0 to 3 if yes now the new UFC undisputed champion of the champions NEW MAX Star is current value else keep trying like Cornor MC'Gragor.
5. so far so good is there any edge cases if there is one edge that can ruin anything that is empty array / array with one element -> answers are 0 / element itself.

😈 Let the devil code from the heaven's of the Leet CODE 😈


```python
#assume we have a list like arr =[1,2,-3,4,5]
# Actual Code

l=len(arr)
le,ri=0,1
sum=0
m=MIN_INT
for i in range(0,l):
    while(le<ri<l):
        sum=sum+arr[ri]
        if sum>max:
            max=sum
        elif sum<max:
              le=ri+1
              ri=ri+2
    ri++

```

IDK HOW THE ABOVE WOULD WORK 

BUT I HAVE SEEN THIS SOLUTION AND I FEEL IT CAN BE THE BEST POSSIBLE ONE OUT THERE WHAT IT IS DOING LET'S SEE

IF THERE IS AN INSTANCE WHERE

SUPPOSE WE WANT TO FIND A SOLUTION FOR THE MAXIMUM SUBARRAY WITH THE HIGHEST 
VALUE (MAX SUB-ARRAY) 
DRAW A LINE AND SUPPOSE WE ARE GOING FROM ONE DOT TO ANOTHER IN THAT LINE
IF THERE COMES A DOT WHICH IS EITHER LESS THAN THE SUM SO FAR OR MORE THAN THE VALUE 
THEN WHAT WILL YOU DO 
YOU SHOULD MAKE A DECISON AS EITHER TO PICK IT UP OR DROP FRESH AS YOU CANNOT JUMP
YOU CAN EITHER START FRESH OR CONTINUE 
IF IT IS A POSITIVE DOT THEN DEFINTELY ADD IF NOT OBIVOUSLY YOU MIGHT ADD OR DROP 
IN EITHER CASES IF YOU EITHER ADD OR DROP 
THE UPCOMING FUTURE SUM IS STILL UNPREDICTABLE SO IF WE DROP THE VALUE NOW WHAT
WE HAVE ACCUMALTED SO FAR WHAT IF FUTURE IS NOT FRUTFULL AS TILL CURRENT THEN
WE SHOULD BE ABLE TO CONSIDER THE PREVIOUS SOLUTION AS THE BEST SOLUTION WHICH MEANS
EVEN THOUGH WE ARE WORKING TO FIND THE BEST SOLUTION STILL WE ARE EXPECTED TO KEEP TRACK OF THE 
SUMS SO FAR AND ALSO MAKE THE APPROPRIATE DECISION BASING ON THE FACTOR IS IT HELPING US 
TO STRIVE BETTER SUCH AS SO I NEED TO STORE ALL THE VALUES OF ALL THE PREVIOUS 
SUBARRAYS BEFORE I BREAK THE CURRENT SUBARRAY AND GO FOR A NEW ONE 
AWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWWW HOW WONDERFUL PUT IT INTO THE CODE
SURGENT 
RIGHT ON THE ACTION 

```
def battleshipdestroyer:
    allsubarrsums,localsum="[0'],0
length = len(arr)

for i in range(length):
if localsum<0:
localsum=0

localsum+=arr[i]
allsubarrsums.append(localsum)


out of the loop

max(allsubarrsums) will give the max sub array


```

![diagram-export-3-25-2025-5_54_22-PM](https://github.com/user-attachments/assets/eb2d80d4-4145-495a-bf3a-64e2b0142eb4)


## How can i furthur improve the given set of code ?

### Let's ask few questions to ourselves as 
- Are we getting the right answer
- If Above question's answer is Yes then let's do this
- Optimze but how can we do that
  1. Give me the list of the variables and the sub processes in the actual problem that is being used to solve the problem.
  2. They are
    1. Variables are -> Length / store all the max sums till now / local sum updated in every instance.
    2. Process is we store all the values into the array like structure to find the max value of it.
    3. we reset the local sum to the zero when we reach the value less than the Zero.

What can be improved:

1. Resetting the sum is the core step that cannot be altered or modified as it will lose the key essence of this problem solving method.
2. But the process of adding the all the values then finding the max![diagram-export-3-25-2025-6_11_56-PM](https://github.com/user-attachments/assets/2b4bb79d-83a5-4d3b-84ac-344e671dcaa6)

Explanation of the Given Code:

The code is an implementation of Kadane’s Algorithm, which efficiently finds the maximum sum subarray in a given list of integers.

Breakdown of the Code:

class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        mxsum, csum = -float('inf'), 0

	•	mxsum (Maximum Sum): Keeps track of the highest sum found so far. Initialized to negative infinity to handle cases where all elements are negative.
	•	csum (Current Sum): Tracks the sum of the current subarray.

        size = len(nums)
        if size == 1:
            return nums[0]

	•	If the array has only one element, the answer is simply the element itself.

        for i in range(size):
            if csum < 0:
                csum = 0
            csum += nums[i]
            mxsum = max(mxsum, csum)

	•	We traverse the array.
	•	If csum becomes negative, we reset it to 0 (because negative sums hurt our subarray).
	•	Add the current element to csum.
	•	Update mxsum to store the maximum sum encountered so far.

        return mxsum

	•	Finally, return the maximum subarray sum.

Example Walkthrough

Input:

nums = [1, 2, -3, 4, 5]

Step-by-step Execution:

Iteration	nums[i]	csum (Current Sum)	mxsum (Max Sum)
1st (i=0)	1	1	1
2nd (i=1)	2	3	3
3rd (i=2)	-3	0 (Reset)	3
4th (i=3)	4	4	4
5th (i=4)	5	9	9

Final Output:

9

✅ Correct Answer: [4,5] → 9

Optimizations and Improvements
	1.	Memory Optimization
	•	Instead of storing all subarrays, the algorithm keeps only csum and mxsum, reducing space complexity to O(1).
	2.	Time Complexity
	•	Brute force: O(N²)
	•	Kadane’s Algorithm: O(N) (Best possible!)

Key Takeaways
	•	Kadane’s Algorithm efficiently finds the max sum subarray in O(N) time.
	•	If the current sum (csum) goes negative, reset it to 0.
	•	Maintain a global max (mxsum) to store the best sum seen so far.
	•	Single-pass, no extra space, making it highly optimized.

🔥 Final Verdict:
✅ This is the best possible solution for Maximum Subarray Problem using Kadane’s Algorithm! 🚀

