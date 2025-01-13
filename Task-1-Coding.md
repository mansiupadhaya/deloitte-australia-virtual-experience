# Task 1: Coding 

The first task required the unification of telemetry data for a client - Daikibo Industrials. Upon carefully assessing the code, I could see that the only difference in the data in data-1.json and data-2.json was the format in which the data was represented. 

Apart from spotting the 2 functions that were in need of implementation for the unification of data, the ISO dates were to be converted to milliseconds too.

The goal was to receive an output (screenshot below) with no failures in the tests.

![image](https://github.com/user-attachments/assets/d4147e78-9543-4237-aa3c-68f6f457da5c)

## Steps taken

The steps taken to transform the JSON formats into the unified format are as follows:

For Format 1 (``convertFromFormat1(jsonObject)) ``:
- Split the ``location`` string into parts
The location field is a single string using slashes (/) to separate parts.
split('/') is used to break the string into a list of its components

``locationParts = jsonObject['location'].split('/')``

A new dictionary (``result``) is created with the required unified format

``['japan', 'tokyo', 'keiyō-industrial-zone', 'daikibo-factory-meiyo', 'section-1'] ``

``data`` is also transformed where ``status`` maps from ``operationStatus``; ``temperature`` maps from ``temp`` 

The changes made result in the following output format

``{
    "deviceID": "dh28dslkja",
    "deviceType": "LaserCutter",
    "timestamp": 1624445837783,
    "location": {
        "country": "japan",
        "city": "tokyo",
        "area": "keiyō-industrial-zone",
        "factory": "daikibo-factory-meiyo",
        "section": "section-1"
    },
    "data": {
        "status": "healthy",
        "temperature": 22
    }
}``

Format 2 (``convertFromFormat2(jsonObject``):

The ``timestamp`` is in ISO format. ``datetimme.datetime.strptime()`` is used to parse the string into ``datetime`` object:

``date = datetime.datetime.strptime(jsonObject['timestamp'], '%Y-%m-%dT%H:%M:%S.%fZ')``

The difference from the Unix epoch (1970-01-01) is calculated to get the timestamp in seconds, then multiplied by 1000 to convert to milisecnds

``timestamp = round(
        (date - datetime.datetime(1970, 1, 1)).total_seconds() * 1000)``

## A quick summary of the functional steps

Format 1
- Split ``location`` string into parts
- Create the nested ``location`` dictionary
- Map ``operationStatus`` and ``temp`` to ``data``

Format 2 
- Convert ISO 8691 ``timestamp`` to milliseconds
- Extract fields directly or from nested objects
- Assemble the unified structure with consistent keys and nesting





