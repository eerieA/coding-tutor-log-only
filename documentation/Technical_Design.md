# Technical Design Document

Vivaan Wadhwa, Samuel Salitra, Brandon Kato, Richard Cao, Jade Duan

*Note: This document was converted from [our original](https://docs.google.com/document/d/1GsRyazWEEgTnIDQ9AvHCPnttqBSTSK709P5eyh0ctwk/edit?usp=sharing) Google Spreadsheet.*

# Table of Contents
- [User Stories](#user-stories)
  - [Epic 1: Educator dashboard](#epic-1-educator-dashboard)
  - [Epic 2: User Consent and Data Collection](#epic-2-user-consent-and-data-collection)
  - [Epic 3: User Experience and Interactions](#epic-3-user-experience-and-interactions)
- [Technical Design](#technical-design)
  - [User Interface](#user-interface)
  - [REST API](#rest-api)
  - [Backend](#backend)
  - [Test Coverage](#test-coverage)
- [Table of Contributions](#table-of-contributions)
  

# User Stories

### Epic 1: Educator dashboard

#### User story 1

**Step 1: Role-Goal-Benefit**

As an educator, I want to be able to see student question solving statistics, so that I can assess their skills as computer scientists

**Step 2: Notes, Limitations or Clarifications**

* The statistics should include metrics such as the number of problems attempted, completion rate, time spent on each problem, and accuracy.  
* Statistics should be accessible for individual students and aggregated for the entire class.  
* Data should be presented in a clear, visual format, such as charts or graphs.  
* Educators should be able to filter statistics by date range, difficulty, and topic.

**Step 3: Definition of Done and Validation**

* Educators are able to access a statistics dashboard that displays individual and class-level performance metrics.  
* The dashboard allows filtering and sorting of statistics by various criteria.  
* Educators can view detailed statistics for individual students, including problem-solving trends and areas of improvement.  
* The system provides visual representations (charts/graphs) of the data for easier interpretation.  
* Data on the dashboard is up-to-date and reflects recent activity.

**Step 4: Engineering Tasks**

* Design and develop a statistics dashboard that displays student performance metrics.  
* Implement data visualization components to display statistics in charts and graphs.  
* Add filtering and sorting functionalities to the dashboard for better data analysis.  
* Integrate the dashboard with the existing user interface and ensure proper authentication and authorization for educators.

**Step 5: Estimation of Efforts**

* (8 Hours) Design and develop a statistics dashboard that displays student performance metrics.  
* (5 Hours) Implement data visualization components to display statistics in charts and graphs.  
* (4 Hours) Add filtering and sorting functionalities to the dashboard for better data analysis.  
* (3 Hours) Integrate the dashboard with the existing user interface and ensure proper authentication and authorization for educators.

Total: (20 Hours)

#### User story 2

**Step 1: Role-Goal-Benefit**  
As an educator, I want to invite students to my classroom, so that I can manage data access amongst students

**Step 2: Notes, Limitations or Clarifications**

* Educators should be able to revoke access or remove members from the classroom.  
* The system should notify the educator when a student joins.

**Step 3: Definition of Done and Validation**

* Educators are able to create classroom codes for the students to join the classroom  
* The classroom codes are unique and randomly generated.  
* Proper Access Control is established.

**Step 4: Engineering Tasks**

* Create a hashing system to create unique and random codes for joining classrooms  
* Set up access control to enforce appropriate permissions for instructors and students.  
* Add notification features to inform educators when students join.

**Step 5: Estimation of Efforts**

* (7 hours)Create a hashing system to create unique and random codes for joining classrooms  
* (2 hours)Set up access control to enforce appropriate permissions for instructors and students.  
* (1 hours)Add notification features to inform educators when students join.

Total: (10 Hours)

#### User story 3

**Step 1: Role-Goal-Benefit**

As an educator, I want to have access to a problem bank with pre-made questions of varying difficulty and topics, so that I can easily assign them to students without having to create all of them.

**Step 2: Notes, Limitations or Clarifications**

* The problem bank will include pre-made questions categorized by difficulty and topics.  
* Each problem will have a title, unique identifier, description, and a solution.  
* Problems will be tagged for easy filtering by difficulty and topic.  
* Educators should be able to browse, search, and filter problems within the problem bank.  
* Problems should be ready for assignment directly or copied into customized quizzes.

**Step 3: Definition of Done and Validation**

* Educators can access a questions page that displays a list of available problems.  
* The question page should allow filtering by difficulty and topic.  
* Educators can view details of each problem, including the solution.  
* Problems can be selected and assigned directly to students or added to a customized quiz.  
* The problem bank interface should be user-friendly and allow easy navigation.

**Step 4: Engineering Tasks**

* Create the problems on various concepts and of varying difficulty  
* Add to existing list of questions  
* Implement filtering functionality for problems by difficulty and topic.  
* Design a user-friendly interface for browsing and searching problems.

**Step 5: Estimation of Efforts**

* (10 hours) Create the problems on various concepts and of varying difficulty  
* (1 hour) Add to existing list of questions  
* (5 hours) Implement filtering functionality for problems by difficulty and topic.  
* (5 hours) Design a user-friendly interface for browsing and searching problems.

Total: (21 Hours)

#### User story 4

**Step 1: Role-Goal-Benefit**

As an educator, I want to have access to a problem bank with pre-made questions of varying difficulty and topics, so that I can easily assign them to students without having to create all of them.

**Step 2: Notes, Limitations or Clarifications**

* The problem bank will include pre-made questions categorized by difficulty and topics.  
* Each problem will have a title, unique identifier, description, and a solution.  
* Problems will be tagged for easy filtering by difficulty and topic.  
* Educators should be able to browse, search, and filter problems within the problem bank.  
* Problems should be ready for assignment directly or copied into customized quizzes.

**Step 3: Definition of Done and Validation**

* Educators can access a questions page that displays a list of available problems.  
* The question page should allow filtering by difficulty and topic.  
* Educators can view details of each problem, including the solution.  
* Problems can be selected and assigned directly to students or added to a customized quiz.  
* The problem bank interface should be user-friendly and allow easy navigation.

**Step 4: Engineering Tasks**

* Create the problems on various concepts and of varying difficulty  
* Add to existing list of questions  
* Implement filtering functionality for problems by difficulty and topic.  
* Design a user-friendly interface for browsing and searching problems.

**Step 5: Estimation of Efforts**

* (10 hours) Create the problems on various concepts and of varying difficulty  
* (1 hour) Add to existing list of questions  
* (5 hours) Implement filtering functionality for problems by difficulty and topic.  
* (5 hours) Design a user-friendly interface for browsing and searching problems.

Total: (21 Hours)

#### User story 5

**Step 1: Role-Goal-Benefit Statement**

As an educator, I want to assign a difficulty rating to each question, so that I can give students a quick idea of how much foundation they should have before attempting it.

**Step 2: Notes, Limitations, or Clarifications**

* Difficulty is only assigned by accounts with instructor status  
* Only one rating can be assigned at a given time  
* Ratings will be sorted by Easy, Medium, or Hard

**Step 3: Definitions of Done**

* When an instructor saves the difficulty level of a question as Easy, Medium, or Hard  
* When an instructor changes the initial difficulty level of a question to Easy, Medium, or Hard

**Step 4: Engineering Tasks**

1\.   Set-up database to have all questions with the option to store information on hints  
2\.   Create option for instructor to edit question difficulty level in classroom profile  
3\.   Create page for instructor to select questions they want to difficulty levels for  
4\.   Create another page to go into the question they select to look at all the test cases and a button to edit the difficulty for the specific test case the user chooses

**Step 5: Estimation of Effort**

* Task 1: 1 Hours  
* Task 2: 1 Hour  
* Task 3: 2 Hours  
* Task 4: 2 Hours

#### User story 6

**Step 1: Role-Goal-Benefit Statement**

As an educator, I want to be able to provide optional hints for students having issues with a problem, so that I can guide students to better refine their coding comprehension

**Step 2: Notes, Limitations, or Clarifications**

* Only one hint can be assigned to a specific test case that is failed  
* Only instructor status accounts can create or edit hints

**Step 3: Definitions of Done**

* When an educator clicks edit on the test cases available, types in their hint and clicks save

**Step 4: Engineering Tasks**

1\.    	When an educator clicks edit on the test cases available, types in their hint and clicks save  
2\.    	Set-up database to have all tests with the option to store information on hints  
3\.    	Create option for instructor to edit hints in classroom profile  
4\.    	Create page for instructor to select questions they want to edit hints for  
5\.    	Create another page to go into the question they select to look at all the test cases and a button to edit hint for the specific test case the user chooses  
6\.    	Create another page with a textbox that allows the user to either add, change, or remove the hint with a save button at the corner

**Step 5: Estimation of Effort**

* Task 1: 2 Hours  
* Task 2: 1 Hour  
* Task 3: 3 Hours  
* Task 4: 3 Hours  
* Task 5: 1 Hour  
* Task 6: 2 Hours

#### User story 7

**Step 1: Role-Goal-Benefit Statement**

As an educator, I need the program to keep my account and authorization secure, so that I know I am not jeopardizing students’ privacy by using this app.

**Step 2: Notes, Limitations, or Clarifications**

* Accounts will be created with a user input for username and password  
* Users with the corresponding username and password can access the specific accounts  
* Users will input a student code if they wish to join an existing class  
* Users will create a classroom and will be given student codes for others to join their classroom


**Step 3: Definitions of Done**

* For joining a classroom, when user clicks create account and input all necessary information (Name, Age, Major, and Years of Coding Experience) and student or instructor code  
* For creating a classroom, when user is prompted with student code if they choose to invite others to their new classroom following the same instructions as joining a classroom, but instead requesting to create a classroom  
* 

**Step 4: Engineering Tasks**

1\.    	Set-up an account creation page with fields for name, age, major, years of coding experience, option to join or create classroom, then within join classroom field to enter classroom code  
2\.    	Have database record submission of a new account and classroom creation  
3\.    	If new account joins classroom have database recognize if new account is an instructor or student

**Step 5: Estimation of Effort**

* Task 1: 3 Hours  
* Task 2: 2 Hours  
* Task 3: 1 Hour

#### User story 8

**Step 1: Role-Goal-Benefit Statement**

As an educator, I want to see if my students can identify code with errors, so that I can teach them debugging

**Step 2: Notes, Limitations, or Clarifications**

* Students will specify the correct code to fix the specific line that contains the bug

**Step 3: Definitions of Done**

* When a student sees a question asking them to identify what lines of the code are incorrect and see the test cases that fail

**Step 4: Engineering Tasks**

1\.    	Create question with incorrect line of code  
2\.    	Create test suite that tests for the desired code  
3\.    	Store code and test suite to database  
4\.    	Determine how to engineer user input into a prompt for Ollama to create code  
5\.    	Parse Ollama output into code that can be used against test suite

**Step 5: Estimation of Effort**

* Task 1: 1 Hour  
* Task 2: 2 Hours  
* Task 3: 1 Hour  
* Task 4: 3 Hours  
* Task 5: 2 Hours

### Epic 2: User Consent and Data Collection

#### User story 10

**Step 1: Role-Goal-Benefit Statement**

As a researcher, I want to verify the user’s understanding of the data that will be collected, so that I have their consent.

**Step 2: Notes, Limitations, or Clarifications**

* This is important for complying with PIPEDA

**Step 3: Definitions of Done**

* Users will be able to understand the data that is being collected and the reason for doing so.  
* Users will be given or denied consent for data collection.  
* Users who do not consent will not have their data collected.

**Step 4: Engineering Tasks**

* Create a disclaimer that users read to understand what data is being collected and their purpose.  
* Create a checkbox that users can click to give their consent, which is required for creating an account.  
* Add the disclaimer and checkbox to the user registration page.

**Step 5: Estimation of Effort**

* (2 Hours) Create a disclaimer that users read to understand what data is being collected and their purpose.  
* (2 Hours) Create a checkbox that users can click to give their consent, which is required for creating an account.  
* (2 Hours) Add the disclaimer and checkbox to the user registration page.

Total Time: 6 Hours

#### User story 11

**Step 1: Role-Goal-Benefit Statement**

As a user, I want to be able to log in and have the application recognize my role as an educator or student, so that I am able to access the functionality that I need.

**Step 2: Notes, Limitations, or Clarifications**

* Users will log in with a unique username and a corresponding password  
* After logging in, users will have their authorization stored as a session cookie  
* The session cookie will also be used for future HTTP requests  
* Unauthorized users will not be able to access questions or classrooms

**Step 3: Definitions of Done**

* Users can input their username and password to access functions related to their role as a student or educator  
* Unauthorized users are unable to access protected endpoints available for authorized users  
* User authentication is persisted through tab reloading  
* User id is available for HTTP requests after authorization  
* User is able to log out and remove the session cookie

**Step 4: Engineering Tasks**

* Create a login page that allows users to input a username and password  
* Send a cookie that stores the user id  
* Protect REST API endpoints by checking user id  
* Add a logout button that removes the session cookie

**Step 5: Estimation of Effort**

* (6 Hours) Create a login page that allows users to input a username and password  
* (2 Hours) Send a cookie that stores the user id  
* (3 Hours) Protect REST API endpoints by checking user id  
* (2 Hours) Add a logout button that removes the session cookie  
* Total: 13 Hours

#### User story 12

**Step 1: Role-Goal-Benefit Statement**

As a student, I want to view a list of problems that I can solve, so that I am able to easily click on one and begin solving it.

**Step 2: Notes, Limitations, or Clarifications**

* Problems will be pre-made as well as educator-made  
* Listed problems will have a title, id, and difficulty

**Step 3: Definitions of Done**

* Students are able to view a problems page, which displays available problems  
* A student may click on a listed problem which directs them to the problem page

**Step 4: Engineering Tasks**

* Create a problem page that displays a list of problems  
* Create a REST API endpoint for retrieving the problems to the website  
* Create a component for displaying a single problem

**Step 5: Estimation of Effort**

* (5 Hours) Create a problem page that displays a list of problems  
* (4 Hours) Create a REST API endpoint for retrieving the problems to the website  
* (2 Hours) Create a component for displaying a single problem  
* Total: (11 Hours)

### Epic 3: User Experience and Interactions

#### User story 13

**Step 1: Role-goal-benefit**  
As a student, I want to be able to sort problems by difficulty or topic, so that I can find questions that are most relevant to me.   
**Step 2: Notes, limitations, or clarifications** 

*  Questions will be sorted into three levels of difficulty: “Easy”, “Medium”, and “Hard” to prevent confusion over more granular classifications.   
*  The levels of difficult indicate the relative complexity of the code statement presented to the user  
* This functionality will extend on work done for User story 12\. Therefore, a list of problems will already be available on the user’s question list page.

**Step 3: Definitions of Done/Validation**

*  When a student opens their question list page, they will be presented with a scrollable list of questions.   
* When a button is toggled, the questions will switch from being sorted in ascending order of difficulty to being sorted in alphabetical order of their topic tag. 

**Step 4: Engineering Tasks**

* Add a toggle button to the frontend.  
*  Implement two compare() functions for question objects. The first function will perform comparisons using the question’s Topic attribute while the second will perform comparison on the question’s Difficulty attribute.   
*  Add a handler function that detects when the button changes state, calls sort() on the question list array with the appropriate compare function, and returns the result for display to the user.

**Step 5 Estimation of effort:**

* Add a toggle button to the frontend: 1  
* Implement and fully test compare() function: 3  
* Implement and fully test handler function: 2  
*  Total: 6 hours

#### User story 14

**Step 1: Role-Goal-Benefit (RGB)**  
As a student, I need a way to input and submit my comprehension so that I can get feedback

**Step 2: Limitations or Clarifications**

* The comprehension input UI component will take the form of a text box that accepts an arbitrary user response as a string.  
* The response will be evaluated when the user clicks a “submitt” button

**Step 3: Definitions of Done (Tests)**

*  A tester can input text into this UI component  
*  The response is submitted when the user clicks the “submit” button, which can only happen exactly once.   
*  A tester will not be able to modify the contents of the textbox after clicking “submit”  
* The user response is successfully converted to code that matches the user’s description by the LLM.  
* The LLM-generated code is tested by running it against all linked test-cases.  
* The result is recorded as a tuple in the “Response” table

**Step 4: Engineering Tasks**

* Research and Design:  
  o   Design the input UI for the submission form, including a text box and a submission button  
*  Frontend:  
  o   Implement the input text box in javascript  
  o   Add a handler function that prevents modification of the text box when the submission button is clicked and initiates a request to the backend for validation of the input  
*   Backend:  
  o   Implement server-side logic to handle submission requests  
  o   Implement a function to sanitize potentially harmful inputs and pass them to the LLM  
  o   Implement server-side logic to handle the LLM response and sanitize potentially harmful code  
  o   Implement server-side logic to retrieve all test cases associated with the question ID from the backend database  
  o   Implement a call to run the sanitized code against each test case. Return the hint attribute of the first test case that fails. If none fail, return a signal for “success”.  
  o   Implement server-side logic to retrieve the highest attempt number N associated with the given question ID and user ID as from the Responses table in the backend database.  
  o   Implement server-side logic to store the attempt number N+1, question ID, user ID, user response, LLM code, and all other relevant metadata as tuple in the Responses table in the backend database  
* Integration:  
  o   API endpoint for sending user response to a prompt  
  o   Implement logic to parse the fetched response from the frontend  
* Testing:  
  o   Write unit tests for validation functions, parsing functions, the code-call, and each database-level GET and PUT statement  
  o   Write integration tests for the data flow from frontend to backend, to/from LLM, and to/from code-testing module

**Step 5: Estimation of Effort (Story Points)**

* Research and design: 1 hour  
*  Frontend development: 3 hours  
*  Backend development: 15 hours  
* Front-end integration: 2 hours  
* Testing: 6 hours  
* Total: 27 hours

#### User story 15

**Step 1: Role-Goal-Benefit (RGB)**  
As a student, I want to know if my comprehension is correct, so that I can confirm my understanding.

**Step 2: Limitations or Clarifications**

* This extends the work performed for user story 14\. Therefore, it is assumed that a functional system for submitting and assessing student responses has been implemented. 

**Step 3: Definitions of Done (Tests)**

* After submitting their response in user story 14, the user will be informed that their answer is correct if all associated test cases pass when their code is evaluated

**Step 4: Engineering Tasks**

* Frontend:  
  o   Add a textbox to the student question page for displaying the result of their submission  
  o   Add a function to update the textbox when the backend processes the submission and generates a feedback string  
* Backend:  
  o   Implement server-side logic to generate a feedback string by parsing the result of running all required test cases against the LLM-generated code in the code evaluation module. If a success state is returned, a string informing the user of correctness should be returned.   
* Integration:  
  o   Implement the logic to parse the fetched request for the front-end  
* Testing:  
  o   Unit testing of the function for generating a feedback from the code evaluation module  
  o   Integration testing for sending feedback string from backend to frontend

**Step 5: Estimation of Effort (Story Points)**

\-              Frontend: 2 hours  
\-              Backend: 3 hours  
\-              Integration: 2 hours  
\-              Testing: 3 hours  
\-              Total: 10 hours

#### User story 16

**Step 1: Role-Goal-Benefit (RGB)**  
As a student, I have to know if I am not correct, then what I have done wrong so that I can do better next time.

**Step 2: Limitations or Clarifications**

* This extends the work performed for user story 15\. Therefore, it is assumed that a functional system for returning a feedback string for correct answers has been implemented. 

**Step 3: Definitions of Done (Tests)**

* After submitting their response in user story 14, the user will be informed that their answer is incorrect along with a helpful hint if at least one of the associated test cases fail when their code is evaluated

**Step 4: Engineering Tasks**

*  Backend:

  o   Update the server-side logic to generate a feedback string for incorrect answers by parsing the result of running all required test cases against the LLM-generated code in the code evaluation module. If one of the test cases fails, a string informing the user of their incorrect answer alongside the hint associated with the first test case to fail should be returned.

* Testing:

  o   Unit testing of the function for generating feedback from the code evaluation module

**Step 5: Estimation of Effort (Story Points)**

\-              Backend: 2 hours  
\-              Testing: 2 hours  
\-              Total: 4 hours

#### User story 17

**Step 1: Role-Goal-Benefit (RGB)**  
As a student, I want to see how long it takes me to complete each question, so that I can improve my proficiency in code comprehension.

**Step 2: Limitations or Clarifications**

* The most intuitive way is to display a timer at a non-intrusive position. It does not have to look good or use any graphics.  
* To limit the complexity of this functionality, only the most recent time record has to be preserved. But feel free to store more if the team has extra bandwidth.  
* If possible, emphasize that the timing is used as a self-improvement tool and will not affect their grades, so that it imposes less pressure on the student.

**Step 3: Definitions of Done (Tests)**

* A timing component is implemented and can be accessed by a user.  
* The time tracking starts when the question is shown, and stops when:  
  * the answer is submitted, or  
  * (optionally) the time limit for this question is reached.  
* The time record data is correctly passed to the data source and preserved.  
* The time record for questions the student has attempted (submitted and passed / failed) can be seen in an appropriate view any time, such as in the student profile or dashboard.  
* The time record is shown in such a way that the student can compare their most recent time used to some standard, such as the one before the most recent one, or the class median. This ideally should be shown for each attempted question.

**Step 4: Engineering Tasks**

* Frontend:  
  * Develop UI components to display the time elapsed in real time, on the same page where the question is shown.  
  * Implement the logic to start the timer when the question is presented and stop it when the answer is submitted or the time limit is reached.  
  * Create a summary view where students can see the time taken for all attempted questions along with their improvements.  
  * (Optional) Display a text hint on the UI telling students that the time they spend will not affect their progress record.  
  * (Optional) Display a warning, such as a different color for the timer's text, when the time limit is near.  
* Backend:  
  * Create entries for the time record that are correctly associated with the student and the question, and make it possible to query them in a structured way.  
  * Implement server-side logic to retrieve all relevant data for the summary view and compile them all into a formatted data structure.  
* Integration:  
  * Include the time record in the request body when a submission is made and sent to the corresponding API endpoint.  
  * Implement logic to parse the sent information from the frontend.  
  * Implement logic to parse the response from the API.  
* Testing:  
  * Write unit tests for the timer start and stop function, data compilation functions, parsing functions, etc.  
  * Write integration tests for data flows and persistence regarding the time record, such as whether the time is correctly updated when a student makes a non-first attempt to the same question.

**Step 5: Estimation of Effort (Story Points)**

* Frontend Development: 11 hours  
* Backend Development: 3 hours  
* Frontend-backend integration: 2 hours  
* Testing: 5 hours  
  Total Story Points: 21 hours

#### User story 18

**Step 1: Role-Goal-Benefit (RGB)**  
As a student, I want to be able to ask the LLM questions about the solution, so that I can understand what the code is doing.

**Step 2: Limitations or Clarifications**

* There needs to be a user-friendly interface for asking questions and displaying answers. This should be separate from the comprehension input UI component.  
* The interface should keep a temporary log for questions and answers asked in the current session.  
* It does not need to be too helpful, so consider limiting the number of questions each time.  
* May need to limit the conversation context to only the solution to the question.

**Step 3: Definitions of Done (Tests)**

* A tester can access and interact with this solution explanation UI component.  
* A tester can only access it after a submission is done and the result is returned.  
* A tester can input any questions, but the LLM will only answer questions highly relevant to the solution.  
* All responses for the initial question and any follow-up queries make sense and are helpful.

**Step 4: Engineering Tasks**

* Research and Design:  
  * Roughly design the user interface for the Q\&A feature, including input fields and display areas for responses.  
* Frontend:  
  * Develop the UI components according to the UI design.  
  * Link it up with the state of whether a pass / fail result is returned for a question.  
  * Preserve a temporary history for a short time and show it to the tester as long as this session is valid.  
  * (Optional) Handle scenarios where the question number has exceeded the allowed limit.  
* Backend:  
  * Implement server-side logic to handle the requests. Validate sensitive parameters passed through the API URI if needed, to counter fight malicious injections and such.  
  * Sanitize the request contents and pass them to the LLM.  
  * Take in the preserved temporary history and pass it as context to the LLM as long as this session is valid.  
  * (Optional) Handle scenarios where the number of questions has exceeded the allowed limit.  
* Integration:  
  * API endpoint for sending the questions after a submission pass / fail (e.g. {server}/api/v1/q\_a\_solution?qid=q6dkjfh97h\&sid=s874hf87haanfw974h\&q\_number=3).  
  * Implement logic to parse the sent request for the backend.  
  * Implement logic to parse the fetched response for the frontend.  
* Testing:  
  * Write unit tests for the validation functions, parsing functions, etc.  
  * Write integration tests for the integration data flows.  
  * (Optional) Manually test the usability of the UI and gather feedback.

**Step 5: Estimation of Effort (Story Points)**

* Research and Design: 0.5 hour  
* Frontend Development: 8 hours  
* Backend Development: 3.5 hours  
* Frontend-backend integration: 1 hours  
* Testing: 4 hours  
  Total Story Points: 17 hours

#### User story 19

**Step 1: Role-Goal-Benefit (RGB)**  
As a student with vision deficiency, I hope when I use my browser’s built-in zooming feature, the app remains readable to some extent, so that I can read the texts more easily.

**Step 2: Limitations or Clarifications**

* The app should support zoom levels ranging from 100% to 150%. Feel free to support more if the team has extra time.  
* Text should reflow properly, and buttons/links should remain accessible without overlapping or going off-screen.  
* Essentially this is a regular basic responsive design with a few extra steps. Can expand it with more responsive design requirements if necessary.

**Step 3: Definitions of Done (Tests)**

* A tester can manually test the app at different zoom levels (e.g. 100%, 125%, 150%).  
* At each zoom level, all textual information remains readable for the tester, and all interactive elements remain functional and accessible.  
* The scaling should work consistently for all supported browsers and devices.

**Step 4: Engineering Tasks**

* Frontend:  
  * Implement responsive CSS that allows texts, elements and containers to scale properly. ([Responsive design (MDN)](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design))  
  * Use relative units (e.g., em, rem) and sizes (%) for font sizes and layout elements, because these units scale according to the browser's zoom level.  
  * Restrict zoom levels to the considered range 100% \~ 150%.  
  * Utilize modules like [react-responsive](https://www.npmjs.com/package/react-responsive) to set the responsive sizes, if need per component responsiveness and is less sensitive about performance.  
* Backend:  
  * None.  
* Integration:  
  * None.  
* Testing:  
  * Manually test the UI interactions in different browsers, for each of the supported zoom levels on the supported devices.  
  * Write functional tests that set the zoom levels and simulate user inputs for a full submission flow.

**Step 5: Estimation of Effort (Story Points)**

* Frontend Development: 8 hours  
* Backend Development: 0 hours  
* Frontend-backend integration: 0 hours  
* Testing: 6 hours  
  Total Story Points: 14 hours

#### User story 20

**Step 1: Role-Goal-Benefit (RGB)**  
As a student, I think it would be nice to have game-like virtual rewards, so that I can keep myself motivated.

**Step 2: Limitations or Clarifications**

* Virtual rewards can include titles, points, levels, or other easily visualizable symbols.  
* The rewards should be meaningfully related to a student's overall performance on the provided questions or tests. Some examples:  
  * Based simply on numbers of Qs: Such as *Code Explorer* for students completing 5 questions, *Logic Legend* for 50 questions, etc.  
  * Based on intermediate tokens: Such as 10 points for each question, and 50 points will give students level 1 standing, 500 give level 8 standing.  
* No matter what method we eventually adopt, use non-discriminative wordings where applicable. (Just in case: no need to go too hard on DEI.)

**Step 3: Definitions of Done (Tests)**

* A rewards system is implemented where students earn titles, points, or achievements that reflect their progress.  
* A tester can see their rewards displayed prominently, whenever they log in.  
* A tester is able to access them any time and they should always be correct, i.e. rewards are persisted in the same manner as progress.

**Step 4: Engineering Tasks**

* Research and Design:  
  * Research different types of virtual rewards and their effectiveness, as well as complexity to implement.  
  * Design an appropriate curve to map progress \-\>reward. It is possible to borrow some from game designers, for example [this article](https://www.davideaversa.it/blog/gamedesign-math-rpg-level-based-progression/) .  
  * Create mockups for UI elements displaying the reward. Preferably use as few art assets as possible.  
* Frontend:  
  * Develop UI components to display rewards in the app.  
  * Incorporate those UI components in a page, such as user dashboard, user profile etc.  
  * Implement notifications or alerts to inform students when they earn a new reward.  
* Backend:  
  * Create a rewards database schema or other data sources to store reward types, criteria, and student progress.  
  * Implement server-side logic to award rewards based on student progress.  
* Integration:  
  * Correctly compile the rewards information in a pertinent API response, such as a response for a request fetching user profile sent to the user profile endpoint (e.g. {server}/api/v1/user\_prof?id=u3478567asjkd).  
  * Implement logic to parse the fetched information for the frontend.  
* Testing:  
  * Write unit tests for the automatic awarding functions, parsing functions, etc.  
  * Write integration tests for the integration data flows and data persistence, but exclude user login and reward alert.  
  * (Optional) Write an end-to-end test for the scenario where a user succeeds on a question and a reward is gained. This includes user login and reward alert.  
  * (Optional) Conduct user testing to gather feedback on the rewards system's motivational impact.

**Step 5: Estimation of Effort (Story Points)**

* Research and Design: 1 hour  
* Frontend Development: 5 hours  
* Backend Development: 2 hours  
* Frontend-backend integration: 2 hours  
* Testing: 5 hours  
  Total Story Points: 15 hours

# Technical Design

## User Interface

### 

### UI mockups

<img alt="UI mockups" src="/resources/UI mockups.jpg" width="320">

### UI usage and API communication diagram

<img alt="UI mockups" src="/resources/UI usage and API.jpg" width="320">

## REST API

### Users

### **1\. GET /login/\<username\>/\<password\>**

#### **Description**

Sends the `username` and `password` and checks if the credentials match the database. Returns a session cookie with the user `id` for further authorization.

#### **Parameters**

| Name | Type | Description |
| ----- | ----- | ----- |
| `username` | string | The username of the user. |
| `password` | string | The password of the user. |

#### **Return Calls**

* **200 (OK):** Username and password exist.  
* **401 (Unauthorized):** Username and password do not exist.

---

### **2\. GET /user/\<id\>**

#### **Description**

Retrieves complete user profile by `id`.

#### **Parameters**

| Name | Type | Description |
| ----- | ----- | ----- |
| `id` | string | The id of the user to retrieve the profile. |

#### **Return Calls**

* **200 (OK):** `id` exists and is accessible.  
* **403 (Forbidden):** `id` exists but should not be accessible by requester.  
* **404 (Not Found):** `id` does not exist.

---

### **3\. POST /user/\<role\>/\<username\>/\<password\>**

#### **Description**

Creates a new user with corresponding `role`, `username`, and `password`. Additional information can be passed in the body of the request.

#### **Parameters**

| Name | Type | Description |
| ----- | ----- | ----- |
| `role` | string | The role of the new user. |
| `username` | string | The username of the new user. |
| `password` | string | The password of the new user. |
| `email` | string | The email used by the new user |

#### **Return Calls**

* **200 (OK):** Username and password are unique, and the user is created.  
* **400 (Bad Request):** Username is taken.

---

### **4\. PATCH /user/\<id\>**

#### **Description**

Updates user profile with additional information passed in the body of the request.

#### **Parameters**

| Name | Type | Description |
| ----- | ----- | ----- |
| `id` | string | The ID of the user whose profile to update. |
| `username` | string | The updated username |
| `password` | string | The updated password |
| `email` | string | The updated email |

#### **Return Calls**

* **200 (OK):** User profile is updated.  
* **404 (Not Found):** ID does not exist.

---

### Question

### **5\. GET /question/**

#### **Description**

Retrieves a list of all question headers.

#### **Parameters**

None

#### **Return Calls**

* **200 (OK):** Successfully retrieved list of question headers.

---

### **6\. GET /question/\<id\>**

#### **Description**

Retrieves complete question information by `id`.

#### **Parameters**

| Name | Type | Description |
| ----- | ----- | ----- |
| `id` | string | The ID of the question to retrieve. |

#### **Return Calls**

* **200 (OK):** `id` exists and is accessible.  
* **404 (Not Found):** `id` does not exist.

---

### **7\. POST /question/\<classroomId\>**

#### **Description**

Creates a new question associated with a classroom's `id`. Additional information can be passed in the body of the request.

#### 

#### **Parameters**

| Name | Type | Description |
| ----- | ----- | ----- |
| `classroomId` | string | The ID of the teacher creating the question. |
| `title` | string | The title of the question |
| `prompt` | string | Question prompt |
| `time_limit` | integer | Time limit for question if it has one, else \-1 |
| `difficulty` | integer | Difficulty of the question, ranged 1-3 |

#### **Return Calls**

* **200 (OK):** Successfully created the question.

---

### **8\. PATCH /question/\<id\>**

#### **Description**

Updates question information by `id`.

#### **Parameters**

| Name | Type | Description |
| ----- | ----- | ----- |
| `id` | string | The ID of the question to update. |
| `title` | string | The updated title of the question |
| `prompt` | string | Updated Question prompt |
| `time_limit` | integer | Updated Time limit for question if it has one, else \-1 |

#### **Return Calls**

* **200 (OK):** ID exists, and question is updated.  
* **404 (Not Found):** ID does not exist.

---

### **9\. DELETE /question/\<id\>**

#### **Description**

Deletes the question by `id`. The question must belong to the user id to succeed.

#### **Parameters**

| Name | Type | Description |
| ----- | ----- | ----- |
| `id` | string | The ID of the question to delete. |

#### **Return Calls**

* **200 (OK):** Successfully deleted the question.  
* **403 (Forbidden):** Question does not belong to the user.

---

### Attempts

### **10\. GET /attempt/\<questionId\>/\<studentId\>/\<attempt\_number\>/**

#### **Description**

If any of these parameters (`questionId`, `studentId`, `attempt_number`) is set to `-1`, the corresponding filter is not applied

#### **Parameters**

| Name | Type | Description |
| ----- | ----- | ----- |
| `questionId` | string | The ID of the question for which attempts are retrieved or \-1 |
| `studentId` | string | The ID of the student whose attempts are retrieved or \-1 |
| `attempt_number` | string | The specific attempt number to retrieve or \-1 |

#### **Return Calls**

* **200 (OK):** `id` exists and is accessible.  
* **403 (Forbidden):** `id` exists but should not be accessible by requester.  
* **404 (Not Found):** `id` does not exist.

### **11\. POST /attempt/\<questionId\>/\<studentId\>/\<attempt\_number\>/\<type\>**

#### **Description**

Creates a new request to the LLM associated with `questionId, studentId` and `attempt_number`. The `type` parameter defines if it’s generating code or a response to a user question.

#### **Parameters**

| Name | Type | Description |
| ----- | ----- | ----- |
| `questionId` | string | The ID of the question for which LLM Response is retrieved |
| `studentId` | string | The ID of the student whose LLM Response is retrieved |
| `attempt_number` | string | The specific attempt number to retrieve  |
| `type` | string | Type of generated response from LLM |

#### 

#### **Return Calls**

* **200 (OK):** Successfully created the request.

### **12\. POST /evaluate-answer/\<questionId\>/\<studentId\>**

#### **Description**

Evaluates the student submission and creates a new attempt. Additional Information can be found in the body.

#### **Parameters**

| Name | Type | Description |
| ----- | ----- | ----- |
| `questionId` | string | The ID of the question being evaluated. |
| `response_time` | integer | Time taken by student to answer question |
| `response` | string | Response given by the user |

#### **Return Calls**

* **200 (OK):** Successfully created evaluation request

---

### Classroom

### **13\. GET /classroom/\<id\>**

#### **Description**

Returns all relevant information about a class including student and teacher `id`’s.  Should only be accessible by a user authorized to do so.

#### **Parameters**

| Name | Type | Description |
| ----- | ----- | ----- |
| `id` | string | The ID of the classroom. |

#### **Return Calls**

* **200 (OK):** Successfully retrieved classroom information.

---

### **14\. POST /classroom/\<teacherId\>**

#### **Description**

Creates a new classroom associated with a teacher’s `id` (the owner of the classroom).

#### **Parameters**

| Name | Type | Description |
| ----- | ----- | ----- |
| `teacherId` | string | The ID of the teacher creating the classroom. |

#### **Return Calls**

* **200 (OK):** Successfully created the classroom.

---

### **15\. DELETE /classroom/\<id\>**

#### **Description**

Deletes the classroom by `id`. The classroom must belong to the user `id` to succeed.

#### **Parameters**

| Name | Type | Description |
| ----- | ----- | ----- |
| `id` | string | The ID of the classroom to delete. |

#### **Return Calls**

* **200 (OK):** Successfully deleted the classroom.  
* **403 (Forbidden):** Classroom does not belong to the user.

---

### **16\. GET /classroom-code/\<clasroomid\>**

#### **Description**

Creates a classroom code for users to join with. 

#### **Parameters**

| Name | Type | Description |
| ----- | ----- | ----- |
| `classroomid` | string | The ID of the classroom. |

#### **Return Calls**

* **200 (OK):** Successfully created the classroom code.

---

### **17\. POST /classroom-code/\<code\>**

#### **Description**

Joins a classroom if the `code` is valid 

#### **Parameters**

| Name | Type | Description |
| ----- | ----- | ----- |
| `code` | string | The classroom code to join. |

#### **Return Calls**

* **200 (OK):** Successfully joined the classroom.  
* **400 (Bad Request):** Invalid code

---

### Test Cases

### **18\. GET /test-cases/\<questionID\>**

#### **Description**

Retrieves all test cases associated with `questionId`.

#### **Parameters**

| Name | Type | Description |
| ----- | ----- | ----- |
| `questionId` | string | The ID of the question related to the request. |

#### **Return Calls**

* **200 (OK):** Retrieved test cases  
* **404(Not Found):** QuestionID doesn’t exist

### **19\. POST /test-cases/\<questionID\>**

#### **Description**

Creates test cases associated to `questionID`. Additional Information can be found in body of the request.

#### **Parameters**

| Name | Type | Description |
| ----- | ----- | ----- |
| `questionId` | string | The ID of the question related to the request. |
| `title` | string | Title of the test case |
| `output` | string | Expected output |

#### **Return Calls**

* **200 (OK):** Successfully created test case


## Backend

Our project’s data will be stored in a relational database. We plan to use the postgreSQL database management system. The specific data included as well as their relationships and datatypes are listed below. The entries in each table can be uniquely identified by their primary key.

Our API exposes this data to the rest of the application. Each table can be queried by GET commands and modified by PATCH and POST commands as appropriate. Please see above for the specifics of this interface. We will implement server-side logic that uses standard SQL commands to fulfill the API request.

Finally, we will use the LLM "Ollama” for our code generation module. The LLM will be prompted with a sanitized version of the student response string associated with an “answer” object. Additionally, we will include an initial prompt before the response string similar to the example prompt found here: [https://www.promptingguide.ai/applications/coding](https://www.promptingguide.ai/applications/coding). The LLM response will be parsed for the necessary code block which will be stored as an attribute of the “answer” object.  

Example prompt:   
“You are a helpful code assistant that can teach a junior developer how to code. Your language of choice is \*language\*. Don't explain the code, just generate the code block itself.” \+ \*Student Response String\*  
 

* ER Diagram:

<img alt="UI mockups" src="/resources/ER diagram.jpg" width="320">

* Tables (underline indicates primary key(s), **bold** indicates foreign key):  
  * User:  
    * Role: string (‘student’ or ‘educator’ or ‘researcher’)  
    * User ID: integer  
    * Email: string  
    * **Classroom ID**: integer  
    * Username: string  
    * Password: string  
    * Experience: integer  
  * Classroom:   
    * Classroom ID: integer  
    * **Educator ID**: integer  
    * Name: string  
    * Code: string (randomly generated unique identifier)  
  * Answer:  
    * **Student ID: integer**  
    * **Question ID: integer**  
    * **Attempt Number: integer**  
    * Response Time: integer (seconds)  
    * Response: string  
    * LLM Code: string  
    * Outcome: binary (1 \= pass, 0 \= fail)  
    * Timestamp: datetime  
  * Question:   
    * Question ID: integer  
    * Classroom ID: integer (-1 for default questions)  
    * Title: string  
    * Prompt: string  
    * Time limit: integer (seconds) (Optional)  
    * Difficulty: integer  (1 to 3\)  
    * Topic: string  
  * Test Case:  
    * **Question ID: integer**  
    * Title: string  
    * Input: string (comma-separated list)  
    * Expected output: string

## Test Coverage

### Account Creation

**What/Why we Test:**

- Testing for correct student account creation to a classroom  
- Testing for correct instructor account creation to a classroom  
- Testing for a correct instructor account and creating a new classroom  
- Test to see if only 1 instructor is allowed in a single classroom  
- Testing to see if multiple students can be added or removed to a single classroom  
- Ensure database is storing correct information  
- Before accounts are created consent and privacy acknowledgement is prompted and agreed to

**What Tests We Can Do:**

- Manual – Account Creation  
- Unit Tests – Database Storage of information

### Backend & API Interactions

**What/Why we Test:**

- Testing for valid API request  
- Making sure correct outputs are achieved when API calls made  
- Making sure correct inputs are stored in the intended locations in the database  
- Making sure invalid calls are giving appropriate error response codes

**What Tests We Can Do:**

- Unit Tests

### Code Validation

**What/Why we Test:**

- Having a valid test suite to match question’s code  
- Spot the bug questions have failing tests that are only intended to fail  
- Multi-part question follows the correct sequence of questions we desire  
- Database saves all user’s attempts (Ollama generated code snippets) at describing code  
- Database records number of failing tests for each attempt

**What Tests We Can Do:**

- Unit Tests

### Interaction of User Inputs and Ollama Prompts

**What/Why we Test:**

- User input correctly parses and edits to create an Ollama prompt that generates valid code  
- Handling for invalid user inputs that do not generate code  
- Parsing Ollama prompt to use valid generated code

**What Tests We Can Do:**

- Manual – Understanding how Ollama behaves  
- Unit Tests – Ensure Ollama behaves the way we understand and intend it to behave

### Question Banks in Application

**What/Why we Test:**

- Database correctly stores question with corresponding testing suite  
- Database stores response times, number of attempts and whether student completed question  
- Database stores correct sequence of questions from test bank for user-generated quizzes

**What Tests We Can Do:**

- Unit Tests

### Database Storage

**What/Why we Test:**

- Handling creation of data by ensuring only valid formatting is saved  
- Handling valid request protocols are followed from the front-end to the back-end

**What Tests We Can Do:**

- Unit Tests

### Administrator Dashboard

**What/Why we Test:**

- Database correctly assigns, reassigns, or removes difficulty ratings  
- Addition, modification, or removal of hints on test cases  
- Database correctly populates test bank page with all available questions with corresponding test cases  
- Instructors can view necessary information and statistics of each student in their generated classroom

**What Tests We Can Do:**

- Unit Tests

### UI

**What/Why we Test:**

- Any button or actionable feature leads user to the intended section of the application  
- Application text and icon resizing scales appropriately

**What Tests We Can Do:**

- Manual Testing
 

# Table of Contributions

| Name | Worked on Part(s) |
| :---- | :---- |
| Brandon Kato | User stories 5-8 (20%), Test Coverage (100%) |
| Jade Duan | User stories 17-20 (20%), User Interface (100%) |
| Richard Cao | User stories 10-12 (20%), API Interface (40%) |
| Samuel Salitra | User stories 13-16 (20%), Backend (100%) |
| Vivaan Wadhwa | User stories 1-4 (20%), API Interface (60%) |

\* Team member names are arranged in the same order as they are in the Canvas group.  
