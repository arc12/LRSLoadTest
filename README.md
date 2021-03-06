LRSLoadTest
===========

Learning Record Store (LRS) load testing scripts and notes

Goals
-----
Create a series of reusable scripts (jmeter, etc.) which can be used to load test an LRS and roughly benchmark its ability to handle large numbers of incoming statements.

Usage
-----
- lrs_loadtest.jmx:
	Tests the ability of an LRS to POST and GET random quantities of statements. To run this script, you must set the following user-defined variables prior to usage: 

	- username: the username for the LRS
	- password: the password for the LRS
	- lrsServerUrl: the hostname for the LRS
	- lrsServerPort: the port on the LRS server
	- lrsBasePath: the REST path on the LRS server
	- lrsStatementsPath: the REST endpoint for POSTing and GETting statements} (added to the base path)
	- lrsAboutPath: the REST endpoint for GETting the xAPI version (added to the base path)
	- testDataDir: the directory to the CSV data files (on your local machine)

	This test will post random amounts of statements, and optionally randomly perform a get, depending on the following settings:

	- statementMin: minimum number of statements to post per user
	- statementMax: maximum number of statements to post per user
	- queryMaxLoad: chance to do a GET per statement POST

Test Data
---------

Within the data directory, there are several files that hold test data for posting statements.

- actors.txt:
	Holds test users (actors)
	- columns:
		- name: the users name
		- email: the user's email

- contexts:
	Holds test contexts
	- columns:
		- context: the action context
		- guid: the id of the action context

- objects:
	Holds test objects
	- columns:
		- object: object on which an action is performed

- verbs:
	Holds test verbs
	- columns:
		- verb: the action to perform on an object in a context

Contacts
--------
Post issues in the issue tracker or send questions to:
- Aaron Zeckoski (azeckoski @ unicon.net) (azeckoski @ vt.edu)
- Robert Long (rlong @ unicon.net)
