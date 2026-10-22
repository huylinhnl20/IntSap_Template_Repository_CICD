# Test Messages Guidelines
## Introduction
This folder is for test messages that can be used to test the operations of the service. We can distinguish between several types of test cases:
- Test cases that do not contain environment specific variables and will therefor work in all environments;
- Test cases that contain environment specific variables and will only work in a specific environment;
- Test cases that consists out of multiple steps, where first a specific object is created, in order to use that object within another step.

In order to structure all test cases in a generic way, please adhere to the following guidelines:
- All messages that are related to one another, should be placed in the same test case folder. All test case folders have to be named *Operation_TestCase_x*, where *x* has to be the next available number;
- All request messages should be named *Operation_Request*. In case the test cases consists out of multiple steps, the prefix *x_* has to be added, where *x* has to be the next available number;
- All response messages should be named *Operation_Response*. In case the test cases consists out of multiple steps, the prefix *x_* has to be added, where *x* has the same value as for the corresponding request;
- All test cases that contain environment specific variables, should be placed in a environment specific folder, e.g. *PO5*.

## Examples
In the table below various example are given.
| Scenario | Folder location | Messages |
| ----------------- | ----------------- | ----------------- |
| No environment specific variables | Test_Messages/GetStandardizedAddress_TestCase_1 | GetStandardizedAddress_Request<br>GetStandardizedAddress_Response |
| Environment specific variables | Test_Messages/PO6/GetProposition_TestCase_1 | GetProposition_Request<br>GetProposition_Response |
| Multiple steps | Test_Messages/GetBusinessPartner_TestCase_1 | 1_CreateBusinessPartner_Request<br>1_CreateBusinessPartner_Response<br>2_GetBusinessPartner_Request<br>2_GetBusinessPartner_Response |

In the *Multiple steps* example above, first a new business partner is created. The business partner number in the CreateBusinessPartner response can then be added in the GetBusinessPartner request.
