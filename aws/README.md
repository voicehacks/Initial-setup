## Summary
This will take you through the initial steps to configure your Alexa skill.  

### Create a function in Amazon Web Services (AWS)
1. First, login to the [AWS Management Console](https://aws.amazon.com/).  If you haven't done so already, just create a free account.
1. Make sure that your region in the top right corner is showing as N. Virginia. If needed, just click the current region (next to your name) and change it to N. Virginia
1. In the search box, type in "Lambda", then select lambda from the dropdown
1. You should be on the next screen. Click the blue button that says "Create a Lambda function".
1. Blueprints are sample configurations of event sources and Lambda functions. ** IMPORTANT ** For this tutorial, we will be using the _alexa-skill-kit-sdk-factskill_. It should be on the top right. You are more than welcome to start from scratch, but for this tutorial, we recommend that you use the above named template. 
1. Now we'll configure our trigger.  If you think about this in a programmatic sense, we are telling our lambda where the invocation will come from.  Click the box to the left of the Lambda icon, it should look like a dotted outline.  A dropdown appears; select Alexa Skills Kit.  Then click the Next button on the bottom right of the page. 
1. We've now arrived at what will become a familiar page while we build this skill.  Before we dive into the code, let's take a moment to name our skill and (only if you plan on publishing) add a brief description. 
1. Now copy this code and paste it into the editor just below where you named your function:
```
        var Alexa = require('alexa-sdk');

        exports.handler = function(event, context, callback) {
            var alexa = Alexa.handler(event, context);

            // alexa.dynamoDBTableName = 'YourTableName'; // creates new table for userid:session.attributes

            alexa.registerHandlers(handlers);
            alexa.execute();
        };

        var handlers = {
            'LaunchRequest': function () {
                this.emit('MyIntent');
            },

            'MyIntent': function () {
                this.emit(':tell', 'Hello World from Alexa!');
            }
        };
```

1. Next, scroll below the code editor field to the section titled "Lambda function handler and role" and select "create a custom role" from the dropdown next to Role\*. In the new browser window that has opened, make sure that the dropdown next to IAM Role is showing as lambda_basic_execution. Then click the blue "Allow" button. Now back at our Lambda function, lambda_basic_execution should be showing next to Existing Role\*. Click the Next button at the bottom right. 
1. We're now asked to review our function. For this exercise, just make sure that your Trigger is showing Alexa Skills Kit and the name and description are what you chose. Also double check that the Existing role\* is lambda_basic_execution. If everything is correct, click "Create Function".

## Great work!

Way to go, you've completed most of the steps to connect Alexa's voice recognition to your program.  Now, we'll configure the rest in our [second section](../skills)
