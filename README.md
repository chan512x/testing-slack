# testing-slack
This project automates Slack workflows using Selenium WebDriver with Java. It includes testing functionality for signing in, navigating channels, creating channels, sending messages, and adding colleagues.

## Prerequistes
- Java Development Kit (JDK) installed (version 11 or higher).
- Maven (for dependency management).
- Geckodriver for Firefox (managed automatically with WebDriverManager).
- Selenium WebDriver and JUnit libraries.

## Setup

1. Clone the project

```bash
  git clone https://github.com/chan512x/testing-slack.git
```

 2. Configure properties file: In input.properties, set your Slack URLs, channel paths, valid/invalid emails, and messages.

 3. Project Structure:

-  ```src/test/java/input.properties```: stores configurable properties such as URLs, XPaths, and messages.

-  ```selenium_slack/MainTest.java```: Main test file, containing methods for each automated task.

## Usage

### Running Tests
To execute the tests, run the MainTest class. You can use the command:
``` mvn test ```
### Key Features
1. **Sign In Test**: Opens Slack, verifies the title, opens the sign-in page, and tests email format validity.
   - Invalid email attempts.
   - Manual verification prompt for two-factor authentication.
2. **Channel Navigation and Messaging**:
   - Navigates to a specified Slack channel.
   - Sends a preset message to the channel.
3. **Channel Creation**:
   - Attempts to create a new channel.
   - If a channel name is already taken, it retries with an alternate name.
4. **Adding Colleagues**:
   - Adds a new colleague to a direct message.
   - Handles errors and retries for invalid inputs.

## Code Structure
The main class ``` MainTest``` contains the following methods:

- ```signInTest()```: Manages the Slack sign-in process.
- ```verifyEmailFormatUsingWebsite()```: Validates email format during login.
- ```navigateToChannelAndSendMessage()```: Sends a message in a specific channel.
- ```addAndCreateChannel()```: Automates channel creation and name validation.
- ```navigateAndAddColleagues()```: Adds colleagues to Slack with retries for errors.

## Known Limitations
- Manual intervention for two-factor authentication during the login process.
- Limited retries and error handling for element interactions.

## Troubleshooting
If tests fail:

- Verify your properties in input.properties.
- Ensure the Firefox browser and Geckodriver are correctly set up.

## Contributions
Feel free to submit issues, fork the repository, or open pull requests.


