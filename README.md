# JMeter Test Plan - User Login

## Overview
This repository contains a JMeter test plan designed to test the login functionality of a web application. The test plan simulates user authentication against the `testphp.vulnweb.com` site.

## Features
- Simulates a user logging in with predefined credentials
- Includes assertions to validate response status code, page content, and response headers
- Utilizes a thread group with loop control to simulate multiple login attempts
- Implements a delay mechanism using timers to mimic real-world traffic
- Collects and reports test results using various JMeter listeners

## Test Plan Structure
The test plan consists of the following elements:

1. **Thread Group**
   - Simulates user login with 1 user performing 5 iterations.
   - Uses a defined ramp-up period of 1 second.

2. **HTTP Request Defaults**
   - Configures the default request settings (domain, protocol, and content type).

3. **HTTP Request Sampler**
   - Sends a `POST` request to `/userinfo.php` with predefined credentials (`uname=test`, `pass=test`).

4. **Assertions**
   - Validates that the response status code is `200`.
   - Checks for expected page elements like `<title>user info</title>`.
   - Ensures the correct response headers are received.

5. **Timers**
   - Introduces a uniform random timer to simulate realistic user interactions.

6. **Result Collectors**
   - `View Results Tree`
   - `Summary Report`
   - `Aggregate Report`

## Prerequisites
- [Apache JMeter 5.5](https://jmeter.apache.org/download_jmeter.cgi) installed on your system.

## Running the Test Plan
1. Open JMeter.
2. Load the test plan (`.jmx` file).
3. Click on the **Start** button to execute the test.
4. View the results in the configured listeners.

