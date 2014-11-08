# Controller


## Make a post request to Login Page:

Request URL: http://afsaccess1.njit.edu/~vk255/Code_Testing/MiddleEnd/login.php

Input: POST request and variable names are username, password

Output:

```
{
    "Backend_Login" : "Failed",
    "NJIT_Login" : "Failed",
    "Error" : "Invalid request"
}
```

On success:

```
{
    "userType" : "Student",
    "username" : "John",
    "userID" : "1",
    "Backend_Login" : "Success",
    "exams" :
        [
            {
                "examID"    : "1"
                "examName" : "Exam1"
                "examTaken" : "Y"
            },
            {
                "examID"    : "2"
                "examName"  : "Exam2"
                "examTaken" : "N"
            }
        ],
    "NJIT_Login" : "Failed"
}
```

[Read more words](another.md)
