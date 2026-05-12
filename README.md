# Project: Student Registry

> [!IMPORTANT]
> **[View My Product Engineering Process (Slide Deck)](./docs/my-process.pdf)**
>
> *This deck provides some insights into the UX and technical considerations or trade-offs that were made.*

# Starting the App

This is hosted on GitHub Pages: https://d1anas0.github.io/student-registry/, please also run the JSON server locally:
1. run `npm install`
2. run `npm run server:start` to access the aforementioned student & profile details
3. run `npm run start` to access starter app at localhost:3000

# Learnings, Challenges, Assumptions made, Features to be Implemented

- When I initially approached this challenge, I struggled to understand why I was having trouble accessing nested data. At the time I simply got past this by adding a check so that if for whatever reason its not available, it won't crash the app. It was a band-aid fix I know, but had not yet acquired the skills to properly resolve the issue.
  - Upon revisiting this last year, I realised that the issue was rooted in a runtime error due to my implementation of the component, such as for StudentProfile. Additionally, in mounting this component inside of the table body, in a real production environment this likely would have caused performance issues for a large database.
- date formatter: I assumed that the date would always be in the same format.
- Refactored the date formatter intending for it to be a util, though for this specific exercise it may be a little overkill!
- Features that were intended to be included:
  - fully developed UI as suggested in the wireframe, including the editable first/last name text fields.
  - proper error messages for delayed/errored API requests
  - write more tests!
 
   

# Brief

In a school, often teachers needs view and update student details.
Users will land on a simple table listing of registered students. 
Upon selecting the student profile of interest a modal will open, allowing them to edit/update the profile.


# Requirements

In this single-page app, a user should be able to:

- See a list of students in a table with just their full names and date of birth shown in localized format (ie: DD/MM/YYYY)
- When a student is selected from the table, a view of your choice (ie: a modal) will show the following details of the student
  - the student's profile image
  - First name
  - Last name
  - Date of birth
  - Address
    - Street line 1
    - Street line 2
    - Country
    - Postcode
- Only the first name and last names are editable. Other student details are **read only**.
- A teacher could update the first and last names of a student and **persist** it

I was provided the following API endpoints:

```
GET http://localhost:5000/students
GET http://localhost:5000/students/:id
PATCH http://localhost:5000/students/:id
    Example: A request body of { date_of_birth: "foobar" } will update a students date of birth only. See db.json.
GET http://localhost:5000/profiles
GET http://localhost:5000/profiles/:id

```

- Occasionally the student and profile API endpoints may take a longer period of time to process a request, a sensible loading view/message should inform the user of this
- Occasionally the student and profiles API endpoints will be unresponsive and a sensible message should warn the user about their unavailability
- **Do not modify** `./server.js`
- You can use external libraries

