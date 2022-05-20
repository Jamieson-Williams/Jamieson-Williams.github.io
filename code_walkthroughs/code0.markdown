---
layout: default
title:  "Code 0"
nav_order: 2
parent: Code Walkthroughs
last_modified_date: "22-05-20"
---

# Code 0 - Runoff

Welcome to the first code walkthrough. In this walkthrough, we will take a look at CS50's Runoff Problem Set from week 3. This can be found [here](https://cs50.harvard.edu/college/2022/spring/psets/3/runoff/). Runoff uses the C programming language. 

In this assignment, we have to complete various functions that simulates a 'runoff' election process. A runoff election is where voters rank candidates in order of preference, and if no candidate recieves more than half of the votes, the candidate with the least amount of votes is eliminated and the process of going through a voters preferences starts again. 

## Specification

There are six different functions that need to be implemented for the runoff assignment. These are vote, tabulate, print_winner, find_min, is_tie and eliminate. Below is a brief desciption of each function.

* **Vote** - Takes arguments voter, rank and name to update candidates preference. If preference is successfully recorded, function returns true, otherwise false. 
* **Tabulate** - Updates the number of votes each candidate has. Every voter votes for top preferred candidate that is not eliminated.
* **Print_Winner** - Prints candidates name if they have more than half the votes and returns true. Otherwise returns false. 
* **Find_Min** - Returns the minimum vote total for any candidate who is still in the election.
* **Is_Tie** - Takes argument min, which is the minimum number of votes that any candidate currently in the election has. Returns true if every candidate remaining has same number of votes, otherwise returns false. 
* **Eliminate** - Takes argument min and eliminates any candidate who has min number of votes. 

## The Code

We are now ready to start implementing each function. Make sure to check out the Runoff assignment linked for more details and background knowledge about this assignment. 

### Vote

We know that vote takes three arguments; voter, rank and name. Voter is the int value of the current voter, rank is the int value of the preference on the voters ballot, and name is the name of the candidate inputted by the user. So how do we tackle this?

Our vote functions need to check the name of each vote and validate whether it's a candidate. To do this, we need a way to loop through the votes. So let's begin by writing our loop.

```c
for (int position = 0; position < ???)
```

We run into a problem. How long should we loop for? We want to loop through all of the voters' votes. Recall that a voter ranks each candidate, which means they vote for each candidate. Their is an integer variable defined called candidate_count that holds the amount of candidates in the election. We can use that to know when all the candidates have been looped through. So to finish the loop we write:

```c
for (int position = 0; position < candidate_count; position++)
{

}
```

Now, we need to compare the name that the voter wrote on the ballot, with the name of the candidate. These are both strings, so we can compare them with strcmp. Strcmp takes two string arguments and returns less than 0 if the first argument comes before the second, 0 if both strings are the same, or greater than 0 if the first string comes after the second. With that in mind, we can evaluate whether strcmp returns 0 by using the following:

```c
strcmp(string1, string2) == 0
```

Recall that the strings we want to compare are the name on ballot, given by the name argument, and the name of the candidate. Candidates is an array, so if we want to pull out a specific candidate's name, we need to index the position in the array and pass in the name struct which is defined earlier in the program. But we don't know the exact index of the candidate's name we need. This is where the position variable comes in handy. We can use this to iterate through all the candidates in the array and pull out the name of that struct using .name. Our function now looks like:

```c
for (int position = 0; position < candidate_count; position++)
{
    if (strcmp(name, candidates[position].name) == 0)
    {

    }
}
```

We can now compare the name of the candidate the voter put down on the ballot, with the names of all the candidates. All that's left to do, is to update the preference array to indicate that the voter has selected the candidate as their 'rank' preference. The preferences array has been defined for us already, where preferences[i][j] is the jth preference for voter i. So we can use the voter and rank input to grab where in the array we want to update. We can then assign the value position to this entry in the array so that preferences[i][j] = position is "the order of a voters preference where position = 0 is the first preference, 1 the second preference, etc." We return true to update the array and move onto the next vote. Make use of the printf function in c see how this works if you're stuck. This completes the vote function. We end up with the vote function looking like this:

```c
bool vote(int voter, int rank, string name)
{
    for (int position = 0; position < candidate_count; position++)
    {
        if (strcmp(name, candidates[position].name) == 0)
        {
            preferences[voter][rank] = position;
            return true;
        }
    }
return false;
}
```

### Tabulate

I found this to be the hardest function to implement in this assignment. This function updates the number of votes that each candidate has. It has to check to see if the candidate is still in the election (i.e not eliminated) and ensure that only a voters' top preferred candidate receives the vote. 

We need to able to 'grab' voters preferences, and to do that we need to use two loops. The first will be used to loop over each voter, while the second loops over each candidate voted for by a single voter. We can use the pre-defined variables of voter_count and candidate_count to know when to end our loops. With this in mind we can start our function like this:

```c
for (int b = 0; b < voter_count; b++)
{
    for (int c = 0; c < candidate_count; c++)
    {

    }
}
```

Now we can loop over the voters preferences, but what do we need to do for each preference? We first need to verify whether or not the candidate is still in the election. Recall that candidates is just an array of struct candidate, and struct candidate has a defined bool value called eliminated. So, we can see whether the candidate is eliminated by using the notation `.eliminated`. Ok, but we can only interact with the candidates array. So we must also need to know the position of the struct canidate in the candidates array, and once we have that we can use the (.) operator to grab the eliminated value. We can use the preferences array with the loop variables, b and c, to get the position of the candidate in the candidates array. Then, if the candidate is not eliminated, we can update their votes! So how does this look?

```c
for (int b = 0; b < voter_count; b++)
{
    for (int c = 0; c < candidate_count; c++)
    {
        if (!candidates[preferences[b][c]].eliminated)
        {

        }
    }
}
```

To explain this further, preferences[b][c] returns an int of the position of the candidate the voter has voted for. Candidates then looks in it's array to find that position, and grabs the eliminated boolean value for the candidate struct. If the eliminated value is True, the if conditional evaluates to false and doesn't run, continuing the looping the voters ballot. If the eliminated value is False, the if conditional can run the next part of code, which will end up updating the candidates votes. Similiar to how we used the preference array and looping variables to index candidates array, we can apply that same logic to grab the votes int defined in the candidate struct. We then want to increment this by 1 and break out of our loop, which moves onto the next voters ballot. Our code to do this is:

```c
void tabulate(void)
{
    for (int b = 0; b < voter_count; b++)
    {
        for (int c = 0; c < candidate_count; c++)
        {
            if (!candidates[preferences[b][c]].eliminated)
            {
                candidates[preferences[b][c]].votes++;
                break;
            }
        }
    }
    return;
}
```

And with that our tabulate function is done. Remember you can use printf statements to see what the values are at specific times in the function. 

### Print_Winner

The print_winner function looks to see if a candidate has more than half the votes. It prints the candidates name if they do, and returns true. The first thing we need to do is loop over each candidate so we can determine if any of them have more than 50% of the votes.

```c
for (int d = 0; d < candidate_count; d++)
{

}
```

Now, we need to check the candidates votes, and do some maths to determine if it's more than 50% of the total votes. We can get the candidates' votes by indexing the candidates array with our looping variable, and using .votes. There is a variable defined called voter_count, so if we divide that by 2, and compare that with the candidates' votes then we can see if the candidate has won the election. Remember, we print the candidates name and return true. This looks like:

```c
bool print_winner(void)
{
    for (int d = 0; d < candidate_count; d++)
    {
        if (candidates[d].votes > voter_count / 2)
        {
            printf("The winner is: %s\n", candidates[d].name);
            return true;
        }
    }
    return false;
}
```

### Find_Min

The find_min function returns the minimum number of votes for any candidate still in the election. Again, we will want to loop over all candidates.

```c
for (int e = 0; e < candidate_count; e++)
{

}
```

We need to check two conditions, if the candidate is eliminated and if the candidate has the minimum number of votes. We know from previous functions discussed that we can use candidates[e].eliminated to get the boolean value, eliminated, for a candidate. But how do we compare the candidates votes to the minimum number of votes? We could use code such as candidate[e].votes < minumum number of votes to see if the candidate has a lower amount of votes than the previous candidates. But we run into a problem. How do we keep track of the minimum number of votes as we loop through the candidates? If we assign an int variable, lets say num_of_votes, and store the value of candidate[e].votes if candidate[e].votes is lower than the current num_of_votes, we can keep track of the minimum number of votes. So, let's first define num_of_votes and assign it a value higher than the maximum number of votes. We can be sure that this will evaluate to true granted the candidate is not eliminated. I choose the starting int value to be 100, since that's the maximum amount of voters. Putting all this together we get:

```c
int num_of votes = 100;
for (int e = 0; e < candidate_count; e++)
{
    if (candidates[e].eliminated == false && candidates[e].votes < num_of_votes)
    {

    }
}   
```

The if conditional is saying "If the candidate is not eliminated, and if the candidates votes is lower than num_of_votes, then perform this code". We now just need to update num_of_votes with the value of candidates[e].votes if the conditional evaluates to true. 

```c
int num_of votes = 100;
for (int e = 0; e < candidate_count; e++)
{
    if (candidates[e].eliminated == false && candidates[e].votes < num_of_votes)
    {
        num_of_votes = candidates[e].votes;
    }
}   
```

Great. We now ensure that the lowest number of votes is tracked. We can now just return num_of_votes. For testing purposes, I also kept track of the candidates name with the lowest votes. The code is basically the same as keeping track of the lowest votes. Our function is now complete!

```c
int find_min(void)
{
    int num_of votes = 100;
    string eliminate_cand = "";
    for (int e = 0; e < candidate_count; e++)
    {
        if (candidates[e].eliminated == false && candidates[e].votes < num_of_votes)
        {
            num_of_votes = candidates[e].votes;
            eliminate_cand = candidates[e].name;
        }
    }
    return num_of_votes;
}   
```

### Is_Tie