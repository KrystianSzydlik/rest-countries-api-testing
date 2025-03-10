# Test Plan: REST Countries API Application

## 1. Introduction

### 1.1 Purpose

This test plan outlines the testing strategy, objectives, and approach for the REST Countries API application. It serves as a guide for QA activities and defines the scope and methodology for ensuring application quality.

### 1.2 Scope

This plan covers testing of:

- REST Countries API functionality
- Frontend application functionality and usability
- Integration between frontend and API
- Performance under various conditions
- Cross-browser compatibility

### 1.3 References

- Application codebase: [REST-Countries-API](https://github.com/KrystianSzydlik/REST-Countries-API)
- REST Countries API documentation: https://restcountries.com/
- Design mockups/requirements: [REST Countries API with color theme switcher](https://www.frontendmentor.io/challenges/rest-countries-api-with-color-theme-switcher-5cacc469fec04111f7b848ca)

## 2. Test Strategy

### 2.1 Testing Levels

The following testing levels will be performed:

- API Testing
- Integration Testing
- UI/Functional Testing
- Performance Testing

### 2.2 Testing Types

The following testing types will be conducted:

- Functional Testing
- Usability Testing
- Error Handling Testing
- Responsiveness Testing
- Cross-browser Testing

### 2.3 Tools and Technologies

- **API Testing**: Postman
- **Network Analysis**: Charles Proxy
- **Bug Tracking**: GitHub Issues
- **Test Management**: Markdown documentation in repository

## 3. Test Environment

### 3.1 Hardware

- Desktop/laptop with minimum 8GB RAM
- Mobile devices for responsive testing (or device emulators)

### 3.2 Software

- Operating System: Windows 10/11, macOS
- Browsers: Chrome (latest), Firefox (latest), Safari (latest), Edge (latest)
- Developer Tools for browsers
- Postman for API testing
- Charles Proxy for traffic analysis

### 3.3 Test Data

- Various country search queries
- Different region filter selections
- Edge cases (very long country names, countries with special characters)
- Countries with/without specific attributes (e.g., no capital city)

## 4. Testing Focus Areas

### 4.1 API Testing

Testing will focus on:

- Endpoint verification
- Response validation
- Error handling
- Performance benchmarking

#### 4.1.1 Key API Test Cases

1. Verify GET request for all countries returns 200 OK
2. Verify country search by name returns correct results
3. Verify region filtering returns only countries in that region
4. Verify fields parameter limits returned data
5. Verify error handling for invalid requests

### 4.2 UI Testing

Testing will focus on:

- Search functionality
- Filter functionality
- Country card display
- Responsive design
- Loading states

#### 4.2.1 Key UI Test Cases

1. Verify search input filters countries correctly
2. Verify region dropdown filters correctly
3. Verify country cards display correct information
4. Verify responsive layout on different screen sizes
5. Verify loading indicators during API requests

### 4.3 Integration Testing

Testing will focus on:

- Data flow from API to UI
- State management
- Error handling
- Data consistency

#### 4.3.1 Key Integration Test Cases

1. Verify API data is correctly displayed in UI
2. Verify search functionality correctly queries API
3. Verify error states are properly handled and displayed
4. Verify data consistency between API responses and UI display

### 4.4 Performance Testing

Testing will focus on:

- Response times
- Behavior under network throttling
- Load with many results
- Memory usage

#### 4.4.1 Key Performance Test Cases

1. Measure API response time for various requests
2. Test application behavior with network throttling
3. Test application with large result sets
4. Monitor memory usage during extended use

## 5. Defect Management

### 5.1 Defect Classification

Defects will be classified by severity:

- **Critical**: Application crash, data loss, security vulnerability
- **Major**: Core functionality failure, incorrect data processing
- **Minor**: UI issues, non-critical functional problems
- **Cosmetic**: Visual inconsistencies, typos

### 5.2 Defect Reporting Process

1. Identify and reproduce the issue
2. Document reproduction steps and environment
3. Capture evidence (screenshots, network logs)
4. Create GitHub issue with appropriate template
5. Assign severity and component labels
6. Link to test case if applicable

## 6. Test Deliverables

### 6.1 Before Testing

- Test Plan (this document)
- Test cases
- Postman collections

### 6.2 During Testing

- Defect reports
- Test progress reports
- Updated test cases

### 6.3 After Testing

- Test summary report
- API test results (Postman exports)
- Performance test results
- Bug tracking summary

## 7. Risks and Contingencies

### 7.1 Identified Risks

1. API availability issues
2. API rate limiting
3. Changes to API response structure
4. Browser compatibility issues

### 7.2 Contingency Plans

1. Mock API responses for testing when API is unavailable
2. Implement rate limiting handling in tests
3. Version API tests and update when changes occur
4. Prioritize testing on most common browsers first
