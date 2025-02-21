# Coding Standards

## Overview

Coding standards ensure consistency, maintainability, and quality across all development efforts. These standards apply to all programming languages and platforms used at Trexis.

## General Standards

### Naming Conventions

#### Variables and Parameters
```csharp
// C# Examples
private string _firstName;           // Private field
public string FirstName { get; set;} // Property
var customerList = new List<Customer>();  // Local variable
```

```java
// Java Examples
private String firstName;            // Instance variable
public static final int MAX_COUNT;   // Constant
List<Customer> customerList;         // Collection
```

#### Methods and Functions
```csharp
public void ProcessCustomerData()    // Public method
private bool ValidateInput()         // Private method
protected virtual void OnClose()     // Protected virtual method
```

#### Classes and Interfaces
```csharp
public class CustomerService        // Service class
public interface IDataRepository    // Interface
public abstract class BaseEntity    // Abstract class
```

### Code Organization

#### File Structure
```markdown
1. Using/Import statements
2. Namespace declaration
3. Class/Interface declaration
4. Fields/Properties
5. Constructors
6. Methods
7. Nested classes
```

#### Method Organization
```markdown
1. Public methods
2. Protected methods
3. Private methods
4. Event handlers
```

## Language-Specific Standards

### C# Standards

#### Properties
```csharp
public class Customer
{
    public int Id { get; private set; }
    public string Name { get; set; }
    
    private string _internalValue;
    public string InternalValue
    {
        get { return _internalValue; }
        set
        {
            if (string.IsNullOrEmpty(value))
                throw new ArgumentException();
            _internalValue = value;
        }
    }
}
```

#### Exception Handling
```csharp
try
{
    // Operation that may throw exception
}
catch (SpecificException ex)
{
    // Handle specific exception
    Logger.LogError(ex);
}
catch (Exception ex)
{
    // Handle general exception
    Logger.LogError(ex);
    throw;
}
finally
{
    // Cleanup code
}
```

### SQL Standards

#### Naming Conventions
```sql
-- Tables
CREATE TABLE dbo.Customer
(
    CustomerId   INT          PRIMARY KEY,
    FirstName    VARCHAR(50)  NOT NULL,
    LastName     VARCHAR(50)  NOT NULL,
    CreatedDate  DATETIME     DEFAULT GETDATE()
)

-- Stored Procedures
CREATE PROCEDURE dbo.usp_GetCustomerById
    @CustomerId INT
AS
BEGIN
    SET NOCOUNT ON;
    
    SELECT *
    FROM dbo.Customer
    WHERE CustomerId = @CustomerId
END
```

#### Query Writing
```sql
-- Good Practice
SELECT c.CustomerId,
       c.FirstName,
       c.LastName,
       o.OrderDate
FROM dbo.Customer c
    INNER JOIN dbo.Order o ON c.CustomerId = o.CustomerId
WHERE c.Status = 'Active'
    AND o.OrderDate >= '2024-01-01'
ORDER BY o.OrderDate DESC;

-- Avoid
SELECT *
FROM Customer, Order
WHERE Customer.CustomerId = Order.CustomerId;
```

## Documentation Standards

### Code Comments

#### XML Documentation
```csharp
/// <summary>
/// Processes customer data and returns validation result
/// </summary>
/// <param name="customerId">The unique identifier of the customer</param>
/// <returns>True if processing successful, false otherwise</returns>
/// <exception cref="ArgumentException">Thrown when customerId is invalid</exception>
public bool ProcessCustomerData(int customerId)
{
    // Implementation
}
```

#### Inline Comments
```csharp
// Calculate total with tax
decimal total = subtotal * (1 + taxRate); // Good - explains why

decimal total = subtotal * 1.08; // Bad - magic number
```

## Best Practices

### Code Quality
1. **DRY (Don't Repeat Yourself)**
   - Use functions for repeated code
   - Create shared utilities
   - Implement common interfaces

2. **SOLID Principles**
   - Single Responsibility
   - Open/Closed
   - Liskov Substitution
   - Interface Segregation
   - Dependency Inversion

3. **Clean Code**
   - Clear names
   - Small functions
   - Minimal complexity
   - Good organization

### Performance
1. **Resource Management**
   - Proper disposal
   - Memory usage
   - Connection handling
   - Transaction scope

2. **Query Optimization**
   - Efficient joins
   - Proper indexing
   - Result limiting
   - Parameter usage

### Security
1. **Input Validation**
   - Type checking
   - Range validation
   - Format verification
   - Sanitization

2. **Data Protection**
   - Encryption
   - Access control
   - Secure storage
   - Safe transmission

## Code Review Guidelines

### Review Process
1. Code standards check
2. Logic verification
3. Security review
4. Performance review

### Review Checklist
- [ ] Follows naming conventions
- [ ] Proper error handling
- [ ] Adequate documentation
- [ ] Unit tests included
- [ ] Security considerations
- [ ] Performance optimization

## Related Topics
- [Environment Setup](environment-setup.md)
- [Unit Testing](unit-testing.md)
- [Code Review](code-review.md)

## Navigation
- [Back to Project Flow](../README.md)
- [Back to Main](../../../README.md)
