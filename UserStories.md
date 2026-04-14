# User stories and exceptions


- User story 1: As an employer, I want to keep track of my employees’ performance reviews so that I can monitor my employees’ progress over time.
Exception: employer has access to employees who are no longer under them
- User story 2: As a manager, I want to record comments about my employees so I can give them feedback.
Exception: The comment exceeds allowed length, an error message would be displayed
- User story 3 : As a high-ranking executive, I would like to be able to see the average score a manager under me is giving to their employees. 
Exception : The lower-ranking employees being able to access this data
- User story 4: As team lead, I want to create a task force for an upcoming project. I would like to be able to sort people in my team by their “teamwork skills” score from their performance reviews.
Exception: Database has not updated and someone who left the team is still in it
- User story 5: As a manager, with the inclusion of using AI to increase productivity, I would like to add a new field to our performance review cycle and judge people on how effectively they are using AI.
Exception: Older users don’t have this field filled, it would be kept as null.
- User story 6: As a manager, I would like to be able to store performance reviews by team, and also be able to join tables to find all performance reviews for a particular employee (across all the teams they have been in).
Exception: The employee has no associated teams or reviews, a message is displayed.
- User story 7: As a senior leader, I want to collect my employee’s reviews by their subordinates, so that I can get another perspective on their work
Exception: Employee has no subordinates, so a message about that is shown.
- User story 8: As an employee, I want to see my past performance reviews, so that I can remember what I need to improve
Exception:  The system fails to retrieve the data due to a network error, so a message about checking later is shown.
- User story 9: As an employee, I want to give comments on my supervisor, so that my perspective can be shared
Exception: Employee gets fired
Reviews will be stored/marked separately, but will still be stored so that a full picture can be gathered of the situation
- User story 10: As an investor, I want to give comments on company performance, so that we have clear communication of expectations
Exception: User doesn’t have investor role
User (signed in) will be told their current role and directed to contact their boss/investor coordinator if their role needs to be changed.
- User story 11: As a company director, I want to filter investor comments by time of posting, so that we can discuss them at a relevant time
Exception: The selected time range is invalid, there would be an error message
- User story 12: As an investor, I want to delete comments, so that we can keep things clear if a company changes direction
Exception: Accidentally deleting the wrong comment
Deleted comments will be stored for 14 days in a "recycle bin,” so they can be found/restored but are still separated from the undeleted comments.
