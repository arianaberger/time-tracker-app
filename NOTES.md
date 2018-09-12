Questions:
- Correct DB setup?
- ApplicationRecord?

------------

USER
- name
- email
- password
- title
- password_digest (schema)
- has_secure_password (model)

has_many :projects
has_many :clients, through: :projects


CLIENT
already clients
create new

- name

- has_many :projects
- has_many :users, through: :projects


PROJECT (JOIN)
- name
- deadline
- status

- has_many :entries
- belongs_to :client (schema, model)
- belongs_to :user (schema, model)


ENTRY
- date
- time
- notes

time: start_time
end_time:

- belongs_to :project (needs foreign key)
*- has_many :tags*



*---
TAGS (NEED ANOTHER JOIN?)
- description

- has_many :entries, through: entry_tags
- has_many :entry_tags*


Nested routes

clients/1/projects -> show (index) + create a new project?
-> post to clients/1/projects (then create, redirect to that project[:id])

projects/1/entries [index] + create a new one from this page
-> post to projects/1/entries + redirect_to entry page