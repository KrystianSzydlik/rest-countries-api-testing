# API Test Cases: REST Countries API

## Test Case Format
Each test case follows this structure:
- **Test ID**: Unique identifier
- **Test Objective**: Purpose of the test
- **Preconditions**: Required setup before test execution
- **Test Steps**: Detailed procedure
- **Expected Results**: What should happen if the test passes
- **Actual Results**: Observed behavior (to be filled during testing)
- **Status**: Pass/Fail/Blocked (to be filled during testing)
- **Bug IDs**: Reference to any reported bugs (if applicable)
- **Notes**: Additional information

---

## Category: Basic API Functionality

### Test Case API-001: Verify GET Request to All Countries Endpoint

- **Test ID**: API-001
- **Test Objective**: Verify that the API returns all countries when making a GET request to the /all endpoint
- **Preconditions**: Postman is set up with the correct environment
- **Test Steps**:
  1. Send a GET request to `https://restcountries.com/v3.1/all`
  2. Observe the response status code
  3. Observe the response body
  4. Verify response time is acceptable
- **Expected Results**:
  - Response status code is 200 OK
  - Response body contains an array of country objects
  - Each country object contains essential fields (name, population, flags, etc.)
  - Response time is under 1000ms
- **Actual Results**: 
- **Status**: 
- **Bug IDs**:
- **Notes**: 

### Test Case API-002: Verify Country Search by Name

- **Test ID**: API-002
- **Test Objective**: Verify that the API returns correct countries when searching by name
- **Preconditions**: Postman is set up with the correct environment
- **Test Steps**:
  1. Send a GET request to `https://restcountries.com/v3.1/name/sweden`
  2. Observe the response status code
  3. Observe the response body
- **Expected Results**:
  - Response status code is 200 OK
  - Response body contains an array with a single country object for Sweden
  - Country object contains correct data for Sweden
- **Actual Results**: 
- **Status**: 
- **Bug IDs**:
- **Notes**: 

### Test Case API-003: Verify Region Filtering

- **Test ID**: API-003
- **Test Objective**: Verify that the API returns only countries from a specific region
- **Preconditions**: Postman is set up with the correct environment
- **Test Steps**:
  1. Send a GET request to `https://restcountries.com/v3.1/region/europe`
  2. Observe the response status code
  3. Observe the response body
  4. Check each country's region field
- **Expected Results**:
  - Response status code is 200 OK
  - Response body contains an array of country objects
  - All countries in the response have their "region" field set to "Europe"
- **Actual Results**: 
- **Status**: 
- **Bug IDs**:
- **Notes**: 

### Test Case API-004: Verify Fields Parameter

- **Test ID**: API-004
- **Test Objective**: Verify that the fields parameter limits the data returned in the response
- **Preconditions**: Postman is set up with the correct environment
- **Test Steps**:
  1. Send a GET request to `https://restcountries.com/v3.1/all?fields=name,capital,population`
  2. Observe the response status code
  3. Observe the response body structure
- **Expected Results**:
  - Response status code is 200 OK
  - Response body contains an array of country objects
  - Each country object only contains the requested fields (name, capital, population)
  - Other fields like "flags", "region", etc. are not present
- **Actual Results**: 
- **Status**: 
- **Bug IDs**:
- **Notes**: 

### Test Case API-005: Verify Error Handling for Invalid Country Name

- **Test ID**: API-005
- **Test Objective**: Verify that the API returns an appropriate error when an invalid country name is provided
- **Preconditions**: Postman is set up with the correct environment
- **Test Steps**:
  1. Send a GET request to `https://restcountries.com/v3.1/name/invalidcountryname`
  2. Observe the response status code
  3. Observe the response body
- **Expected Results**:
  - Response status code is 404 Not Found
  - Response body contains an appropriate error message
- **Actual Results**: 
- **Status**: 
- **Bug IDs**:
- **Notes**: 

---

## Category: Performance Testing

### Test Case API-006: Verify Response Time for All Countries

- **Test ID**: API-006
- **Test Objective**: Verify that the API response time for all countries is within acceptable limits
- **Preconditions**: Postman is set up with the correct environment
- **Test Steps**:
  1. Send a GET request to `https://restcountries.com/v3.1/all`
  2. Measure the response time
  3. Run the test multiple times at different times of day
  4. Calculate average response time
- **Expected Results**:
  - Average response time is under 1000ms
  - Response time is consistent across multiple runs
- **Actual Results**: 
- **Status**: 
- **Bug IDs**:
- **Notes**: 

### Test Case API-007: Verify Performance with Fields Parameter

- **Test ID**: API-007
- **Test Objective**: Compare API performance when requesting all fields vs. specific fields
- **Preconditions**: Postman is set up with the correct environment
- **Test Steps**:
  1. Send a GET request to `https://restcountries.com/v3.1/all`
  2. Measure the response time
  3. Send a GET request to `https://restcountries.com/v3.1/all?fields=name,capital,population`
  4. Measure the response time
  5. Compare the two response times
- **Expected Results**:
  - Response with filtered fields is faster than response with all fields
  - Both responses return 200 OK status
- **Actual Results**: 
- **Status**: 
- **Bug IDs**:
- **Notes**: 

---

## Category: Security Testing

### Test Case API-008: Verify CORS Headers

- **Test ID**: API-008
- **Test Objective**: Verify that the API includes appropriate CORS headers
- **Preconditions**: Postman is set up with the correct environment
- **Test Steps**:
  1. Send a GET request to `https://restcountries.com/v3.1/all`
  2. Examine the response headers
  3. Check for CORS-related headers (Access-Control-Allow-Origin, etc.)
- **Expected Results**:
  - Response includes appropriate CORS headers
  - Access-Control-Allow-Origin header is present
- **Actual Results**: 
- **Status**: 
- **Bug IDs**:
- **Notes**: 

### Test Case API-009: Verify HTTPS Support

- **Test ID**: API-009
- **Test Objective**: Verify that the API supports secure HTTPS connections
- **Preconditions**: Postman is set up with the correct environment
- **Test Steps**:
  1. Send a GET request to `https://restcountries.com/v3.1/all`
  2. Check that the connection uses HTTPS
  3. Attempt to send a request using HTTP instead of HTTPS
- **Expected Results**:
  - HTTPS connection is successful
  - HTTP connection either redirects to HTTPS or fails
  - SSL certificate is valid
- **Actual Results**: 
- **Status**: 
- **Bug IDs**:
- **Notes**: 
