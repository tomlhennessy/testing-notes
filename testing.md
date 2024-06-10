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
