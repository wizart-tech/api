We developed our API to help our clients to manage their data in WIzart PIM. The API use REST approach based on JSON format. In our
developing we are going to standardise the API and our goal is full supporting JSON:API v1.1 specification. More details
about the specification you can found here [JSON:API Specification](https://jsonapi.org/format/1.1/).

To support old
version of the API we are using [semantic versioning 2.0.0](https://semver.org/)

## Versions lifetime

| **Version** | **Release** | **End of supporting** |
| --- |-------------|-----------------------|
| 2.0 |             | 01.06.2021            |
| 2.1 | 14.04.2022  | 01.01.2023            |

# API Authentication and Authorization

We support two types of authorization: OAuth 2.0 and token-based
authorization. We use OAuth 2.0 for data manipulation where we need the best possible data protection. The token based
authorization we use to get the data. You can found any token in your account
in [PIM Admin](https://pim-admin.wizart.ai/configuration/web). See the detail
instruction [here](https://wizart.atlassian.net/wiki/spaces/WDP/pages/1744994307/API+authentication+and+authorization).

For
each of our methods, the type of authorization supported was marked.

| **Authorization type** | **Description** |
|--- |------------------------------------------------------------------------------------------|
| Bearer Token | The authorization method based on OAuth 2.0. We usually use this method to process data. |
| Web Token | We use it for web integrations on the client's websites.                                 |
| Android Token | We use it for integrations from android apps.                                            |
| Ios Token | We use it for integrations from Ios apps.                                                |
| Direct Token | We use this token for our partners who wants to build their own services based on our API. |

 **Note:** It is very important
to use the correct token as we are optimizing our responses for devices and some API methods may not be available for
another tokens.

# Checking import status

 **Information:** ‘**importId**’ is the ID of the import. You can get it
using [Other API methods | Getting-all-imported-data](https://wizart.atlassian.net/wiki/spaces/WDP/pages/2176712714/Other+API+methods#Getting-all-imported-data)
, or you can check the name of your log file.

You can come across the following statuses/notifications:

| **Status** | **Description**                                  | **State** |
| --- |--------------------------------------------------| --- |
| uploading_files | Upload the files that you’re sending to the PIM. | intermediate status, import in progress |
| validating_csv | Make sure your CSV has all required fields completed, as well as no changes in the structure of the original CSV template. If you get an error at this stage, please check [File upload requirements \\[wall product types\\]](https://wizart.atlassian.net/wiki/spaces/WDP/pages/2199289857) or [File upload requirements \\[flooring\\]](https://wizart.atlassian.net/wiki/spaces/WDP/pages/2198208539/File+upload+requirements+flooring). | intermediate status, import in progress |
| unpacking_archive | Extract the uploaded images from the archive. | intermediate status, import in progress |
| checking_images | Make sure your CSV is not missing any images from the ZIP archive. | intermediate, in progress |
| waiting_queue | Waiting for free workers to start the import. | in progress |
| importing_data | The import is in progress. | in progress |
| success | You’ll get the ‘success’ notification if the import was finished without any errors and warnings, which means that all the products **have been successfully imported**. | import finished |
| warning | You’ll get the ‘warning’ notification if the import was finished without any errors but with some warnings. Your CSV file might contain some non-critical errors, for example, incorrect value type. **Some** of the products **might not have been imported**. Please note that **the products whose records contain errors will be skipped**, but the import of the other products will be still in progress. | import finished |
| failure | If you see the ‘failure’ notification, the import was finished with some errors. Usually, it is a server error. **All the products before this error occurred** will be **successfully imported** to the PIM, **the other products will have to be re-imported**. Please note that **the products with a fatal error will stop the import process**; however, the products imported before the error occurred will be successfully imported. | import finished |

## Integration
Documentation

 *   [API Authentication And Authorization](https://wizart.atlassian.net/l/c/KCbDaQrX)

*   [Import](https://wizart.atlassian.net/l/c/8MPtY1aw)


# Support

You can create a bug report and ask questions
via our official [GitHub repository](https://github.com/wizart-tech/api).

