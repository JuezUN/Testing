## Submissions test

This test is intended to see and measure the behavior of the server when there are several users submitting the  same task at the same time.

This test is done with JMeter, so the only thing that you have to do is open this file.

Following are explained the different components:

- *CSV users*: This component is used to get the necessary users to do the test. You have to set the file you are going to use (You can find and example on **users_set.csv** file).
- *HTTP Request Defaults*: Component to manage the default values use for the whole test. You only have to configure the server name or IP and the port.
-   Submission: Thread group where you set the number of users or threads you are going to use for your test.
  - _Login_: In this component the sign in is managed for every user.
  - *Register for a course*: here the request to register for a course is managed. You have to configure the value of parameter **register_courseid**, where you set the course id.
  -  _Go to course_: here you emulate the process to got to the course, so you have to set the course id on the path.
  - *Submission page*: here you go to the task page which you want to submit the code. You have to the task id at the end of the path.
  - *Submission*: in this component, you can submit the task. You have to set the values for the different parameters.

**Note**: every request has a Results Tree to view the result for the request and every thread.

The **summary report** shows the different statistics for the whole test.

How to start it? Firstly, clear all the reports ans listeners, then, start the test.

**How to insert users in the DB?** : For that, you can find the **mongo.js** file. Run the next command `mongo INGInious < mongo.js` to insert the users.