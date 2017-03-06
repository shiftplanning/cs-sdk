ShiftPlanning C# SDK
================

The [ShiftPlanning API](http://www.humanity.com/api/) allows you to call modules within the ShiftPlanning [employee scheduling software](http://www.humanity.com/) that respond in REST style JSON & XML.

This repository contains the open source C# SDK that allows you to utilize the above API in your applications. Except as otherwise noted, the ShiftPlanning C# SDK is licensed under the Apache Licence, Version 2.0 http://www.apache.org/licenses/LICENSE-2.0.html)


Usage
-----

The [examples][examples] are a good place to start. The minimal you'll need to
have is:

	 //initialize SDK where 'XXXXXXXXXXXXXXXXXX' = API Key
         shiftPlanning = new ShiftPlanning("XXXXXXXXXXXXXXXXXX");


Logged in vs Logged out:

	if (shiftPlanning.getLoginStatus())
	{
		//LOGGED IN

	}
	else
	{
		//LOGGED OUT

	}


To make [API][API] calls:

	// call to update wages of employee 101

	//preparing list of request fields
	RequestFields employee_data = new RequestFields();
	employee_data.Add("id", 101);
	employee_data.Add("wage", 25);

	response = shiftPlanning.updateEmployee(employee_data);
	if (response.Status.Code == "1")
	{
		// Success
	}

####Adding SDK to a new project

If you create a new project, you need to add the following files

* APIRequest.cs
* APIResponse.cs
* DataFields.cs
* RequestFields.cs
* ShiftPlanning.cs

from ShiftPlanning C# SDK into your project. (Right click on the project, Add, Existing item…, select files, and Add As Link)

With sources imported you will be able to easily debug, add your own methods in ShiftPlanning.cs, or to change existing if you need.

Feedback
--------

We are relying on the [GitHub issues tracker][issues] linked from above for
feedback. File bugs or other issues [here][issues].

[issues]: http://github.com/shiftplanning/cs-sdk/issues