# Testing Pyramid

* Why do we test?

    1. Ensure Functionality
        • Verify the application works as intended

    2. Increase Flexibility & Reduce Fear
        • Allows confident refactoring and modifications
        • Tests highlight broken parts when changes occur

    3. Facilitate Collaboration
        • Specifications serve as a communication tool among developers

    4. Documentation
        • Well-written tests can document behaviour of the codebase


* What do we test?

    1. Public Interface
        • Test functions that the outside world will use and rely on
        • Prioritise the most important and complex parts of the interface


* The Testing Pyramid

    1. Unit Tests
        • Test individual components in isolation
        • Fast to write and run

    2. Integration Tests
        • Test interactions between components
        • Ensure coherent functionality of combined units

    3. End-to-End (E2E) Tests
        • Test the entire application
        • Closest to testing actual user experience
        • Slowest to write and run

Practical Exmple: Chess Game
    • Unit Tests: Test individual pieces (e.g. pawn, knight)
    • Integration Tests: Test interactions between pieces and the board
    • E2E Tests: Test a complete game scenario

Testing Pyramid Strategy
    • Base: Many unit tests
    • Middle: Medium amount of integration tests
    • Fewer: end-to-end tests

Benefits
    • Faster identification of errors
    • Efficient testing process for large applications

* Key Takeaways
    • Understand the importance of testing
    • Know what parts of the application to test
    • Familiarise with the testing pyramid to structure tests effectively


# Test-Driven Development (TDD)

* What is TDD?

    • Test-Driven Development: A practice where tests are written before the code to ensure the code works as expected
    • Steps in TDD:
        1. Red: Write tests and watch them fail
        2. Green: Write the minimum code to pass the tests
        3. Refactor: Optimise and clean up the code while ensuring tests still pass

* Motivations for TDD:
    • Ensure Code Works: Writing tests first guarantees functionality
    • Testable Code: Code written to pass tests is inherently testable
    • Facilitates Collaboration: Allows developers to add and test new code without breaking existing features
    • Avoids Unnecessary Code: Encourages writing only the needed code, reducing bloat
    • Enforces Modularity: Promotes writing small, testable, and modular chunks of code
    • Clear Understanding: Ensures developers know what the code should achieve through writing tests

* Three Steps of TDD:

    1. Red:
        • Write tests that fail
        • Ensures no false positives

    2. Green:
        • Write just enough code to pass the tests
        • Focus on making tests pass, not on writing perfect code

    3. Refactor:
        • Improve and clean up the code
        • Ensure the code is maintainable and readable without breaking functionality

* Advantages of TDD
    • Confidence in Code: Specs describe expected behaviour, reducing fear of changes
    • Efficient Development: Short development cycles with small, manageable tests
    • Code Quality: High-quality, maintainable, and modular code

* Key Takeaways
    • TDD Cycle: Red (fail), Green (pass), Refactor (optimise)
    • Benefits: Ensures functionality, facilitates collaboration, enforces modularity, and reduces unnecessary code
    • Practice: Write tests first, then code, and continuously refactor for optimal results


# Determining Common Test Cases

Knowing how much to test can be challenging. Too many tests can slow down development, while too few can miss key errors or edge cases. This guide will help you approach writing specs for common use cases, unintuitive cases, and edge cases.

* Two Main Reasons for Test Specs
    1. Specification: Tests are created before writing code to specify what should be built, guiding the developer
    2. Regression Prevention: Tests prevent future changes from breaking the code. Good initial tests help maintain this

* Example: Sticker Distribution Algorithm
Andrea, a kindergarten teacher, wants to give stickers to children based on their performance ratings. Each child should get at least one sticker, with higher-rated children getting more stickers than their neighbours.

* Test Cases

    1. Common Use Case:
        • For ratings `[1, 2, 3, 4]`, the stickers needed are `1 + 2 + 3 + 4 = 10`
        ```js
        describe('Stickers', function () {
            it('should give 10 stickers to students ranked [1, 2, 3, 4]', function () {
                const stickers = countStickers([1, 2, 3, 4]);
                expect(stickers).to.equal(10);
            });
        });
        ```

    2. Adding a Non-Unique Test:
        • Adding a similar test for `[1, 2, 3, 4, 5]` doesn't test anything new

    3. Unintuitive Case:
        • For `[1, 2, 3, 4, 3]`, the total stickers needed are `1 + 2 + 3 + 4 + 1 = 11`
        ```js
        it('should give a lower-ranked neighbor 1 sticker', function () {
            const stickers = countStickers([1, 2, 3, 4, 3]);
            expect(stickers).to.equal(11);
        });
        ```

    4. Complex Unintuitive Case:
        • For `[1, 2, 3, 4, 3, 1]`, the total is `1 + 2 + 3 + 4 + 2 + 1 = 13`
        ```js
        it(`should raise the sticker count if lower than its neighbour`, function () {
            const stickers = countStickers([1, 2, 3, 4, 3, 1]);
            expect(stickers).to.equal(13);
        });
        ```

    5. Backward Increase:
        • For `[1, 3, 5, 4, 3, 2, 1]`, the total is `1 + 2 + 5 + 4 + 3 + 2 + 1 = 18`
        ```js
        it('should increase the sticker count far backwards if needed', function () {
            const stickers = countStickers([1, 3, 5, 4, 3, 2, 1]);
            expect(stickers).to.equal(18);
        });
        ```

* Testing Edge Cases

    • Improper Inputs:
    ```js
    it('should return `undefined` with improper inputs', function () {
        const stickers = countSticker(['one', 'two', 'three']);
        expect(stickers).to.equal(undefined);
    });
    ```

    • Empty Array:
    ```js
    it('should return 0 with an empty array', function () {
        const stickers = countStickers([]);
        expect(stickers).to.equal(0);
    });
    ```

    • Large Inputs:
    ```js
    it('should work with 10000 students', function () {
        let largeRankings = [];
        let total = 0;
        for (let i = 1; i <= 10000; i++) {
            largeRanking.push(i);
            total += i;
        }
        const stickers = countStickers(largeRankings);
        expect(stickers).to.equal(total)
    });
    ```
    • Be cautious with large input tests as they can slow down development. Only include them if they are realistic for the problem domain

* Summary
    • Learnt how to write test cases for common, unintuitive, and edge cases
    • Proper testing helps to understand problems better and ensures robust code, which is critical for reliable software development
