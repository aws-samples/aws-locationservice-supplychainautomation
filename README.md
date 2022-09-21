## Supply Chain Automation

This example contains the cloud formation template to create AWS resources (AWS IoT Core, Amazon Location Service, Amazon RDS, Amazon EventBridge, AWS Lambda, Amazon SES), and code assets for AWS Lambda. Scripts to create the database schema and sample data. GeoJSON files for creating the geofences.

The scripts to create table schemas and sample data can be found [here](dbscripts/db_scripts.sql)

The GeoJSON file for creating geofences can be found [here](geofences/)

The cloudFormation stack includes three Lambda functions. The details are as follows:

**vcs-iot-messageparser**

Processing events from IoT and performing the following actions.
1.	Validate the vehicle information 
2.	Update the vehicle's current Status

**vcs-amazon-location-service-eventparser**

For processing events from Amazon Location and performing the following actions
1.	Identify the dealership corresponding to the geofence 
2.	Retrieve the dealer notification information
3.	Update vehicle's current status 
4.	Send an email notification

**vcs-iot-simulator**

Used for generating GPS locations and publishing it to AWS IoT Core. Invoking the Lambda will generate three sets of events (transit events indicating that the vehicle is en route, entry events indicating that the vehicle is entering the geofence, and exit events indicating that the vehicle is exiting the geofence). 

==============================================

Copyright 2020 Amazon.com, Inc. or its affiliates. All Rights Reserved.

SPDX-License-Identifier: MIT-0

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the [LICENSE](LICENSE) file.

