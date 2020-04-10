# Better Distance Learning System (name TBD)

## The problems:
As a parent, I’ve seen a disjointed system applied to learning at home.  Some teachers get it, others don’t.  The teachers are unwilling or unable to check in with students on a regular basis, giving students enough time to learn on their own, but not so much time that the students lose interest or have their own mistakes reinforced.

As a developer who’s spent a bunch of time in the education sector, I’ve seen some awful UX from a parents’ perspective, bad UX from a grade school child’s perspective.

I can’t evaluate the teachers’ or school administrators’ perspective on the tools I’ve seen, but I’d assume they are equally clunky or non-existent.

For maximum usage, this should start off being web-based and needs to be usable on computers, chromebooks, tablets, and possibly even phones.  (although phones present significant UX challenges)

This needs to be easy for educators to pick up and run with.  It needs to be able to be used by a variety of different ages and skill levels.

This SHOULD be easily internationalized. (Use image icons as much as possible) (Not MVP)

## What this is not
This will not be an SIS (student information system) (I’m not going down that rabbit hole of PII) This may eventually turn into a full LMS.

## The user roles
### System administrator: 
(1..many) these people can keep the system running.  They add users, adjust rights and defaults.  They deal with low level, technical details.  They cannot see any reports.  They are able to TTL (time to live) for any messages, uploads, etc.

### School administrators: 
(1..many) These people deal with the daily non-educational aspects of running the software, they can add users, adjust rights, see reports. They are able to set some defaults such as days.  They can schedule sessions. They can make global announcements.

### Educators: 
(many) These people are in charge of individual class sessions.  They have full rights for sessions they “own”. They can create reports, assignments, tests.  They can mute/unmute the entire class or individual students.  They can see and clear when a student toggles the “raise hand” flag.  They can toggle between their own camera, desktop, or whiteboard view (or possibly any combination of them). They are allowed to upload files.  They are able to initiate DMs with any student, or all parents of a student in one of their classes.  They are able to initiate DMs with any other educator or school admin.

### Para Professionals: 
(many) [necessary?] These people can be given rights by School admins or educators. (most, if not all educator rights are identical)

### Students: 
(many) They are assigned to be a 1 class session at a time.  They are not allowed to join a session they are not part of.  They are, however, allowed to stay in a session they are  already part of (class goes long)  They are allowed to see reports.  They are allowed to see assignments, they are allowed to make copies of assigned files and edit them.  They are allowed to upload files only when they can associate them with an assignment.  They must be allowed to mute themselves and turn off their own cameras. They are able to mark assignments as “complete”.  They are able to initiate DMs with any teacher they are in a class with or with any school admin.

### Parents: 
(1..many per student) They are able to view assignments. They are able to (with teacher permissions) view reports of complete/incomplete assignments. They are able to see students’ reports.

### notes:
each person may have 1 or more roles

## User:
* required email
* required firstname
* lastname
* schoolID
* SIS ID

* There should be an easy, securely random invite code for parents
* parent links to students will need to be approved by a student's teacher or school admin

## Groups
* In order to help break things out, there can optionally be groups or departments.
* Each group will have 1 or more admin which can add or remove people and promote others to admin
* Each group will have a persistant chat 
* Only School admins can create groups
* There's no limit to the combination of groups and users


## School Structures
## calendar
a series of events and periods in chronological order

## periods
a timeslot - may exist on any day and may float around on a rotating schedule
admin defined

## Classes:
* Each “class” will be a period/educator(s) combination.
* it will have a Name, a description, and optionally an icon
* Each class will have 1 or more sessions. (e.g. days the class can appear on)
* The class will have at least 1 educator assigned to it.  The educators are in control of the class.
* The class will have at least 1 student assigned to it.
* The class will have a video conference assigned to it, with separate audio and video controls
* The class will have a whiteboard assigned to it.  If used, the whiteboard will be saved at the end of session, in addition to any time the educator triggers a save.
* The class will have 1 persistent message board, with the teacher able to mark any post as hidden.
* The educator can upload files for students or other educators to download.  These will persist and be assigned to the class and class session.
* Class participation is mutually exclusive. (e.g. you cannot have a student or educator in multiple simultaneous classes)
* Students will be able to toggle a “raise hand” flag to alert educators to an immediate question/need.
* Educators will be alerted to this via audio and visual cues.  They will be able to turn this off, and optionally respond via DM.
* educators will have a way of determining which students are "present"
* educators will have a way of seeing that a student is still in class with another educator

## Class Sessions
* Each class session will not necessarily be at the same time each day (e.g. Blue day it may be period 1, Yellow day, it may not exist, Orange day, it may be period 5)
* The class session will have 0..many assignments assigned. These can be assigned in advance, during or after the class.


## Assignments
* There should be a text field accompanying all assignments.
* 0..many files can be attached to an assignment.
* Educator determines response types (video, audio, text, file, attachment markup, etc)
* Each assignment will have a “completed” flag which can be toggled by the educator and student.
* Each assignment/student pair will have a “response”
* The educator can toggle 2 “discussion” fields where students can discuss the assignment with other students and the educator or only the educator (the latter will be attached to the response).
* Educators can toggle if parents can see the response, discussion, grade

## assignment responses
* Each assignment response can be given a grade.
* For any response, the educator can override other defaults to allow parents to see responses, grades, discussions, etc they would not otherwise be able to see.
* students, educators (for that class) and 

## Messaging
* Administrators can initiate a message to any role, group or person
* For legal reasons, the messages will be kept, but encrypted at rest
* every group and class will have a persistant chat attached to it

# grading (not MVP)
* assignements can recieve a weighting
* responses can receive a point grade

## backend
* Users, groups, periods and classes will need to be imported via CSV

* uploaded files WILL NOT be considered private

