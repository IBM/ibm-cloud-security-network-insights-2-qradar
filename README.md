<!-- This should be the location of the title of the repository, normally the short name -->
# ibm-cloud-security-network-insights-2-qradar

## Scope

The purpose of this project is to provide a mechanism for ingesting IBM Cloud Security Network Insights into QRadar using the Universal Cloud REST API protocol.

# Pre-Requisites

## IBM Cloud

IBM Cloud account(s) with privileges to:
1. User account to create and configure Network Insights
2. User or service account for accessing the Findings API

IBM Cloud Security Advisor Network Insights:
    Follow the guide to setup at least one Virtual Private Cloud (VPC) network interface flow logs to detect any suspicious activity by using learned patterns and threat intelligence. See [Enabling Network Insights](https://cloud.ibm.com/docs/security-advisor?topic=security-advisor-setup-network)


## QRadar
1. The Universal Cloud REST API protocol is supported on QRadar 7.3.2 or later, and you must have the QRadar Log Source Management app installed. For information on how to install the app, see Installing the QRadar Log Source Management app.
For Universal Cloud REST API protocol examples, see [GitHub samples](https://github.com/ibm-security-intelligence/IBM-QRadar-Universal-Cloud-REST-API).
2. IBM QRadar user account with privileges to create/modify log sources and create/modify DSMs.
3. Reference the [Universal Cloud REST API](https://www.ibm.com/docs/en/qsip/7.4?topic=configuration-universal-cloud-rest-api-protocol) for additional information.

## Setup QRadar using the Universal Cloud REST API

The parameters needed to configure the Univeral Cloud Rest API require information specific to the instance of IBM Cloud Security Insights. The following information will need to be put into the Workflow Parameters. 
1. api_key: [Create an API key](https://cloud.ibm.com/docs/account?topic=account-manapikey) to generate the access token for the [Findings API](https://cloud.ibm.com/apidocs/security-advisor/findings)
2. endpoint_url: The [Endpoint URL](https://cloud.ibm.com/apidocs/security-advisor/findings) for the desired location. Only use the FQDN and not the full URL. For example, use "us-south.secadvisor.cloud.ibm.com". Do NOT use the full URL "https://us-south.secadvisor.cloud.ibm.com/findings". 
- You can find the right endpoint_url at [Findings Endpoints](https://cloud.ibm.com/apidocs/security-advisor/findings#endpoints) based upon your [Location](https://cloud.ibm.com/docs/security-compliance?topic=security-compliance-mng-data#storage-location-api) setting.
3. account_id: Go to the [Account settings](https://cloud.ibm.com/account/settings) page in the console to view your account ID and account type.


# QRadar Log Source Configuration

1. Log in to QRadar.
2. Click the _Admin_ tab.
3. To open the app, click the _QRadar Log Source Management_ app icon.
4. Click _New Log Source_ > Single Log Source.
5. On the Select a Log Source Type page, _Select a Log Source Type (Universal DSM)_ and click _Select Protocol Type (Universal Rest API)_.
6. On the Select a Protocol Type page, select a protocol and click _Configure Log Source Parameters_.
7. On the Configure the Log Source parameters page, configure the log source parameters and click _Configure Protocol
Parameters_.
8. On the Configure the Protocol Parameters page, configure the protocol-specific parameters (Workflow and Workflow
Parameter Values). 
9. In the Test protocol parameters window, click _Start Test_.
10. To fix any errors, click _Configure Protocol Parameters_. Configure the parameters and click Test Protocol Parameters.
11. Click _Finish_

<!-- A notes section is useful for anything that isn't covered in the Usage or Scope. Like what we have below. -->
## Notes

If you have any questions or issues you can create a new [issue here](https://github.com/mdobbsatl/ibm-cloud-security-network-insights-2-qradar/issues).

Pull requests are very welcome! Make sure your patches are well tested.
Ideally create a topic branch for every separate change you make. For
example:

1. Fork the repo
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## License

All source files must include a Copyright and License header. 

If you would like to see the detailed LICENSE click [here](LICENSE).

```text
#
# Copyright 2020- IBM Inc. All rights reserved
# SPDX-License-Identifier: Apache2.0
#
```

