# Backend Technical Server specs

## Business Goal:

A language learning school wants to build a prototype of a learning portal which will act as three things:
- Inventory of possible vocabulary that will be learned
- Act as a record learning store: providing correct and wrong score on practice vocabulary
-  A unified launchpad to launch different learning apps

## Technical Requirements

- The backend will be build using go
- The database will be SQLite
- The API will be built using Gin
- The API will return JSON
- There will be no authentication or authorization
- Everything will be treated as a single user

## Database Schema

We have the following table:
- Words - stores vocabulary
  - id interger
  - Swahili string
  - English string
  - Parts json
- Word_groups - join table for words and groups many-to-many
  - id interger
  - word_id interger
  - Group_id interger
- Groups - thematic groups of words
  - id interger
  - name string
- Study_sessions - records of study sessions
  - id interger
  - study_session_id interger
  - group_id interger
  - study_activity interger
- Study_activities - a specific study activity 
  - id interger
  - study_session_id interger
  - created_at datetime
- word_review_items - Record of word practice, determine if the word was correct or not
  - id interger
  - study_session_id interger
  - correct boollean
  - created_ datetime


### API Endpoints

- GET /words
- GET /words/:id
- GET /groups/:id/words