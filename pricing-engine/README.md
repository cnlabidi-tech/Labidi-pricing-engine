double[] prices = {100.0, 200.0};
%23 Pricing Engine

A Java-based pricing and discount calculation engine with Gradle build, unit tests (JUnit 5) and simple Python integration tests.

## Table of Contents
- [Table of Contents](#table-of-contents)
- [Project Overview](#project-overview)
- [Project Structure](#project-structure)
- [Technology](#technology)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Build](#build)
  - [Run the app (example)](#run-the-app-example)
- [Testing](#testing)
  - [Unit tests (Java / JUnit)](#unit-tests-java--junit)
  - [Integration tests (Python)](#integration-tests-python)
- [Example Usage (Java)](#example-usage-java)
- [Contributing](#contributing)
- [License](#license)

## Project Overview
Calculates final price of orders based on item prices, quantities, customer type (REGULAR / VIP) and discount codes. Produces a breakdown: subtotal, discounts, tax and final price.

## Project Structure
```
pricing-engine/
├── app/                        # Application module (entry point)
├── list/                       # Core pricing engine library
│   ├── src/main/java/.../list/ # PricingEngine, PricingResult, calculators, strategies
│   └── src/test/java/.../list/ # Unit tests (JUnit 5)
├── utilities/                  # Utility code
├── simple_integration_test.py  # Python integration tests
├── build.gradle.kts
└── settings.gradle.kts
```

## Technology
- Language: Java 11+
- Build: Gradle (use the included `gradlew`)
- Unit tests: JUnit 5
- Integration tests: Python (pytest / simple scripts)

## Getting Started

### Prerequisites
- JDK 11 or newer
- Python 3.8+ (for integration tests)

### Build
```bash
./gradlew clean build
```

### Run the app (example)
```bash
./gradlew run
```

## Testing

### Unit tests (Java / JUnit)
```bash
./gradlew test
```

### Integration tests (Python)
```bash
python simple_integration_test.py
```

## Example Usage (Java)
```java
PricingEngine engine = new PricingEngine();
double[] prices = {100.0, 200.0};
int[] quantities = {1, 2};

PricingResult result = engine.calculateWithDetails(prices, quantities, "VIP", "SAVE10");
System.out.println(result.getDetailedBreakdown());
```

Expected formatted output example:
```
Subtotal:          $500.00
Customer Discount: -$100.00
Code Discount:     -$10.00
Total Discount:    -$110.00
Tax (15%):         +$58.50
Final Price:       $448.50
```

## Contributing
- Create a feature branch: `git checkout -b feature/your-feature`
- Run tests: `./gradlew test`
- Commit: `git commit -m "Add feature: description"`
- Push & open a Pull Request

## License
MIT

---
Created as part of a Software Engineering Lab on Refactoring & Testing