# REST Countries API - QA Testing Project

## Project Overview

This repository contains a comprehensive QA testing project for the REST Countries API application. The application allows users to search for countries, filter by region, and view country details using the [REST Countries API](https://restcountries.com/).

### Application Under Test

The target application is a React-based front-end that:

- Displays country information from the REST Countries API
- Allows searching for countries by name
- Provides filtering by region
- Shows detailed information for selected countries

## Testing Approach

This project demonstrates a complete QA testing approach including:

1. **API Testing**: Verifying the external API functionality using Postman
2. **Integration Testing**: Testing the communication between frontend and API
3. **UI Testing**: Validating the user interface functionality
4. **Performance Testing**: Checking application response times under various conditions
5. **Bug Reporting**: Documenting identified issues with clear reproduction steps

## Tools & Technologies

- **Postman**: API testing and collection management
- **Charles Proxy**: Network traffic analysis and request inspection
- **Git/GitHub**: Version control and project management
- **JavaScript/TypeScript**: Test scripting (for automated tests)
- **Markdown**: Documentation

## Repository Structure

```
├── README.md                                       # Project overview (this file)
├── test-plan.md                                    # Comprehensive test strategy document
├── api-tests/                                      # Postman collections and API tests
│   ├── collections/                                # Exported Postman collections
│   ├── environments/                               # Postman environments
│   └── results/                                    # Test execution results and reports
├── integration-tests/                              # Tests verifying API and UI integration
├── ui-tests/                                       # UI-specific tests
├── performance-tests/                              # Performance testing scripts
├── bug-reports/                                    # Documented issues with screenshots
│   └── images/                                     # Screenshots of bugs
└── documentation/                                  # Additional testing documentation
    ├── test-cases/                                 # Detailed test cases
    ├── reports/                                    # Test summary reports
    └── api-documentation/                          # API testing documentation
        └── postman-collection-documentation.md     # Detailed Postman collection guide
```

## Getting Started

### Prerequisites

- Postman installed
- Charles Proxy installed
- Git installed
- Node.js and npm installed (for running automated tests)

### Running the Tests

1. Clone this repository
2. Import the Postman collections from the `api-tests/collections` folder
   - For detailed information about the collection structure and test scripts, refer to the [Postman Collection Documentation](documentation/api-documentation/postman-collection-documentation.md)
3. Run the collections to execute API tests
4. (Additional instructions for other test types...)

## Test Summary

| Test Type   | Total Tests | Passed | Failed | Incomplete |
| ----------- | ----------- | ------ | ------ | ---------- |
| API         | 0           | 0      | 0      | 0          |
| UI          | 0           | 0      | 0      | 0          |
| Integration | 0           | 0      | 0      | 0          |
| Performance | 0           | 0      | 0      | 0          |

## Bug Summary

| Severity | Count | Open | Closed |
| -------- | ----- | ---- | ------ |
| Critical | 0     | 0    | 0      |
| Major    | 0     | 0    | 0      |
| Minor    | 0     | 0    | 0      |
| Cosmetic | 0     | 0    | 0      |

## Author

Krystian Szydlik - [LinkedIn](https://www.linkedin.com/in/krystian-szydlik/) | [GitHub](https://github.com/KrystianSzydlik)
