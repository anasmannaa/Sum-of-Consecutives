# Sum-of-Consecutives
Some times we face an algebric mathimatical problem says:<br/>
"Find two consecutive numbers whose sum is 57"<br/>

The solution would be easy, we need to create a linear equation (data model) to solve the problem:<br/>
let x = first numbee<br/>
then  x + 1 represents the second number<br/>
first number + second number  = 57 (given by the problem)<br/>
x + (x+1) = 57 (replace first number with x and second number with x + 1)<br/>
2x + 1 = 57 (simplify the equation)<br/>
2x = 56 (subtract 1 from both sides)<br/>
x = 28 (divide both sides by 2)<br/>
The first number is 28, and the second number is x+1 = 29<br/>
and that was the solution mathimatically.<br/><br/>

Recape: we have created a mathimatical data model to solve the equation.<br/><br/>

Now let's take our data model to the second level and create an algorithm to help us solve the same problem for any number od consecutive numbers (after some try and test steps I got that algorith):<br/>
1- let x equal to the number of consecutive numbers that sums to the given sum.<br/>
2- let y represents the cumulative positional sum of the consecutive numbers giving the first number a position value of 0 (for example if we have 4 consecutive numbers that sms to the given sum, we calculate 0 + 1 + 2 + 3, and that will be the value of y)<br/>
3 the solution will be as follow:<br/>
- first number (the least one) = (given sum - y) / x
- first number = x + (second number position) 1
- first number = x + (second number position) 2
- first number = x + (second number position) 3
- and so on ..........

Example:<br/>
Find four consecutive numbers whose sum is 90.<br/><br/>

Solution:<br/>
sum = 90<br/>
Let x = 4<br/>
let y = 0 + 1 + 2 + 3 = 6<br/>
first number = (sum - y) / x = 21<br/>
second number = first number + 1 = 22<br/>
third number = first number + 2 = 23<br/>
Fourth number = first number + 3 = 24<br/><br/>

Check our solution:<br/>
21 + 22 + 23 + 24 = 90 (we did it right)<br/><br/>

Now, it is time to use a programming language data structur to rewrite our algorith (to convert the mathimatical data model into a C language data model)<br/><br/>

Javascript:<br/><br/>
```
function getConsecutives (consecutiveNum, consecutiveSum) {
    const consecutives = [];
    let firstNumber;
    let positionCumulative = 0;
    for (let i = 1; i < consecutiveNum; i++)
    {
        positionCumulative += i;
    }

    firstNumber = (consecutiveSum - positionCumulative) / consecutiveNum;
    
    for (let i = 0; i < consecutiveNum; i++)
    {
        consecutives[i] = firstNumber + i;
    }

    return consecutives;
}
```
Test:
Find four consecutive numbers whose sum is 90?
```
getConsecutives(3, 90);
```
Solution: [21, 22, 23, 24]

