# SendSmsMessageResult class

Returns the message delivery status (success or failure) and exceptions (if any) that occur while sending the text message to the target mobile phone numbers.

Following is a list of its members with description:

- [SendSmsMessageResult.ExceptionMessage](/docs/product_docs/groupid/groupid/admincenter/smsgateway/custom/sendsmsmessageresult/exceptionmessage.md)
- [SendSmsMessageResult.Message](/docs/product_docs/groupid/groupid/admincenter/smsgateway/custom/sendsmsmessageresult/message.md)
- [SendSmsMessageResult.Success](/docs/product_docs/groupid/groupid/admincenter/smsgateway/custom/sendsmsmessageresult/success.md)

| Member | Description |
| --- | --- |
| ExceptionMessage property | Gets the exception message if one occurs while sending the text message. |
| Message property | Returns the [ShortMessage class](/docs/product_docs/groupid/groupid/admincenter/smsgateway/custom/shortmessage/class.md) object processed by the [ISmsGateway.SendShortMessage](/docs/product_docs/groupid/groupid/admincenter/smsgateway/custom/sendshortmessage.md) method. |
| Success property | Returns a boolean value indicating whether the text message is successfully sent to the target mobile phone numbers. |

__See Also__

- [ISMSGateway Members](/docs/product_docs/groupid/groupid/admincenter/smsgateway/custom/overview.md)
