---
layout: post
title: Ruby Koans
---

I struggled with ```about_strings```. In particular, I couldn't figure out what was supposed to go in the blank for: 
```ruby 
  assert_equal __, long_string[0,1]
```
in response to the prompt
```ruby
    long_string = %{
  It was the best of times,
  It was the worst of times.
  }
```
At first I tried ``` true ```, which had worked for other tests in ```about_strings```, but that didn't work. I searched for what the ```string[x,y]``` method did, and then tried ```It```, but that didn't work. Then I realized I hadn't read the documentation for the method carefully enough. The second number isn't the final position of the substring being pulled, it is the *length*. However, I then tried ```"I"```, and that didn't work either. Not sure what the solution is, will have to come back to it later.

The arrays were not too tough. Arrays-within-arrays are pretty cool. I'm not sure what is going on with the ```test_swapping_with_parallel_assignment"``` koan, even though I got it.
