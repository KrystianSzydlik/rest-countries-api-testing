# REST Countries API - Postman Collection Documentation

This document provides an overview of the Postman collection created for testing the REST Countries API. The collection is organized into folders based on test categories, with each request containing pre-request scripts, tests, and examples.

## Collection Structure

```
REST Countries API Tests/
├── Basic Functionality/
│   ├── Get All Countries
│   ├── Search Country by Name
│   ├── Filter Countries by Region
│   └── Get Country by Code
├── Field Filtering/
│   ├── Basic Fields
│   ├── Name Fields Only
│   └── Custom Field Combination
├── Error Handling/
│   ├── Invalid Country Name
│   ├── Invalid Region
│   └── Invalid Field
└── Performance Tests/
    ├── Response Time - All Countries
    ├── Response Time - Filtered Fields
    └── Response Time - Region Filter
```

## Environment Variables

| Variable       | Initial Value                  | Description                         |
| -------------- | ------------------------------ | ----------------------------------- |
| `base_url`     | https://restcountries.com/v3.1 | Base URL for the REST Countries API |
| `country_name` | sweden                         | Sample country name for testing     |
| `region`       | europe                         | Sample region for testing           |
| `fields`       | name,capital,population        | Sample fields for filtering         |

## Request Details

### Get All Countries

- **Method**: GET
- **URL**: {{base_url}}/all
- **Description**: Retrieves information about all countries
- **Tests**:
  - Verify status code is 200
  - Verify response time is acceptable
  - Verify response is an array
  - Verify each country has required fields

### Search Country by Name

- **Method**: GET
- **URL**: {{base_url}}/name/{{country_name}}
- **Description**: Searches for countries by name
- **Tests**:
  - Verify status code is 200
  - Verify response contains the correct country
  - Verify country data is accurate

### Filter Countries by Region

- **Method**: GET
- **URL**: {{base_url}}/region/{{region}}
- **Description**: Retrieves countries in a specific region
- **Tests**:
  - Verify status code is 200
  - Verify all countries have the correct region value
  - Verify response time is acceptable

### Basic Fields

- **Method**: GET
- **URL**: {{base_url}}/all?fields={{fields}}
- **Description**: Retrieves only specific fields for all countries
- **Tests**:
  - Verify status code is 200
  - Verify response only contains requested fields
  - Verify response time is better than full response

## Test Script Examples

### Basic Status Code Test

```javascript
pm.test('Status code is 200', function () {
  pm.response.to.have.status(200);
});
```

### Response Time Test

```javascript
pm.test('Response time is acceptable', function () {
  pm.expect(pm.response.responseTime).to.be.below(1000);
});
```

### Response Structure Test

```javascript
pm.test('Response is an array', function () {
  var jsonData = pm.response.json();
  pm.expect(Array.isArray(jsonData)).to.be.true;
});
```

### Field Validation Test

```javascript
pm.test('Response only contains requested fields', function () {
  var jsonData = pm.response.json();
  var allowedFields = pm.variables.get('fields').split(',');

  // Check first item in array
  var firstCountry = jsonData[0];
  var countryFields = Object.keys(firstCountry);

  // Every country field should be in the allowed fields list
  // (except for name which is an object)
  countryFields.forEach(function (field) {
    if (field !== 'name') {
      pm.expect(allowedFields).to.include(field);
    }
  });
});
```

## Exporting and Sharing

To use this collection:

1. Export the collection from Postman as a JSON file
2. Save the file in the `api-tests/collections` directory
3. Export the environment from Postman
4. Save the environment file in the `api-tests/environments` directory

The collection can be imported by other team members or used in CI/CD pipelines for automated testing.

## Test Results

After running the collection, you can:

1. Export the run results from Postman
2. Save the results in the `api-tests/results` directory
3. Update the test summary in the main README.md file
