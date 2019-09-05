# Using Loops

## Learning Goals
+ Describe the purpose of loops in a program
+ Explain the difference between a "times" loop and a conditional loop
+ Use Control-C to Break an Infinitely Looping Program
+ Use while, until, and times to create loops

## Lesson
+ Hi folks, it's Ian from Flatiron School. In this video, we're going to look at using loops in a ruby application. Our learning goals for this video are:
  + Describe the purpose of loops in a program
  + Explain the difference between a "times" loop and a conditional loop
  + Use Control-C to Break an Infinitely Looping Program
  + Use while, until, and times to create loops
+ So let's get started.
+ When writing an application, you might want to repeat code a certain number of times, or based on a condition.
+ Let's say we want to print out "I <3 Programming" five times. How might we do that?
  + We could just write it out 5 times, but this has some disadvantages
  ```ruby
  puts "I <3 Programming"
  puts "I <3 Programming"
  puts "I <3 Programming"
  puts "I <3 Programming"
  puts "I <3 Programming"
  ```
    + It's harder to read - we have to read this five times.
    + It's harder to maintain - what if we want to change the message? We'll have to edit this five times now. Or what if we want to do this 100 times? Well need to add 95 lines of code!
+ Instead we can use a loop! Loops are useful in programming because they let you repeat chunks of code.
+ Let's look first at conditional looping. Sometimes, we want to execute something until some condition is met.
+ Say we want to build a command line interface, and we want to exit our program after the user types quit
+ For this we can use a `while` loop - this loop will run as long as the condition is true
   ```ruby
    input = gets.strip
    while input != 'quit'
      puts "You typed #{input}"
      input = gets.strip
    end
    ```
  + This will keep looping, and each time, we check to see, "hey, is input equal to 'quit'? if it is, we won't run this"
+ We can also use the `until` loop in ruby - this is just opposite of `while`.
```ruby
 input = gets.strip
 until input == 'quit'
   puts "You typed #{input}"
   input = gets.strip
 end
 ```
 + This is just personal preference on which one is better.
+ Sometimes, you want to do something a certain number of times.
+ So that's conditional looping. Let's look now at how we might loop a certain number of times.
+ Again, there are usually many ways in Ruby to do something. It's usually a matter of personal preference or the preference of your team to figure out which way you want to do something for a particular job. Most of the time there are no wrong answers, just preferences and tradeoffs. So don't worry about it too much.
+ Anyway, let's look at one way we might set up a loop.
+ First, we can do this by setting up a counter variable and using a while loop and a counter
  ```ruby
  counter = 0
  while counter < 5
    puts "I love programming!"
    counter += 1
  end
  ```
  + A lot of times, I might forget to increment my counter.
  ```ruby
  counter = 0
  while counter < 5
    puts "I love programming!"
  end
  ```
  + In that case, I'm stuck in an infinite loop - the program will just keep running because I'm never changing my condition.
  + If this happens, I can break the loop in my terminal using "CTRL-C" - so that's important to remember.
+ Another way to do a loop like this in Ruby is using an Integer method called times
  + This is a cool Ruby trick that is easy to read
  + We'll look more at why this is unique when we look at Object Orientation, but for now we'll just look at the syntax
+ So I can write `5.times` and then, in between `do` and `end` here, I can write the code that I want to run.  
  ```ruby
  5.times do
    puts "I love programming!"
  end
  ```
  + So this is a nice way to do this, because it's super readable. We've shown this code to tons of people over the years, and everyone can pretty much guess at what this does.
+ One last thing to note - sometimes, you may want to break a loop early. Let's look at an example of how we might do that.
+ Say we want to write a program that asks a user a trivia question
+ If they get the question right, we should tell them they are right and not ask them any more
+ Otherwise, we should ask them again, but let's say to be nice, we'll only ask them 5 times.
```ruby
question = "Who was the only US President to serve two non-consecutive terms?"
correct_answer = "Grover Cleveland"
5.times do
  puts question
  answer = gets.strip
end
```
+ So, we can add a condition here that says, if the answer equals the correct answer, we'll print that they got it correct.
  ```ruby
  question = "Who was the only US President to serve two non-consecutive terms?"
  correct_answer = "Grover Cleveland"
  puts question

  5.times do
    answer = gets.strip
    if answer == correct_answer
      puts "That's correct!"
    else
      puts "Sorry, please try again."
    end
  end
  ```
  + But see how this is kind of weird? Because even if you get the correct answer, you still get asked the question again. So if the answer is right, I want to break out of the loop. I can do that using the `break` keyword. `break` basically just says, hey, end this loop - stop whatever you were doing and move on with the program.
  ```ruby
  question = "Who was the only US President to serve two non-consecutive terms?"
  correct_answer = "Grover Cleveland"
  puts question

  5.times do
    answer = gets.strip
    if answer == correct_answer
      puts "That's correct!"
      break
    else
      puts "Sorry, please try again."
    end
  end
  ```
  + The `break` keyword works the same for any type of loop - while, until, or times. So that's it for this video - to recap:
  + We described the purpose of loops in a program - so we can repeat chunks of code and make our programs easier to read and maintain
  + We discussed the difference between a "times" loop and a conditional loop and when you might use one over the other
  + We used Control-C to Break an Infinitely Looping Program
  + And we used while, until, and times to create loops in our programs

  + Thanks so much for watching, happy coding!
