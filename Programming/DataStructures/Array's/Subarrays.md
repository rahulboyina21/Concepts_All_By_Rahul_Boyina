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

