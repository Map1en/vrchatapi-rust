# \InviteApi

All URIs are relative to *https://api.vrchat.cloud/api/1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_invite_message**](InviteApi.md#get_invite_message) | **GET** /message/{userId}/{messageType}/{slot} | Get Invite Message
[**get_invite_messages**](InviteApi.md#get_invite_messages) | **GET** /message/{userId}/{messageType} | List Invite Messages
[**invite_myself_to**](InviteApi.md#invite_myself_to) | **POST** /invite/myself/to/{worldId}:{instanceId} | Invite Myself To Instance
[**invite_user**](InviteApi.md#invite_user) | **POST** /invite/{userId} | Invite User
[**invite_user_with_photo**](InviteApi.md#invite_user_with_photo) | **POST** /invite/{userId}/photo | Invite User with photo
[**request_invite**](InviteApi.md#request_invite) | **POST** /requestInvite/{userId} | Request Invite
[**request_invite_with_photo**](InviteApi.md#request_invite_with_photo) | **POST** /requestInvite/{userId}/photo | Request Invite with photo
[**reset_invite_message**](InviteApi.md#reset_invite_message) | **DELETE** /message/{userId}/{messageType}/{slot} | Reset Invite Message
[**respond_invite**](InviteApi.md#respond_invite) | **POST** /invite/{notificationId}/response | Respond Invite
[**respond_invite_with_photo**](InviteApi.md#respond_invite_with_photo) | **POST** /invite/{notificationId}/response/photo | Respond Invite with photo
[**update_invite_message**](InviteApi.md#update_invite_message) | **PUT** /message/{userId}/{messageType}/{slot} | Update Invite Message



## get_invite_message

> models::InviteMessage get_invite_message(user_id, message_type, slot)
Get Invite Message

Returns a single Invite Message. This returns the exact same information but less than `getInviteMessages`. Admin Credentials are required to view messages of other users!  Message type refers to a different collection of messages, used during different types of responses.  * `message` = Message during a normal invite * `response` = Message when replying to a message * `request` = Message when requesting an invite * `requestResponse` = Message when replying to a request for invite

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**user_id** | **String** | Must be a valid user ID. | [required] |
**message_type** | [**InviteMessageType**](.md) | The type of message to fetch, must be a valid InviteMessageType. | [required] |
**slot** | **i32** | The message slot to fetch of a given message type. | [required] |

### Return type

[**models::InviteMessage**](InviteMessage.md)

### Authorization

[authCookie](../README.md#authCookie)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_invite_messages

> Vec<models::InviteMessage> get_invite_messages(user_id, message_type)
List Invite Messages

Returns a list of all the users Invite Messages. Admin Credentials are required to view messages of other users!  Message type refers to a different collection of messages, used during different types of responses.  * `message` = Message during a normal invite * `response` = Message when replying to a message * `request` = Message when requesting an invite * `requestResponse` = Message when replying to a request for invite

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**user_id** | **String** | Must be a valid user ID. | [required] |
**message_type** | [**InviteMessageType**](.md) | The type of message to fetch, must be a valid InviteMessageType. | [required] |

### Return type

[**Vec<models::InviteMessage>**](InviteMessage.md)

### Authorization

[authCookie](../README.md#authCookie)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## invite_myself_to

> models::SentNotification invite_myself_to(world_id, instance_id)
Invite Myself To Instance

Sends self an invite to an instance

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**world_id** | **String** | Must be a valid world ID. | [required] |
**instance_id** | **String** | Must be a valid instance ID. | [required] |

### Return type

[**models::SentNotification**](SentNotification.md)

### Authorization

[authCookie](../README.md#authCookie)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## invite_user

> models::SentNotification invite_user(user_id, invite_request)
Invite User

Sends an invite to a user. Returns the Notification of type `invite` that was sent.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**user_id** | **String** | Must be a valid user ID. | [required] |
**invite_request** | [**InviteRequest**](InviteRequest.md) | Slot number of the Invite Message to use when inviting a user. | [required] |

### Return type

[**models::SentNotification**](SentNotification.md)

### Authorization

[authCookie](../README.md#authCookie)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## invite_user_with_photo

> models::SentNotification invite_user_with_photo(user_id, image, data)
Invite User with photo

Sends an photo invite to a user. Returns the Notification of type `invite` that was sent.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**user_id** | **String** | Must be a valid user ID. | [required] |
**image** | **std::path::PathBuf** | The binary blob of the png file. | [required] |
**data** | [**models::InviteRequest**](InviteRequest.md) |  | [required] |

### Return type

[**models::SentNotification**](SentNotification.md)

### Authorization

[authCookie](../README.md#authCookie)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## request_invite

> models::Notification request_invite(user_id, request_invite_request)
Request Invite

Requests an invite from a user. Returns the Notification of type `requestInvite` that was sent.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**user_id** | **String** | Must be a valid user ID. | [required] |
**request_invite_request** | Option<[**RequestInviteRequest**](RequestInviteRequest.md)> | Slot number of the Request Message to use when request an invite. |  |

### Return type

[**models::Notification**](Notification.md)

### Authorization

[authCookie](../README.md#authCookie)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## request_invite_with_photo

> models::Notification request_invite_with_photo(user_id, image, data)
Request Invite with photo

Requests with photo an invite from a user. Returns the Notification of type `requestInvite` that was sent.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**user_id** | **String** | Must be a valid user ID. | [required] |
**image** | **std::path::PathBuf** | The binary blob of the png file. | [required] |
**data** | [**models::RequestInviteRequest**](RequestInviteRequest.md) |  | [required] |

### Return type

[**models::Notification**](Notification.md)

### Authorization

[authCookie](../README.md#authCookie)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## reset_invite_message

> Vec<models::InviteMessage> reset_invite_message(user_id, message_type, slot)
Reset Invite Message

Resets a single Invite Message back to its original message, and then returns a list of all of them. Admin Credentials are required to update messages of other users!  Resetting a message respects the rate-limit, so it is not possible to reset within the 60 minutes countdown. Resetting it does however not set the rate-limit to 60 like when editing it. It is possible to edit it right after resetting it. Trying to edit a message before the cooldown timer expires results in a 429 \"Too Fast Error\".  Message type refers to a different collection of messages, used during different types of responses.  * `message` = Message during a normal invite * `response` = Message when replying to a message * `request` = Message when requesting an invite * `requestResponse` = Message when replying to a request for invite  The DELETE endpoint does not have/require any request body.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**user_id** | **String** | Must be a valid user ID. | [required] |
**message_type** | [**InviteMessageType**](.md) | The type of message to fetch, must be a valid InviteMessageType. | [required] |
**slot** | **i32** | The message slot to fetch of a given message type. | [required] |

### Return type

[**Vec<models::InviteMessage>**](InviteMessage.md)

### Authorization

[authCookie](../README.md#authCookie)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## respond_invite

> models::Notification respond_invite(notification_id, invite_response)
Respond Invite

Respond to an invite or invite request without accepting it. `:notificationId` is the ID of the requesting notification.  In case the notification being replied to is an invite, the `responseSlot` refers to a response message from the the `message` collection. In case the notification is an invite request, it will refer to one from the `requestResponse` collection instead.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**notification_id** | **String** | Must be a valid notification ID. | [required] |
**invite_response** | [**InviteResponse**](InviteResponse.md) | Slot number of the Response Message to use when responding to a user. | [required] |

### Return type

[**models::Notification**](Notification.md)

### Authorization

[authCookie](../README.md#authCookie)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## respond_invite_with_photo

> models::Notification respond_invite_with_photo(notification_id, image, data)
Respond Invite with photo

Respond with photo to an invite or invite request without accepting it. `:notificationId` is the ID of the requesting notification.  In case the notification being replied to is an invite, the `responseSlot` refers to a response message from the the `message` collection. In case the notification is an invite request, it will refer to one from the `requestResponse` collection instead.'

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**notification_id** | **String** | Must be a valid notification ID. | [required] |
**image** | **std::path::PathBuf** | The binary blob of the png file. | [required] |
**data** | [**models::InviteResponse**](InviteResponse.md) |  | [required] |

### Return type

[**models::Notification**](Notification.md)

### Authorization

[authCookie](../README.md#authCookie)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_invite_message

> Vec<models::InviteMessage> update_invite_message(user_id, message_type, slot, update_invite_message_request)
Update Invite Message

Updates a single Invite Message and then returns a list of all of them. Admin Credentials are required to update messages of other users!  Updating a message automatically sets the cooldown timer to 60 minutes. Trying to edit a message before the cooldown timer expires results in a 429 \"Too Fast Error\".  Message type refers to a different collection of messages, used during different types of responses.  * `message` = Message during a normal invite * `response` = Message when replying to a message * `request` = Message when requesting an invite * `requestResponse` = Message when replying to a request for invite

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**user_id** | **String** | Must be a valid user ID. | [required] |
**message_type** | [**InviteMessageType**](.md) | The type of message to fetch, must be a valid InviteMessageType. | [required] |
**slot** | **i32** | The message slot to fetch of a given message type. | [required] |
**update_invite_message_request** | Option<[**UpdateInviteMessageRequest**](UpdateInviteMessageRequest.md)> | Message of what to set the invite message to. |  |

### Return type

[**Vec<models::InviteMessage>**](InviteMessage.md)

### Authorization

[authCookie](../README.md#authCookie)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

