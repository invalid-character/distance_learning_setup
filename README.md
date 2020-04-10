# Better Distance Learning System (name TBD)

## The problems:
As a parent, I’ve seen a disjointed system applied to learning at home.  Some teachers get it, others don’t.  The teachers are unwilling or unable to check in with students on a regular basis, giving students enough time to learn on their own, but not so much time that the students lose interest or have their own mistakes reinforced.

As a developer who’s spent a bunch of time in the education sector, I’ve seen some awful UX from a parents’ perspective, bad UX from a grade school child’s perspective.

I can’t evaluate the teachers’ or school administrators’ perspective on the tools I’ve seen, but I’d assume they are equally clunky or non-existent.

For maximum usage, this should start off being web-based and needs to be usable on computers, chromebooks, tablets, and possibly even phones.  (although phones present significant UX challenges)

## What this is not
This will not be an SIS (student information system) (I’m not going down that rabbit hole of PII)

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
