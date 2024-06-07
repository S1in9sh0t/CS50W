# CS50W: Capstone Project - SmashBoxVM

## Distinctiveness and Complexity

This project aims to develop an application similar to deliberately vulnerable security projects such as OWASP Juice Shop, DVWA and WebGOAT. Fully realised, I believe this will satisfy the distinctiveness and complexity requirements mentioned at the [CS50W capstone project](https://cs50.harvard.edu/web/2020/projects/final/capstone/) page. Implementing common vulnerabilities, such as listed below, a leaderboard system with user account and session management is distinct from all of the projects that are part of the courseware provided.

In alignment with my day to day work as a security consultant and penetration tester, developing this application will not only broaden my technical skillset and understanding, but directly contribute to my effectiveness as a regular advisor to the development teams I work with.

## Frontend

Making the website dynamic, a landing page updated regularly with the exploit statistics of the participating userbase is generated with each refresh of the page. Side-by-side view of the login form fields and a rotation of the latest successes displayed with usernames and scores. This is deliberately insecure practice, as it provides an ever rotating username enumeration carousel for anyone on the outside of the application looking to get in.

### Account Management

- Admin/Standard RBAC
  - User registration
  - Login
  - Forgotten password
  - File upload
  - File deletion
  - Comments
  - User create/edit/delete (Admin)

### Site Pages

- Landing page
  - Login form fields
  - Password reset function
- Scoreboard
  - Search function
    - Username
    - Type of exploit
    - Number of exploits
- User account
  - Avatar upload
  - Biography form field
  - Comments from other users
  - Username change
  - Password reset
  - Account deletion
- List of exploits and brief explanations
  - Each exploit has a page where you can find a working example of the vulnerability

## Backend

### SQL DB

- Users: Populate the DB with fake users and scores for testing
  - Username
  - Password/Passphrase
  - Personal exploit score
  - Avatar
  - Comments
- Vulnerabilities
  - XSS
  - SQLi
  - Path Traversal
  - LFI
  - File Upload Abuse
  - Account Takeover
  - Privilege Escalation
  - RCE
- Scoring
  - Total successful exploits
  - Total attempted exploits
  - User with highest number of successes
  - User with highest number of a particular success
  - Most common success
  - Most active user
  - Highest consecutive nuber of exploits

---

### Road Map

Further development is planned as this application is built. This is a lot to include already alongside learning Python and JavaScript programming, but we should end up with a working prototype for a security training VM.

Eventually, I would like to have the site periodically generate random new users and scores to maintain the dynamism of the application. This way, when the repository is cloned locally and not hosted online, it adds a sense of competition.

### Timeline

The CS50W course material spans nine weeks over six projects. The aim is to condense down my learning and create the capstone project alongside the course materials provided. To elaborate, a full day may include one half of studying the material and completing tasks with the remainder used for developing my own application.

