# Controller

A PHP Library to access HTTP-based API

## Make a post request to Login Page:

Request URL: http://afsaccess1.njit.edu/~vk255/Code_Testing/MiddleEnd/login.php

Input Request Type: POST

Input Variables: username, password

Output:

On Failure: 

```
{
    "Backend_Login" : "Failed",
    "NJIT_Login" : "Failed",
    "Error" : "Invalid request"
}
```

On Success for Student:

```
{
    "userType" : "Student",
    "userName" : "John",
    "userID" : "1",
    "Backend_Login" : "Success",
    "exams" : [
      {
          "examID"    : "1"
          "examName" : "Exam1"
          "examTaken" : "True"
      },
      {
          "examID"    : "2"
          "examName"  : "Exam2"
          "examTaken" : "False"
      }
    ],
    "NJIT_Login" : "Failed"
}
```

On Failure for Professor:

```
{
    "userType" :  "Teacher",
    "userName" : "joe",
    "userID" : "11",
    "Backend_Login" : "Success",
    "exams" : [
      {
          "examID" : "1",
          "examName" : "Exam1",
          "examReleased" : "True"
      },
      {
          "examID" : "2",
          "examName" : "Exam2",
          "examReleased" : "False"
      }
    ],
    "NJIT_Login" : "Failed"
}

```

Returns a JSON with a list of exams and each list element containing a JSON which has the examID, examName, and examTaken to check if the exam is taken by the user

[Read more words](another.md)
