# Introduction

This repository contains my personal ideas for potentially upcoming projects.

# List

- [Synchronise EduPage with Google Calendar](#synchronise-edupage-with-google-calendar)

## Synchronise EduPage with Google Calendar

Synchronise all new tasks (HW, Project) and assignmets (Test) in EduPage with your personal Google Calendar account by creating new event for specific occasion.

Each task has specific:

- name of subject
- task type
- task title
- deadline - date and time

e.g.

- event title: "*MAT (Project) - Project about linear functions*"
- deadline set: "*2022/02/22 12:00 PM*"

Each assignmet has specific:

- name of subject
- assignmet title
- date and time of event (from - to)

e.g.

- event title: "*MAT (Test) - Equations with fractions*"
- date and time set: "*2022/02/22 01:15 PM - 02:00 PM*"

Script which will be checking for a new tasks and assignmets, will be executed in certain time during day (e.g. *02:00 PM* and *08:00 PM*). Script will be stored at local server.

### Technologies to use

- Python v3 - Google API, EduPage API
- server storage (e.g. Raspberry Pi)
