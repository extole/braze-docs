---
nav_title: Extole
article_title: Extole
description: "This article outlines the partnership between Braze and Extole, a referral marketing company, that allows you to pull customer events and attributes from refer-a-friend and growth programs into Braze"
alias: /partners/extole/
page_type: partner
search_tag: Partner

---

# Extole

> [Extole][1], a SaaS company, is an industry leader in refer-a-friend marketing, helping create and optimize effective referral marketing programs to increase customer acquisition.

With the Braze and Extole integration, you can pull customer events and attributes from Extole refer-a-friend and growth programs into Braze, empowering you to create more personalized marketing campaigns that boost customer acquisition, engagement, and loyalty. You can also dynamically pull Extole content attributes, such as personalized share codes and links, into Braze communications.

## Prerequisites

| Requirement | Description |
| ----------- | ----------- |
| Extole account | An Extole account is required to take advantage of this partnership. |
| Braze REST API key | A Braze REST API key with `users.track` permissions. <br><br> This can be created within the **Braze Dashboard > Developer Console > REST API Key > Create New API Key**. |
| Braze test REST API key (optional) | A test API key that can be used for testing purposes if you’d like these requests sent to a separate staging Braze instance. |
| Braze instance | Your Braze instance can be obtained from your Braze onboarding manager or can be found on the [API overview]({{site.baseurl}}/api/basics/#endpoints) page. |
| User identity | The unique identifier for a user in Braze and Extole. This is generally the `external_id`. |
{: .reset-td-br-1 .reset-td-br-2}

## Use cases

The following use cases showcase a few ways you can leverage Extole’s integration with Braze. Work with your Extole implementation and customer success managers to develop an option that fits your company’s specific needs.

- Leverage custom events from your referral and engagement programs to trigger a Braze campaign or Canvas
- Power custom dashboards and reporting using data from your Extole-powered programs
- Automatically unsubscribe or subscribe users to your marketing list in Braze

## Integration

Complete the following steps to get your integration up and running quickly. Your Extole implementation and customer success managers will support you through this process.

### Step 1: Connect Your Extole and Braze Accounts 

1. Log in to your Extole account.
2. Select the Braze integration in the [Partners][2] center of your My Extole account.
3. Within the Braze integration, hit the Connect button to initiate the connection between Extole and Braze.
4. Provide your Braze REST API key and URL as well as the events that you want to send from Extole to Braze
5. Complete the connection by saving your settings. Once this is done, Extole events will be able to flow into your Braze account.

### Step 2: Define Event Names and Attributes
Any event that Extole tracks can be sent to Braze. Please work with your implementation or client success manager to identify the event names and user attributes you’d like Extole to send into Braze, or select from the default options in the tables below. Your Extole implementation or client success manager will then map and configure the event names in the Extole dashboard for you.

| Event Name | Attributes |
| ----------- | ----------- |
| Created Share Link | `external_id` (required) - The unique identifier for the customer, such as a user ID.<br>`email`<br>`phone_number`<br>`share_link`<br> `first_name`<br>`last_name`<br>`funnel` - The correct funnel type for the customer (e.g., `advocate` or `friend`)<br>`data` - Any additional data associated with the event |
| Shared | `external_id` (required) - The unique identifier for the customer, such as a user ID.<br>`email`<br>`phone_number`<br>`share_link`<br> `first_name`<br>`last_name`<br>`funnel` - The correct funnel type for the customer (e.g., `advocate` or `friend`)<br>`data` - Any additional data associated with the event |
| Referred Signed Up | `external_id` (required) - The unique identifier for the customer, such as a user ID.<br>`email`<br>`phone_number`<br>`share_link`<br> `first_name`<br>`last_name`<br>`funnel` - The correct funnel type for the customer (e.g., `advocate` or `friend`)<br>`data` - Any additional data associated with the event |
| Referred Converted | `external_id` (required) - The unique identifier for the customer, such as a user ID.<br>`email`<br>`phone_number`<br>`share_link`<br> `first_name`<br>`last_name`<br>`funnel` - The correct funnel type for the customer (e.g., `advocate` or `friend`)<br>`data` - Any additional data associated with the event|
| Subscribed | `external_id` (required) - The unique identifier for the customer, such as a user ID.<br>`email`<br>`phone_number`<br>`share_link`<br> `first_name`<br>`last_name`<br>`funnel` - The correct funnel type for the customer (e.g., `advocate` or `friend`)<br>`data` - Any additional data associated with the event |
| Unsubscribed | `external_id` (required) - The unique identifier for the customer, such as a user ID.<br>`email`<br>`phone_number`<br>`share_link`<br> `first_name`<br>`last_name`<br>`funnel` - The correct funnel type for the customer (e.g., `advocate` or `friend`)<br>`data` - Any additional data associated with the event |
| Earned Reward | `external_id` (required) - The unique identifier for the customer, such as a user ID.<br>`email`<br>`phone_number`<br>`share_link`<br> `first_name`<br>`last_name`<br>`funnel` - The correct funnel type for the customer (e.g., `advocate` or `friend`)<br>`data` - Any additional data associated with the event |
{: .reset-td-br-1 .reset-td-br-2}

## Customization 

### Configure a staging API key for testing

If you only provide one Braze REST API key to Extole, only production events will be sent to Braze. If you also want to send staging or testing events, create another Braze REST API key and configure an additional webhook integration in the Extole dashboard.

### Creating a new user alias

For certain use cases, such as a new email or SMS subscription where Extole does not have an external ID (user ID) for the user, Extole can check for the user's identifier using Braze's [export user by identifier endpoint][3]. If the user exists within Braze, Extole will add and update any profile attributes. If the request does not return a user profile, Extole will instead use the [user track endpoint][4] to create a user alias with the user's email address as the alias name.

## Using this integration

After connecting your Braze account to the Extole dashboard, events will automatically begin flowing from Extole to Braze. A live view of events being sent to Braze can be found in Extole’s outbound webhook center for troubleshooting. 

![][5]

Once the events and attributes you have configured are flowing into Braze, you can use the data to generate Braze audiences and campaign segmentation.

[1]: https://www.extole.com
[2]: https://my.extole.com/partners
[3]: {{site.baseurl}}/api/endpoints/export/user_data/post_users_identifier/
[4]: {{site.baseurl}}/api/endpoints/user_data/post_user_track/#request-body
[5]: {% image_buster /assets/img/extole/extole-webhook-live-events.png %}
