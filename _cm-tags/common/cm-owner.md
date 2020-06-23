---
title: cm-owner
summary: |
  The contact details of an individual or group who is responsible for management of
  the resource, including escalating issues to the relevant department.
category: Global
types: Email
description: |
  Name and email address of a contact responsible for managing this resource. This is 
  the contact that will be notified in the event of health or maintenance issues, and
  is therefore a technical contact or group.
  
formats:
- token: "\"Name\" [Email]"
  components:
  - key: "\"Name\""
    type: String
    description: The name of the resource owner, as an individual or a group.
  - key: "[Email]"
    type: String
    description: The email address of the resource owner, which may be an individual or group mailbox.
  examples:
  - value: "\"IT\" [support@acme.com]"
    description: |
      Indicates that a contact called "IT" should be contacted to deal with communications
      regarding this resource, using the email address specified.
---
{% include tag-details.html tag=page %}