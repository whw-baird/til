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

### about_symbols

```ruby
# THINK ABOUT IT:
#
# Why do we convert the list of symbols to strings and then compare
# against the string value rather than against symbols?
```

This is interesting, and I'm not sure! Would be interested in hearing the answer in class.

```ruby
# THINK ABOUT IT:
# 
# Why is it not a good idea to dynamically create a lot of symbols?
```

I'm not sure, but maybe it's that symbols are immutable, and if you're creating a lot of symbols you're blocking yourself off from changing those values later.

## about_objects

```ruby
# THINK ABOUT IT:
# What pattern do the object IDs for small integers follow?
```

Object IDs for small integers are consecutive odd numbers. I'm not sure why it's done this way, as opposed to just assigning them an object ID equivalent to their value, unless even-numbered object IDs are used for some other purpose?

## about_hashes

I'm not sure what the answer is supposed to be for
```ruby
def test_accessing_hashes_with_fetch
    hash = { :one => "uno" }
    assert_equal "uno", hash.fetch(:one)
    assert_raise(__) do
      hash.fetch(:doesnt_exist)
    end
```
I tried ```Hash```, ```"hash"```, ```nil```, and ```NoMethodError``` but none worked. I didn't get much from the error message on the first few and was going to give up, but then noticed that the error message on the last one said ```#<KeyError: key not found: :doesnt_exist> was raised```. I tried ```KeyError``` and that did the trick. Will have to pay more attention to types of errors and what they mean.

## about_constants

There are two questions about precedence:
```ruby
assert_equal 2, MyAnimals::Bird.new.legs_in_bird
```
and
```ruby
assert_equal 4, MyAnimals::Oyster.new.legs_in_oyster
```
The question is, why does ```LEGS = 4``` take precedence in one case, and ```LEGS = 2``` in the other? I think the answer is that the ```Oyster``` was defined so as to always take ```MyAnimals``` values: ```MyAnimals::Oyster < Animal```.

