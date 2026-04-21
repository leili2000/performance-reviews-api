employees

1. GET /employees
Response:
[{
	“id”: id,
	“firstName”: string,
	“lastName”: string,
	“level”: int,
	“reportsTo”: id,
	“createdAt”: Date
}]

2. GET /employees/{employee_id}
Response:
{
	“id”: id,
	“firstName”: string,
	“lastName”: string,
	“level”: int,
	“reportsTo”: id,
	“createdAt”: Date
}

3. POST /employees
Request:
{
	“firstName”: string,
	“lastName”: string,
	“level”: int,
	“reportsTo”: id
}
Response:
{
	“id”: id,
	“firstName”: string,
	“lastName”: string,
	“level”: int,
	“reportsTo”: id,
	“createdAt”: Date
}

4. DELETE /employees/{employee_id}
	<No Response>


performance_reviews

5. GET /performance_reviews/
Parameters (at least 1 is required):
authorId: id
employeeId: id 
Response:
[{
  "id": id,
  "employeeId": id,
  "level": int,
  "overall": int,
  "categories": {
    "teamWork": int,
    "timeManagement": int,
    "innovation": int
  },
  "meetingDate": Date,
  "meetingSupervisorId": id,
  "result": string,
  "comments": string,
  "author": id,
  "createdAt": Date
}]

6. GET /performance_reviews/{review_id}
Response:
{	
  “id”: id
	“employeeId”: id,
  “level”: int,
	“overall”: int,
	“categories”: {
    “teamWork”: int,
	  “timeManagement”: int,
	  “innovation”: int,
  },
	“meetingDate”: Date,
	“meetingSupervisorId”: id,
	“result”: string,
	“comments”: string
	“authorId”: id
	“createdAt”: Date
}

7. POST /performance_reviews
Request:
{
  “employeeId”: int,
  “level”: int,
	“overall”: int,
	“categories”: {
    “teamWork”: int,
	  “timeManagement”: int,
	  “innovation”: int
  },
	“meetingDate”: Date,
	“meetingSupervisorId”: id,
	“result”: string,
	“comments”: string,
	“author”: id
}
Response:
{
	“id”: id
	“employeeId”: int,
  “level”: int,
	“overall”: int,
	“categories”: {
    “teamWork”: int,
	  “timeManagement”: int,
	  “innovation”: int,
  },
	“meetingDate”: Date,
	“meetingSupervisorId”: id,
	“result”: string,
	“comments”: string,
	“author”: id,
	“createdAt”: Date
}
	
8. DELETE /performance_reviews/{review_id}
  <No response>

comments

9. POST /comments/
	Request:
	{
		“employeeId”: id,
		“subject”: string,
		“comment”: string,
		“authorId”: id
	}
	Response:
	{
	“id”: int,
		“employeeId”: id,
		“subject”: string,
		“comment”: string,
		“authorId”: id,
		“createdAt”: Date
}

10. GET /comment/
Parameters (at least 1 is required):
authorId: id
employeeId: id 
Response:
[{
	“id”: int,
		“employeeId”: id,
		“subject”: string,
		“comment”: string,
		“authorId”: id,
		“createdAt”: Date
}]

11. GET /comment/{comment_id}
Response Body:
{
	“id”: int,
	“employeeId”: id,
	“subject”: string,
	“comment”: string,
	“authorId”: id,
	“createdAt”: Date
}
DELETE /comments/{comment_id}

	<No Response>
