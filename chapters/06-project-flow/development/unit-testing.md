# Unit Testing

## Overview

Unit testing is a fundamental practice that ensures code quality and reliability. This document outlines the unit testing standards and practices at Trexis.

## Testing Framework

### C# Testing
```csharp
// Using MSTest
[TestClass]
public class CustomerServiceTests
{
    [TestMethod]
    public void GetCustomer_ValidId_ReturnsCustomer()
    {
        // Arrange
        var service = new CustomerService();
        int customerId = 1;

        // Act
        var result = service.GetCustomer(customerId);

        // Assert
        Assert.IsNotNull(result);
        Assert.AreEqual(customerId, result.Id);
    }
}
```

### JavaScript Testing
```javascript
// Using Jest
describe('CustomerService', () => {
    test('getCustomer returns customer for valid id', () => {
        // Arrange
        const service = new CustomerService();
        const customerId = 1;

        // Act
        const result = service.getCustomer(customerId);

        // Expect
        expect(result).toBeDefined();
        expect(result.id).toBe(customerId);
    });
});
```

## Test Structure

### Test Organization
```markdown
1. Test Class Structure
   - Setup methods
   - Test categories
   - Cleanup methods
   - Helper methods

2. Test Method Structure
   - Arrange section
   - Act section
   - Assert section
```

### Naming Conventions
```markdown
[MethodUnderTest]_[Scenario]_[ExpectedBehavior]

Examples:
- GetCustomer_ValidId_ReturnsCustomer
- SaveOrder_InvalidData_ThrowsException
- ProcessPayment_InsufficientFunds_ReturnsFalse
```

## Testing Patterns

### 1. Arrange-Act-Assert
```csharp
[TestMethod]
public void CalculateTotal_WithValidItems_ReturnsCorrectSum()
{
    // Arrange
    var calculator = new PriceCalculator();
    var items = new List<Item>
    {
        new Item { Price = 10.00m },
        new Item { Price = 20.00m }
    };

    // Act
    var total = calculator.CalculateTotal(items);

    // Assert
    Assert.AreEqual(30.00m, total);
}
```

### 2. Data-Driven Testing
```csharp
[TestMethod]
[DataRow(1, 2, 3)]
[DataRow(0, 5, 5)]
[DataRow(-1, 1, 0)]
public void Add_WithVariousInputs_ReturnsExpectedSum(
    int a, int b, int expected)
{
    // Arrange
    var calculator = new Calculator();

    // Act
    var result = calculator.Add(a, b);

    // Assert
    Assert.AreEqual(expected, result);
}
```

## Mocking

### Mock Objects
```csharp
// Using Moq
[TestMethod]
public void ProcessOrder_ValidOrder_CallsRepository()
{
    // Arrange
    var mockRepo = new Mock<IOrderRepository>();
    var service = new OrderService(mockRepo.Object);
    var order = new Order { Id = 1 };

    // Act
    service.ProcessOrder(order);

    // Assert
    mockRepo.Verify(r => r.Save(order), Times.Once);
}
```

### Stub Data
```csharp
public class CustomerRepositoryStub : ICustomerRepository
{
    public Customer GetById(int id)
    {
        return new Customer
        {
            Id = id,
            Name = "Test Customer"
        };
    }
}
```

## Test Coverage

### Coverage Goals
```markdown
1. Code Coverage Targets
   - Methods: 80%
   - Lines: 75%
   - Branches: 70%

2. Critical Areas
   - Business logic: 90%
   - Data access: 85%
   - API endpoints: 85%
```

### Coverage Reports
```markdown
1. Report Elements
   - Overall coverage
   - Per-class coverage
   - Uncovered lines
   - Branch coverage

2. Report Location
   - Build artifacts
   - Team dashboard
   - Quality gates
```

## Best Practices

### Writing Tests
1. **Single Responsibility**
   - One assertion per test
   - Clear purpose
   - Independent tests
   - Focused scenarios

2. **Maintainability**
   - Clear names
   - Shared setup
   - Helper methods
   - Clean teardown

3. **Reliability**
   - Consistent results
   - No external dependencies
   - Proper isolation
   - Error handling

### Test Data
1. **Test Data Management**
   - Controlled data
   - Known state
   - Cleanup process
   - Isolation

2. **Data Patterns**
   - Edge cases
   - Boundary values
   - Invalid inputs
   - Special cases

## Quality Checklist

### Test Review
- [ ] Proper naming
- [ ] Clear arrangement
- [ ] Single purpose
- [ ] Proper assertions
- [ ] Error cases
- [ ] Edge cases

### Coverage Review
- [ ] Meets targets
- [ ] Critical paths
- [ ] Error handling
- [ ] Edge cases
- [ ] Integration points

## Related Topics
- [Environment Setup](environment-setup.md)
- [Coding Standards](coding-standards.md)
- [Code Review](code-review.md)

## Navigation
- [Back to Project Flow](../README.md)
- [Back to Main](../../../README.md)
