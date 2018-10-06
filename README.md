# Amazon_Pay_Reprocess_OROs
This .NET Form desktop app is intended on helping merchants' customer service team process orders that fail. For example, when a merchant receives a decline and the order goes into a suspended state, they may not have a way to allow them to recover and retry an auth to capture funds via Seller Central. This tool will allow them to do that.

# How to use this Utility
To use the utility, create use the AmazonPay.txt file attached to configure your MWS Keys and the properties of the file. The default setup will be pointing to production.

The "Get Status" button calls GetOrderReferenceDetails , GetAuthorizationDetails, GetCaptureDetails, and GetRefundDetails APIs. These APIs include each of those corresponding transactions into a single line per authorization. 

The "Authorize/Capture when Suspended" button calls ConfirmOrderReference and Authorize (with captureNow = true) to change the status of the Order Reference Object from "Suspended" to "Open", then authorizes and captures for the amount specified in the amount field. 

The "Authorize/Capture (ORO State: Open)" button calls Authorize (with captureNow = true) to authorize and capture for the amount specified in the amount field.

The "Already Authorized - Just Capture" button calls Capture to capture against the corresponding authorization transaction id listed.The authorization transaction id would go into the "Amazon ID" text box.

The "Refund" button calls Refund to refund against each corresponding capture based on the authorization transaction id listed. The authorization transaction id would go into the "Amazon ID" text box. 


# Minimum Requirements
To execute the AmazonPay_Reprocess_Transactions.exe file, you must have .NET Framework 3.0 SP1 (minimum requirement).

# Usage of the Utility
Please note: use this tool at your discretion. You will need to keep the AmazonPay.txt file locked down internally so that unauthorized access to the AmazonPay.txt file is not provided to other members of the organization.
