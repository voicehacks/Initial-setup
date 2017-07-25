## Summary
This will take you through the steps of configuring your skill in the developer portal. 

### Configure your skill in the developer portal
1. First, login to the [Amazon developer Portal](https://developer.amazon.com/login.html).  If you haven't done so already, just create a free account.
1. From the top navigation bar, select **Alexa**
1. On the icon labeled **Alexa Skills Kit**, click **Get Started**
1. Select add a new skill
1. Choose a name for your skill. We recommend naming this something similar to your Lambda Function name, though it's not required.
1. Create an invocation phrase. We recommend using a simple one- to three-word phrase that makes sense for your skill. A user will utter the phrase "Alexa, open {your invocation phrase}." to begin the skill.  In this example, Alexa is the wake word, open is the launch phrase, and whatever you have entered as the invocation name will be the invocation name or phrase. [Here](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/supported-phrases-to-begin-a-conversation) you can find more info on how users invoke custom skills.
1. Choose save
1. Click next
1. At the top of this page, you should see a button to launch the skill builder. Click that button to launch it.
1. Click the blue "Add an Intent" sectioin of the box on the left to add our first user intent. In the field that appears, enter the name of your first intent, (For instance, myFirstIntent) then click the Create Intent button. 
    - Now we can define the utterances that the user will speak to run this specific intent in your lambda. Enter all the phrases that you think users might say to interact with your skill. The more phrases you enter, the better the results.
    - What if we expect our user to ask the same thing about different objects? This is where slots are useful. Let's change the utterance in our example to say "can I have a {food} yet?" On the right, you should see a field called intent slots with a create a new slot field. type 'food' into this and then click Add. Now we can choose a slot type.  We can either find a type that has been [defined by Amazon](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/built-in-intent-ref/slot-type-reference#list-types) or create our own. Now click "Save Model", then "Build Model" (this process can take a few minutes)
    - Once our model is finished building, click configuration for the final steps in our setup. 
1. Next to Service Endpoint Type, select the AWS Lambda ARN (Amazon Resource Name) radio button, then North America. Now switch over to the browser window from our previous section, where we started to build our Lambda function. At the top right of this page, below your name, you will see something that looks like this: **PHOTO HERE** ARN - arn:aws:lambda:us-east-1:763834435538:function:snackMachine copy everything starting with the lowercase arn: and to the right. Paste this into the text field in your developer portal, under North America. Click Save, then click Next.  Now we can type the utterances that we previously defined as samples into the "Enter Utterance" field and hit enter. If our code is working, we will see both the Lambda request and response that our utterance invokes.  You can push "Listen" under your response field to hear a sample of Alexa's response to your code.  

## Next Steps
Well done! You've now created a basic Alexa skill and configured your skill to continue adding features and functionality. We'll discuss how to make your skill more unique and robust in the modules found [here](../modules)
