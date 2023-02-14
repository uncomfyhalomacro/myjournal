---
tags:
 - self-learning
 - software
 - sevendaysinsevenweeks
 - 7d7w
---

# Ruby Chapters

## Day 1 Self-Study

### Resources

- [The Ruby API](https://rubyapi.org/)
- [Programming Ruby](https://ruby-doc.com/docs/ProgrammingRuby/)
- [The Ruby Documentation](https://docs.ruby-lang.org/en/)

### Tasks Day 1

#### Find

- [x] The Ruby API
- [x] The free online version of _Programming Ruby: The Pragmatic Programmer's Guide_ [TFH08]
- [x] A method that substitutes a part of a string
- [x] Information about Ruby's regular expressions
- [x] Information about Ruby's ranges

#### Do

- [x] Print the string "Hello, world."

```ruby
puts "Hello, world."
```

- [x] For the string "Hello, Ruby." find the index of the word "Ruby."

```ruby
hello = "Hello, Ruby."
rubyindex = hello.index("Ruby.")
puts "The index of 'Ruby.' is #{rubyindex}"

```

- [x] Print your name ten times.

```ruby
i = 0
until i == 10
  i+=1
  puts "Soc Virnyl Estela"
end
```

- [x] Print the string "This is sentence number 1." where the number 1 changes from 1 to 10.

```ruby
i = 0
until i == 10
  i+=1
  puts "This is sentence #{i}"
end
```

- [x] Run a Ruby program in a file. ***Copied all the tasks from above to a file***
- [x] Bonus: Write a program that picks a random number. Player guesses a number and tells them if the guess is too low or too high.

```ruby
#!/usr/bin/ruby
def rng(largest)
  Random.new()
  return Random.rand(1..largest)
end

def player
  guess = gets.to_s.chomp.to_i
  return guess
end

def play_game
  puts "Guess the number! What's the highest number do you want it to be?\n"
  correct_answer = rng(gets.to_s.chomp.to_i)
  puts "Randomizing! Now guess the correct number we generated! Type now below!\n"
  guess = player()
  until guess == correct_answer
    if guess < correct_answer
      puts "Too low!"
    else
      puts "Too high!"
    end
    guess = player()
  end
  puts "You finally got the correct answer: #{correct_answer}"
end

play_game
```

I changed this a bit so it could be also a valid crystal code.

## Day 2 Floating Down from the Sky

