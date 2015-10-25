# portal
an IOT portal to start with.

A simple server which gets data sent by devices in the form of URL parameters.

## TASK DESCRIPTION
We got a few INTERNET-Connected devices, which will be sending data to a serve, data will be sent in simple parameter/value pairs as part of the URL string.

## OPERATION
DEVICE tries to access a page, adds device ID to the URL string along with any other data that may be.
Server parses the data, adds in the database.
user goes to a Web page, LOGs in, sees LIST of Devices, Clicks on Device to see the data uploaded by device.


## DETAILED WORKING
Devices will be coded to access a certain webpage, devices will add parameter/value pairs in the URL string.
called as Query Strings - see https://en.wikipedia.org/wiki/Query_string
Examples:
http://ejaadtech.com/portal?devID=abc123
http://ejaadtech.com/portal?devID=abc123&a1=234&d1=456&a0=3

Every VALID query will have devID key in it along with an ID pair identifying the device.
Each devID will be unique, subject to device firmware, server cannot check/confirm this.
Server will form a TABLE for the device if the devID is not in the devices table and also add the devID to the devices table.

We also dont know how many paramters are there, or what parameters device will send,
Server needs to manage this.

The Server will also record TIME of Query, IP of Query and the whole Query as STRING as well.

When USER logs into the server, a list of Devices is shown to him, upon clicking on the device, user should see the data of the device, in tabular/chart/graph/ form.
Data format and how it is shown to user can be ascertained form the KEY text of the data, for example, a# where # is a number means analog data (simple numbers), d# is similarly digital input data, t# is temperature in Celcius, h# is humidity in percentage.
