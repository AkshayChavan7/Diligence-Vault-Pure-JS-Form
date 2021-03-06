# DiligenceVault- Pure JS Form

**Problem Statement:**

The goal of this challenge is to build a interface to record user survey.

1. The user opens the page & should be presented with multiple questions & appropriate input fields to record the answers
2. Questions marked as "required" cannot be left blank before submitting the survey.
3. Once the user submits a valid form, hide the form & show a success alert that the form is now successfully submitted.

The project skeleton contains a lightweight server written in Nodejs for serving the required endpoints to load the survey related information.

You should:
  - Pretend that this is as production-quality code for review. So, write modular & readable code.
  - Use any HTML5 feature supported by current Chrome
  - Make your submission final & you cannot make any changes once submitted
  - Make the UI as intuitive as you can.

You may:
  - Include Twitter Bootstrap or any other CSS frameworks for styling purposes (only CSS & not JS)
  - Use Es6 or Typescript or Coffescript
  - Be as creative as possible with the UI/UX design but that's not the primary goal.

You should not:
  - Use any frameworks or JS libraries(e.g; AngularJS, jQuery, etc)
  - modify the server


API reference

/                   serves the index.html
/questions          returns a JSON response representing the questions that needs to be rendered
/options?question=  return a bunch of options for the user to choose from

Schema definition

Each object in the array that is returned by `/questions` API has the following properties, following is the explanation of each of them

title      - Contains the question text
type       - Determines which input widget that needs to be rendered
             text     -> render a text field
             email    -> render an email field with email format validation
             number   -> render a number field with numeric validation(just check if the number is 10 digits or not)
             rating   -> render a widget to capture a value between 1 and 10 (see attachment for how the widget should look, feel free to use your own version of design for this if you think you can come up with a better one)
             radio    -> render a radio group so that at most one option can be selected
             checkbox -> render a checkbox group so that user can select multiple options
             textarea -> render a textarea input to capture multiline text input
mandatory  - Determines whether a given question is optional or not, if the user submits the
             form without filling a mandatory question. The UI needs to show appropriate validation & not let user submit the form
has_options - Determines whether a given question has options(checkbox & radio), if a given
              question has options, the UI needs to make an additional request to fetch those options at the endpoint (/options?question=QUESTION_ID), for example: if the question has the "id" set as "1" (GET /options?question=1) returns you the option information

Each object in the array that is returned by `/options?question=<id>` API has the following properties.

label       - Use this to display a label for each option to the user
value       - Use this to capture the value of a given option selection

You need not make any request for form submission.

**Solution Screenshots:**

![Landing Page](https://raw.githubusercontent.com/AkshayChavan7/Diligence-Value-Pure-JS-Form/main/screenshots/ss1.png)

![Submission Window](https://raw.githubusercontent.com/AkshayChavan7/Diligence-Value-Pure-JS-Form/main/screenshots/ss2.png)

#
&copy; Akshay Chavan
