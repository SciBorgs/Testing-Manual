# Technicals

## Introduction

Unit testing is a method of testing blocks (or units) of code. JUnit is a common unit testing framework for Java. We will be using JUnit 5.

## Setting up JUnit 5

1. Add the following clauses to **build.gradle**:
    ```
    test {
        useJUnitPlatform()
    }
    ```
    ```
    dependencies {
        testImplementation ‘org.junit.jupiter:junit-jupiter-api:5.8.1’ 
        testRuntimeOnly ‘org.junit.jupiter:junit-jupiter-api:5.8.1’
    }
    ```
2. Instal VSC extension *Test Runner for Java*
3. Create path `src/test/java`. All tests should be at this address

## Imports

1. Assertions:
    ```
    import static org.junit.jupiter.api.Assertions.*;
    ```
2. Everything else:
    ```
    import org.junit.jupiter.api.*;
    ```
3. Remember to import whatever file you're testing!
4. Sim (**come back later**)

## Structure

1. Testing Classes
    - All testing code is written inside Testing Classes
    - **add link to example**
2. Testing Suites
    - Testing Suites are sets of testing classes
    - **add link to example**

## Types of methods

There are many different types of methods to use inside of testing classes, and different kinds of methods are proceeded by different annotations

1. Test methods
    - These are the actual tests
    - Special types of test methods:
        1. Repeated Tests
            - Method repeats a specified number of times
            - Helps to ensure consistency
        2. Parameterized Tests
            - Method repeats multuiple times with different parameters
            - There are specified sources that it draws from, repeating once with each value
            - Types of sources:
                1. ValueSource: An array of literal parameters
                2. NullSource
                3. EmptySource
                4. Etc.
            - Increases efficiency/avoids redundancies
2. BeforeEach
    - These methods run before each test in a class
    - Often used to create an object
3. AfterEach
    - These methods run after each test in a class
    - Often used to destroy an object
4. BeforeAll
    - This is the first method to run in a testing calss
5. AfterAll
    - This is the last method to run in a testing class

## Annotations

1. `@Test`
    - Purpose
      - Goes before regular testing methods
    - Variations
      - Expected exception: `@Test( expected =` ***`insert expected exception`***`)`
2. `@BeforeEach`
    - Purpose
      - Goes before BeforeEach methods
3. `@AfterEach`
    - Purpose
      - Goes before AfterEach methods
4. `@BeforeAll`
    - Purpose
      - Goes before BeforeAll methods
5. `@AfterAll`
    - Purpose
      - Goes before AfterAll methods
6. `@Disabled`
    - Purpose
      - Goes before test methods or test classes
      - Indicates that the test(s) it precedes should not be run
7. `@Timeout(seconds)`
    - Purpose
      - Goes before test methods
      - Indicates that the test it precedes should timeout after the given number of seconds
8. `@Tag(tag name)`
    - Purpose
      - Goes before test methods or classes
      - Categorizes tests so that you can filter what tests based on the names
      - Generally used to filter what tests are included in Testing Suites
      - For instance, if you tagged all fast tests with one tag, you could make a Testing Suite that only includes fast tests
9.  `@IncludeTags(tag)`
    - Purpose
      - Goes in Testing Suites
      - Filters tests included in the suites by their tag
10. `@DisplayName(name)`
    - Purpose
      - Goes before test methods
      - The given name is displayed if the test fails
11. `@RepeatedTest(# of repititions)`
    - Purpose
      - Goes before RepeatedTest methods
12. `@ParameterizedTest`
    - Purpose
      - Goes before ParameterizedTest methods
13. `@ValueSource(array_name = {values}`
    - Purpose
      - Goes before ParameterizedTest methods
      - Includes sources for the test it precedes to draw from
14. `@NullSource`
    - Purpose
      - Goes before ParameterizedTest methods
      - The test it precedes will run once with a null parameter
15. `@EmptySource`
    - Purpose
      - Goes before ParameterizedTest methods
      - The test it precedes will run once with an empty parameter
16. More annotations can be found [here](https://junit.org/junit5/docs/current/user-guide/#writing-tests-annotations)

## Assertions and Assumptions

### Assertions 

Assertions go inside tests, and whether or not they succeeds decides whether or not the test does. Most tests have assertions, and those without fail only when an exception is thrown. There are many different kinds of assertions to choose from.

1. `assertEquals(expected, actual, optionalFailMessage)`
    - asserts that expected and actual are equal
2. `assertNotEquals(unexpected, actual, optionalFailMessage)`
    - asserts that unexpected and actual are not equal
3. `assertSame(expected, actual, optionalFailMessage)`
    - asserts that expected and actual refer to the same object
4. `assertNotSame(unexpected, actual, optionalFailMessage)`
    - asserts that uexpected and actual refer to different objects
5. `assertTrue(condition, optionalFailMessage)`
    - asserts that condition is true
6. `assertFalse(condition, optionalFailMessage)`
    - asserts that condition is false
7. `assertNull(object, optionalFailMessage)`
    - asserts that object is null
8. `assertNotNull(object, optionalFailMessage)`
    - asserts that object is not null
9.  `assertThrows(expectedExceptionType, executable, optionalFailMessage)`
    - asserts that executing executable returns and throws an exception of expectedExceptionType
10. `assertTimeout(timeout, executable, optionalFailMessage)`
    - asserts that executing executable takes no longer than timeout is exceeded
11. `fail(optionalFailMessage)`
    - automatically fails the test
12. `assertAll(executables...)`
    - asserts that all executables throw no exceptions
13. More assertions can be found [here](https://junit.org/junit5/docs/5.0.1/api/org/junit/jupiter/api/Assertions.html)

### Assumptions

Assumptions also go inside of tests, but unlike assertions, a failed assumption does not cause a failed test. Instead, when an assumption fails, the test that it's in is aborted. In other words, including assumptions in tests makes the tests conditional, only running if the assumption is true. There are two main kinds of assumptions.

1. `assumeTrue(assumption, optionalAbortMessage)`
    - aborts test unless assumption is true
2. `assumeFalse(assumption, optionalAbortMessage)`
    - aborts test unless assumption is false

### AssumingThat

The assumeThat method is a combination of an assertion and an assumption.

1. `assumingThat(assumption, executable)`
   - if assumption is true, runs executable
     - If the executable throws an exception, the test method fails 
   - if assumption is false, does nothing

## Sim

**COME BACK**

## Helpful links

1. [Official JUnit 5 user guide](https://junit.org/junit5/docs/current/user-guide/)
2. [Other helpful JUnit 5 guide](https://www.baeldung.com/junit-5)
3. [JUnit 5 API](https://junit.org/junit5/docs/5.0.1/api/)

# Procedures