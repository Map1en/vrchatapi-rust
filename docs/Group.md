# Group

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**age_verification_slots_available** | Option<**bool**> |  | [optional]
**age_verification_beta_code** | Option<**String**> |  | [optional]
**age_verification_beta_slots** | Option<**f64**> |  | [optional]
**badges** | Option<**Vec<String>**> |  | [optional]
**id** | Option<**String**> |  | [optional]
**name** | Option<**String**> |  | [optional]
**short_code** | Option<**String**> |  | [optional]
**discriminator** | Option<**String**> |  | [optional]
**description** | Option<**String**> |  | [optional]
**icon_url** | Option<**String**> |  | [optional]
**banner_url** | Option<**String**> |  | [optional]
**privacy** | Option<[**models::GroupPrivacy**](GroupPrivacy.md)> |  | [optional]
**owner_id** | Option<**String**> | A users unique ID, usually in the form of `usr_c1644b5b-3ca4-45b4-97c6-a2a0de70d469`. Legacy players can have old IDs in the form of `8JoV9XEdpo`. The ID can never be changed. | [optional]
**rules** | Option<**String**> |  | [optional]
**links** | Option<**Vec<String>**> |  | [optional]
**languages** | Option<**Vec<String>**> |  | [optional]
**icon_id** | Option<**String**> |  | [optional]
**banner_id** | Option<**String**> |  | [optional]
**member_count** | Option<**i32**> |  | [optional]
**member_count_synced_at** | Option<**String**> |  | [optional]
**is_verified** | Option<**bool**> |  | [optional][default to false]
**join_state** | Option<[**models::GroupJoinState**](GroupJoinState.md)> |  | [optional]
**tags** | Option<**Vec<String>**> |  | [optional]
**transfer_target_id** | Option<**String**> | A users unique ID, usually in the form of `usr_c1644b5b-3ca4-45b4-97c6-a2a0de70d469`. Legacy players can have old IDs in the form of `8JoV9XEdpo`. The ID can never be changed. | [optional]
**galleries** | Option<[**Vec<models::GroupGallery>**](GroupGallery.md)> |  | [optional]
**created_at** | Option<**String**> |  | [optional]
**updated_at** | Option<**String**> |  | [optional]
**last_post_created_at** | Option<**String**> |  | [optional]
**online_member_count** | Option<**i32**> |  | [optional]
**membership_status** | Option<[**models::GroupMemberStatus**](GroupMemberStatus.md)> |  | [optional]
**my_member** | Option<[**models::GroupMyMember**](GroupMyMember.md)> |  | [optional]
**roles** | Option<[**Vec<models::GroupRole>**](GroupRole.md)> | Only returned if ?includeRoles=true is specified. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


