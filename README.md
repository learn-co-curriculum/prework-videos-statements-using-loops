# Using Loops

## Learning Goals
+ Describe the purpose of loops in a program
+ Explain the difference between a "times" loop and a conditional loop
+ Use Control-C to Break an Infinitely Looping Program
+ Terminate a while...do...end Loop Naturally
+ Terminate a while...do...end Loop With break Statement
+ Use Integer.times to execute a loop n-times
+ Use loop to create an infinite loop
+ Use until to repeat
+ Compare running a Ruby file versus using IRB
+ Define the Basic while...do...end Structure
+ Provide example of repetition statement

## Outline

+ When writing an application, you might want to repeat code a certain number of times, or based on a condition.
+ Let's say we want to print out "I <3 Programming" five times. How might we do that?
  + We could just write it out 5 times, but this has some disadvantage
    + Harder to read
    + Harder to maintain - what if we want to change the message? Or do this 100 times?
+ Instead we can use a loop!
+ There are a number of different ways to loop a certain number of times in Ruby
  + Remember that, when using Ruby, there's almost always more than one way to do something
  + Which one you should use is usually a matter of the specifics of the problem, and personal preference or the preferences of your team
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
+ Demonstrate `until` as the opposite of `while` - again, just personal preference on which one is better.
+ Sometimes, you want to do something a certain number of times.
+ Let's look at two different types of loops we can use to execute something a certain number of times
+ First, we can do this by setting up a counter variable and using a while loop and a counter
  ```ruby
  counter = 0
  while counter < 5
    puts "I love programming!"
    counter += 1
  end
  ```
  + A lot of times, I might forget to increment my counter. In that case, I'm stuck in an infinite loop - the program will just keep running because I'm never changing my condition.
  + If this happens, I can break the loop in my terminal using "CTRL-C"
+ Another way to do this is using an Integer method called times
  + This is a cool ruby trick that is easy to read
  + We'll look more at why this is unique when we look at Object Orientation, but for now we'll just look at the syntax
  ```ruby
  5.times do
    puts "I love programming!"
  end
  ```
  + So this is a nice way to do this, because it's super readable.
+ One last thing to note - sometimes, you may want to break a loop early.
  + Let's write a program that asks a user a trivia question
  + If they get it right, we should tell them and not ask them anymore
  + Otherwise, we should ask them again a maximum of five times
```ruby
question = "Who was the only US President to serve two non-consecutive terms?"
correct_answer = "Grover Cleveland"
5.times do
  puts question
  answer = gets.strip
end
```
  + So, we can add a condition here that says, if the answer equals the correct answer, then we can break out of the loop.
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
