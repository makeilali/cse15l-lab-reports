# Part 1 - Debugging Scenario
Anonymous:

Hey,

I'm having trouble with my Java program. Whenever I run it, I'm getting some strange output that I can't figure out. Here's a screenshot showing what I'm seeing:

![image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-03-12%20at%205.44.26%20PM.png?raw=true)
![image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-03-12%20at%205.44.32%20PM.png?raw=true)

It looks like the program is printing numbers that are much larger than expected. My guess is that there might be an issue with the sum logic, but I'm not entirely sure. Thoughts?

Response from TA:

Hi there,

Thanks for reaching out. Could you try adding some print statements to your code to see what values the variables have during runtime? Specifically, can you print out the values of the variables involved in the calculation before and after the calculation? This might help us identify where the problem lies. Let me know what you find!

![image](https://github.com/makeilali/cse15l-lab-reports/blob/main/Screenshot%202024-03-12%20at%205.55.56%20PM.png?raw=true)



After adding print statements as suggested by the TA, I noticed that the values of the variables involved in the calculation were increasing exponentially. Upon closer inspection, I realized that I forgot to include a terminating condition for a loop, causing it to run indefinitely and resulting in the unexpected behavior.


# Part 2 - Reflection

Something I learned from my lab experience during th esecond half of this quarter was the grading script that we used. That gave me a perspective from a student on how my assignments are graded, which was very intruiging. That helped me learn the different areas that affect the script based on the effrctiveness could be changed by the little things.
