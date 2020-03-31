# Software requirements specification (SRS)

## The purpose of the application

To provide a gui application for relational data administration for David DBMS.
David is a relational DBMS designed by me.
I recently wrote a simple client program for it called Sling that takes care of communication over network between a client and David server.
So in this project I will build a gui app that uses Sling to communicate with David.

## Users

Bow connects to a David server using credentials and it is up to David to determine the user rights. So Bow has only one type of user who connects to one or more servers using different credentials.

## Draft of the user interface

Here is a preliminary draft of the user interface.

<img src="gui_draft.png">

On the left we have DbObjects Tree. This shows all the database objects like
1. Relvars and Views
2. Constraints
3. Domains
DbObjects are organized in a hierarchical fashion like filesystem. So there will be also Folder objects but they have only organisational function.

Of course there needs to be a dialog where user can specify the url and credentials for the dbms he wants to administer. I will limit Bow so that the user can have only one connection open at a time.

On the right side we see the DataArea. This is tabbed so that user can have open as many queries at a time as he wants. This area is divided into TableView where we show results of the query, QueryArea where user can define the input he wants to send to the server and MonitoringArea that reports about important events happening at the protocol level and especially all the exceptions that the server (or client) throws.

## Functionality

- define different connections to David servers
- ability to connect to one server at a time
- ability to see all the DbObjects in a tree
- ability to write input in D* language, send it to server and show results or errors
- ability to create new tabs in the DataArea
