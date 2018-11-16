# Object-Oriented-Tests
Qualified.io challenge: you are going to build a mock comments section.

## Design
We're going to focus on two aspects:

### Users

Users come in 3 variants, normal users, moderators, and admins. Normal users can only create new comments and edit the their own comments. 

Moderators have the added ability to delete comments (to remove trolls), while admins have the ability to edit or delete any comment.

Users can log in and out, and we track when they last logged in


### Comments

Comments are simply a message, a timestamp, and the author.

Comments can also be a reply, so we'll store what the parent comment was.


# Your Challenge
This is challenge is not about building a fully functional API, but more about focusing on the design from an object-oriented point-of-view.

We've provided the basic API (which is incomplete), which we would like you to complete being aware of the following Object-Oriented Programming concepts:

## Encapsulation of Properties

All classes should have no publicly accessible fields, so the required fields should be 'private'.

The method-based API is provided and these methods should be completed as they are.
Additional methods are allowed, though remember to keep read-only properties read-only.

The classes have lower case names, we're aware this is unconventional, but for some reason this tool doesn't like them to be capitalised (so don't change them).


## Instantiation

Classes should be instantiated with properties (as provided), to create instances with values already assigned.
user/moderator/admin defaults:

Should be marked as not logged in
Should return None for the last logged in at property

Comment defaults:
Should set the current timestamp for the created at property upon instantiation
Replied To is optional, and should be None if not provided.

## Inheritance & Access Control

Note: for the sake of simplicity, you can simply treat object equality as "equal", though more complete solutions will also pass.

### user

Users can be logged in and out.

When logging in, set the last_logged_in_at timestamp. Do not modify this timestamp when logging out

Users can only edit their own comments

Users cannot delete any comments

moderator is a user

Moderators can only edit their own comments

Moderators can delete any comments

admin is both a user and a moderator

Admins can edit any comments

Admins can delete any comments


## Composition

Comments contain a reference to the User who created it (author)
Comments optionally contain a reference to another comment (replied_to)
When converting to a string (to_string), the following format is used:

No replied to:

>«message» by «author.name»

With replied to:

>«message» by «author.name» (replied to «replied_to.author.name»)

Beyond these basics, you are free to add to the API, but only these concepts will be scored automatically.
