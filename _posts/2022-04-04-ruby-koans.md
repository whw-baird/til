---
layout: post
title: Ruby Koans
---

### about_strings

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
At first I tried ``` true ```, which had worked for other tests in ```about_strings```, but that didn't work. I searched for what the ```string[x,y]``` method did, and then tried ```It```, but that didn't work. Then I realized I hadn't read the documentation for the method carefully enough. The second number isn't the final position of the substring being pulled, it is the *length*. However, I then tried ```"I"```, and that didn't work either. I ended up going to some other tests out of order and came back to it. Ran the test again and noticed it said ```Expected "FILL ME IN" to equal "\n"```. I tried ```\n``` and that seemed to break the test, but then I tried again with ```"\n"``` and it worked. I guess ```\n``` represents the new line, but will have to confirm that.

I did not expect ```.join``` to add spaces between the strings in the array. Cool.

### about_arrays

The arrays were not too tough. Arrays-within-arrays are pretty cool. I'm not sure what is going on with the ```test_swapping_with_parallel_assignment"``` koan, even though I got it.

```ruby
# THINK ABOUT IT:
#
# Ruby programmers tend to favor the shovel operator (<<) over the
# plus equals operator (+=) when building up strings.  Why?
```

Two thoughts: first, the shovel operator is the same character twice, so it may be less prone to a typo (e.g. it may be easier to accidentally input ```++``` than ```<,```. Second, the shovel operator looks like quotation marks (and some [human] languages do use << and >> as quotation marks).
