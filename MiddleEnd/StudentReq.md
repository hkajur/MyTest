# Student Requests

All the requests students can make

### studentExams.php

Request URL: http://afsaccess1.njit.edu/~vk255/Code_Testing/MiddleEnd/studentExams.php

Input Request Type: POST

Input Variables: examID, userID

Output:

On Failure:

```
{
	"Error" : "Due to some reason"
}
```

On Success:

```
{  
   "examID":"1",
   "examName":"Exam 1",
   "questions":[  
      {  
         "questionID":"1",
         "question_type":"MC",
         "question":"What is an assignment statement?",
         "choices":[  
            {  
               "choiceID":"1",
               "choice":"Adding a number to an int"
            },
            {  
               "choiceID":"2",
               "choice":"Assigning a multiplication"
            },
            {  
               "choiceID":"3",
               "choice":"Assigning a value to a variable"
            },
            {  
               "choiceID":"4",
               "choice":"Assigning a name to a variable"
            }
         ]
      },
      {  
         "questionID":"2",
         "question_type":"MC",
         "question":"Which of the following is not a keyword in Java?",
         "choices":[  
            {  
               "choiceID":"1",
               "choice":"final"
            },
            {  
               "choiceID":"2",
               "choice":"finalize"
            },
            {  
               "choiceID":"3",
               "choice":"finally"
            },
            {  
               "choiceID":"4",
               "choice":"implements"
            }
         ]
      },
      {  
         "questionID":"11",
         "question_type":"TF",
         "question":"Private constructors cannot be accessed from any derived classes or another class.",
         "choices":[  
            {  
               "choiceID":"1",
               "choice":"True"
            },
            {  
               "choiceID":"2",
               "choice":"False"
            }
         ]
      },
      {  
         "questionID":"16",
         "question_type":"FB",
         "question":"Another term for _______________ is data hiding.",
         "choices":[]
      }
   ]
}
```

If no such exam exists: 

```
{
	"examID" : null,
	"examName" : null,
	"questions" : []
}
```
