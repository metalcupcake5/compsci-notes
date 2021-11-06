## `final`
### 11/4/21
#### constants
- variables in computer science are very different from variables in math and natural sciences in that they do not represent a fixed value; we regularly change and update the values of variables as we please in computer science
- sometimes we want a variable in computer science to represent a fixed value that doesn't get changed later. In this case, we use the keyword `final` while declaring it. This is most typically done with class variables, but can be done with local variables too.
- trying to change the value of a variable that was declared with `final` results in a compile-time error

#### syntax of constants
- constants follow a different naming convention from other identifiers: they are stylized in all caps, with underscores separating words
	- informally known as SCREAMING_SNAKE_CASE
- the keyword `final` is the last keyword before the data type

```java
private static final int MONTHS_PER_YEAR = 12;
```

#### what are constants for?
- constants are basically a way to give a name to a constant value that has importance for your code
- say you're writing a class for a card game, and the maximum number of cards you can have in your hand is 9. If you just use the raw value 9, your teammate might look at code you wrote and not really understand the purpose of `if(cards > 9)`. It's much clearer if you've initialized a class constant `MAX_CARDS` to 9.
- what if the rules change, and the maximum becomes 10? Do you want to change every part of your code that has the value 9? Or do you want to change the single line of code that initializes `MAX_CARDS`?

#### encapsulation exception
- sometimes, you might write a constant that is actually useful for other classes, and you want them to be able to access it
- in these cases you might declare a class constant as `public`. This is basically the only time you should make a class variable `public` instead of `private`

#### Math attributes: `PI`
- data type: `double`
- a `public` class constant in the Math class that represents the most precise value for pi that can be represented with a `double` in Java

```java
public double getArea()
{
	return Math.PI * radius * radius;
}
```