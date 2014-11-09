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

Returns a JSON with a list of questions each question containing a JSON for each question and list of JSON for each choice in each question

MC for MultipleChoice 
TF for TrueFalse
FB for Fill in the blanks


### studentSubmit.php

Request URL: http://afsaccess1.njit.edu/~vk255/Code_Testing/MiddleEnd/studentSubmit.php
	
Input Request Type: JSON POST

Input Message:

```
{
	"userID" : "1",
	"examID" : "1",	
	"questionAnswer" : 
			[
				{
					"questionID" : "1",
					"userAnswer" : "Assigning a value to a variable"
				},
				{
					"questionID" : "2",
					"userAnswer" : "finalize"
				}
			]
}
```

Output:

On Failure:

```
{
	"examSubmit" : "Failed",
	"Error" : "mysql error"
}
```

On Success:

If the exam is submitted successfully this is the JSON that will be returned

```
{
	"examSubmit" : "Success"
}
```

Note: Make sure to store questionID information and the userAnswer will be whatever choice the user picked or the user textbox value


### studentGradedExams.php

Request URL: http://afsaccess1.njit.edu/~vk255/Code_Testing/MiddleEnd/studentGradedExams.php

Input Request type: POST

Input variables: userID

Output:

Gets all the exams for that user that have been graded

```
{
	"exams" : 
		[
			{
				"examID" : "1",
				"examName" : "exam1",
				"score" : "90"
			},
			{
				"examID" : "2",
				"examName" : "exam2",
				"score" : "85"
			}
		]
}
```

If no exams are graded: 

```
{
	"exams" : []
}
```

### studentCheckGradedExam.php

Request URL: http://afsaccess1.njit.edu/~vk255/Code_Testing/MiddleEnd/studentCheckGradedExam.php

Input Request Type: POST 

Input variables: userID, examID

Output:

```
{
	"exam" : 
		[
			{
				"questionID" : "1",
				"question" : "What is an assignment statement?",
				"questionType" : "MC",
				"studentAnswer" : "Assigning a value to a variable",
				"correctAnswer" : "Assigning a value to a variable",
				"userCorrect" : "True",
				"comment" : "Correct, an assignment statement assigns the result of an expression to a variable."
			},
			{
				"questionID" : "2",
				"question" : "Which of the following is not a keyword in Java?",
				"questionType" : "MC",
				"studentAnswer" : "Assigning a multiplication",
				"correctAnswer" : "Assigning a value to a variable",
				"userCorrect" : "True",
				"comment" : "Correct"
			},
			{
				"questionID":"16",
				"question":"Another term for _______________ is data hiding.",
				"questionType":"FB",
				"studentAnswer":"Cool_Test",
				"correctAnswer":"encapsulation",
				"userCorrect":"False",
				"comment": null
			}
		]
}
```

If no exams are graded

```
{
	"exam" : []
}
```