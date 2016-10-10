# JS | Koans Lab

## Koans

### What are the Koans?

Koans originate from Zen Buddhism, and are paradoxical riddles or stories used to test "students" on their path to enlightenment. They are designed to provoke thought or doubt in the student's mind. We are here to learn coding, so... what are the Koans?

The Koans are a series of assertions you must solve to understand how a programming language works. This is the first step to become a better developer. The Koans become increasingly more difficult as you continue, so don't feel discouraged as you move forward through them.

There are Koans for all the programming languages. We will work with JavaScript Koans. The mechanism is the following:

- You get an assertion that is not passing a **test**.
- You have to give the test the correct expected result to pass it.

We are going to test the code assertions through Jasmine. We have introduced here two new concepts: test and Jasmine. Let's see give a brief introduction about both of them.

## Testing

When you are coding, you have to be sure that what you are doing is working. More than that, when you are updating your existing code, you have to be 100% sure that your old code is still working. As our website becomes larger, it becomes more difficult to check that all our features are working as expected. How can we automatize this process?

Easy answer, huh? With **testing**.

### Introduction to testing

Testing allows us to check if the full set of features we have build are working as we expect. Sometimes you can create new features that override or damage the old ones. We avoid this with testing.

For now, you have enough with this brief introduction. We will learn testing in depth later on the course.

### Anatomy of a test

The syntax to create a test depends on the framework we use to create the tests. So we will explain the basic anatomy of a test with [pseudocode](https://en.wikipedia.org/wiki/Pseudocode).

Given a function with some parameters, we expect to get a result. If the result is what we are expecting, the test will pass. If we get an unexpected result, the test will fail. The passed test are marked in green, and the failed ones marked in red.

Let's create an small example to understand it better. Let's suppose we have the following function:

```javascript
function add (num1, num2) {
  // ...
}
```

If we pass as parameters to the `add` function the numbers 1 and 2, we should get as a result 3. So we are calling the `add` function with two numbers, and we expect from the function to return us the summatory of those numbers.

If we get 3 as a result, the test will pass. If we get whatever other result, the test will fail. In pseudocode, it would be something like this:

```
given the parameters 1 and 2 to the add function, we expect to get 3 as a result
```

This is the anatomy of a test. We have the knowledge to understand what is a test and how it works. Now we will introduce you a JavaScript framework to test our application.

## Jasmine

[Jasmine](http://jasmine.github.io/) is a framework used to test JavaScript code. If you take a look at the documentation, you will see that it has a lot of options to test our code. In this lab, we will work with `expects` and `matchers`.

### Describe, it, expect and matchers

To understand better what are the parts of the test in Jasmine, we will walk through an example. This is the first test we will find in our Koans:

```javascript
describe("the JavaScript language", function () {
  describe("has different types and operators", function() {
    it("considers numbers to be equal to their string representation", function() {
      expect(1 == "1").toBeTruthy();
      expect(1 != "1").toBeFalsy();
    });
  });
});
```

We will go through each different part of the test to explain all of them:

#### describe

It's used to group different tests on our code. This is very helpful when we see the tests results. Here we have two different describes:

- The first one will group **all** our tests. It has a description indicating that we are going to test the JavaScript language.
- The second one indicates us that we will test the different types and operators that JavaScript has.

As you can see, those are just information strings. We will see how they are shown in the test results page.

#### it

It receives an `string` that indicates what we will test. It has to be a clear description about what we are going to do. In our example, we are testing that JavaScript considers the numbers to be equal to their string representation.

#### expect

What we are expecting in the test. This function contains the expression we want to test. This expression has to coincide with the matcher of the test. If they agree, the test will pass. If they disagree, the test will fail.

#### matcher

The matchers are going to determine if a test will pass or not. The expression in the expect has to agree with the matcher. In our example, we are testing that JavaScript considers the numbers to be equal to their string representation. The matcher we selected is `.toBeTruthy()`.

So, the test `expect(1 == "1").toBeTruthy()` will pass. There is a huge list of matchers on testing. We don't have to know all of them for the exercise. We will work in testing in another lesson. The matchers we will use here are:

- `.toBeTruthy()` and `.toBeFalsy()`. We expect the expression to be truthy or falsy (difficult, huh?)
- `.toEqual()`. We expect the expression to be equal than the value passed as a parameter, and it has also to be the same type: i.e. `expect(1).toBe(1)`
- `.toBe()`. We expect the expression to be equal than the value passed as a parameter, but not necessary the same type: i.e. `expect(1).toBe("1")`

We will see there are a lot of matchers we can use. Right now we just need the ones described above to do the Koans.

### Execute our tests

Last, but not least, we need to execute our tests! First of all, fork and clone this repo into your Github account. Once you are done, open the file `SpecRunner.html` with your browser.

At the beginning you will see all the tests in green. This is because the tests we have to implement are commented.

All the tests are located inside the `spec` folder. Open the `koans.js` file and uncomment the following line:

```javascript
it("surprises me, NaN is not comparable with NaN", function() {
  expect(5 / "a").toEqual(5 / "a");
  //expect(typeof(NaN)).toEqual();
  expect(isNaN(5 / "a")).toBeTruthy();
});
```

When we uncomment the line and refresh de `SpecRunner.html` page, we will see something like that:

![](https://i.imgur.com/6aOBOPf.png)

**The main goal is not to finish all the tests. We want you to understand why each test is failing and how does JavaScript works in certain scopes.**

As we said, this is the first step to become a better developer. Good luck to all of you :)
