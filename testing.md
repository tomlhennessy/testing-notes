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
