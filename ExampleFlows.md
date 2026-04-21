Example workflow 1: Add a new employee  \
I am Manager Pihu and I just hired a new employee. I want to add them to the system and then verify that they were added correctly.  \
POST /employees  \
I pass in the following information and get the new employee object back:  \
{  \
	&emsp;“id”: 10,  \
	&emsp;“firstName”: “Leili”,  \
	&emsp;“lastName”: “Nelson”,  \
	&emsp;“level”: 10,  \
	&emsp;“reportsTo”: 3,  \
	&emsp;“createdAt”: 4/20  \
}

I can also now get the employee by their id  \
GET /employees/15  \
Returns  \
{  \
  &emsp;“id”: 10,  \
	&emsp;“firstName”: “Leili”,  \
	&emsp;“lastName”: “Nelson”,  \
	&emsp;“level”: 10,  \
	&emsp;“reportsTo”: 3,  \
	&emsp;“createdAt”: 4/20
}

Now, I want to make sure Leili is properly added to the overall list of employees. List shortened for brevity.  \
GET /employees  \
Returns  \
[...,  \
{  \
	&emsp;“id”: 3,  \
	&emsp;“firstName”: “Pihu”,  \
	&emsp;“lastName”: “Jha”,  \
	&emsp;“level”: 2,  \
	&emsp;“reportsTo”: 1  \
	&emsp;“createdAt”: 4/19  \
}, ...,  \
{  \
	&emsp;“id”: 10,  \
	&emsp;“firstName”: “Leili”,  \
	&emsp;“lastName”: “Nelson”,  \
	&emsp;“level”: 10,  \
	&emsp;“reportsTo”: 3,  \
	&emsp;“createdAt”: 4/20  \
}  \
]



Example workflow 2: Add a comment  \
My employee has spent 2 weeks at work, so it is time for their second comment. First, I will verify that I got the right employee ID.  \
GET /employees/15  \
Returns  \
{  \
	&emsp;“id”: 10,  \
	&emsp;“firstName”: “Leili”,  \
	&emsp;“lastName”: “Nelson”,  \
	&emsp;“level”: 10,  \
	&emsp;“reportsTo”: 3,  \
	&emsp;“createdAt”: 4/20  \
}  \
That is the right employee, so I will add their comment  \
POST /comments  \
	{  \
		&emsp;“employeeId”: 15,  \
		&emsp;“subject”: “Week 2”,  \
		&emsp;“comment”: “Outstanding insight and work effort this week!”,  \
		&emsp;“authorId”: 3  \
	}  \
Response:  \
{  \
	&emsp;“id”: 56,  \
		&emsp;“employeeId”: 15,  \
		&emsp;“Subject”: “Week 2”,  \
		&emsp;“comment”: ”Outstanding insight and work effort this week!”,  \
		&emsp;“authorId”: 3,  \
		&emsp;“createdAt”: 4/20  \
}  \
Now, I want to see all the comments for this employee.  \
GET /comments  \
Parameters:  \
{employeeId: 15}  \ 

Result:  \
	[{  \
		&emsp;“id”: 42,  \
		&emsp;“employeeId”: 15,  \
		&emsp;“Subject”: “Week 1”,  \
		&emsp;“comment”: “Broke 3 dishes :(”,  \
		&emsp;“authorId”: 2,  \
		&emsp;“createdAt”: 4/3  \
},  \
{  \
		&emsp;“id”: 56,  \
		&emsp;“employeeId”: 15,  \
		&emsp;“Subject”: “Week 2”,  \
		&emsp;“comment”: ”Outstanding insight and work effort this week!”,  \
		&emsp;“authorId”: 3,  \
		&emsp;“createdAt”: 4/20  \
}]  \
I can see that my comment got added correctly and that maybe Leili is not such a perfect employee, despite what her Week 2 comment says.  \

Example workflow 32: Add a new review for Leili  \
GET /employees/301  \
Check that Leili exists and is eligible for review.  \
Should return  \
{  \
&emsp;“employeeId”: 15,  \
&emsp;“firstName”: “Leili”,  \
&emsp;“lastName”: “Nelson”,  \
&emsp;“Level”: 1,  \
&emsp;“reportsTo”: 45  \
}  \
POST /performance_reviews  \
Create a new performance review for Leili.  \
GET /performance_reviews/7008  \
View the exact review that was just stored.  \
GET /employees/301/reviews  \
View all reviews for Leili.
