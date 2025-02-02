---

copyright:
  years: 2020, 2022
lastupdated: "2022-02-07"

keywords: event-notifications, event notifications, about event notifications, destinations, push

subcollection: event-notifications

content-type: tutorial
account-plan: lite
completion-time: 10m

---

{:codeblock: .codeblock}
{:external: target="_blank" .external}
{:important: .important}
{:note: .note}
{:pre: .pre}
{:screen: .screen}
{:shortdesc: .shortdesc}
{:tip: .tip}



# {{site.data.keyword.Bluemix_notm}} push notification service
{: #en-destinations-push}
{: toc-content-type="tutorial"}
{: toc-completion-time="10m"}

{{site.data.keyword.en_short}} provides a push notification service for sending transactional and informational event notifications to mobile devices. 
{: shortdesc}

## Adding a push service destination
{: #en-destinations-push-add}


Add an {{site.data.keyword.Bluemix_notm}} push notification destination to your instance of {{site.data.keyword.en_short}} by clicking the `Add` button in the `Destinations` view of the {{site.data.keyword.en_short}} dashboard. After a new push destination is created, you see an entry `{{site.data.keyword.Bluemix_notm}} push service` in the `Destination` list. You must configure your push destination by adding credentials for Apple Push Notification Service (APNS) or Firebase Cloud Messaging (FCM). See [Send a push notification using Event Notifications](/docs/event-notifications?topic=event-notifications-en-send-push) for more details.

Each application and platform requires a separate push destination.

## Using an {{site.data.keyword.Bluemix_notm}} push service destination
{: #en-destinations-push-use}

To use the push service destination, add it to a subscription. The subscription also needs a topic to filter events of interest from your sources. When an event lands in the topic, {{site.data.keyword.en_short}} immediately routes the event notification to your registered devices. 

The push service works along with an app on your users' mobile devices. You must instrument the app with the {{site.data.keyword.en_short}} push SDK. The app must ensure that users consent to notifications, and then the SDK helps to register their mobile devices. See the [Create an Event Notifications destination](/docs/event-notifications?topic=event-notifications-en-create-en-destination) for details.

## Push charges
{: #en-destinations-push-charge}

The {{site.data.keyword.Bluemix_notm}} push service has two components to pricing: a destination instance fee and a consumption price.

The destination instance fee is a fixed amount charged monthly. Every push destination added to your {{site.data.keyword.en_short}} instance incurs the fee.

The consumption price is based on outbound digital messages. Every push notification that is sent by the {{site.data.keyword.Bluemix_notm}} push service counts as one outbound digital message and is charged. For example, you send messages to two platforms (iOS and Android) and you create a subscription that has 100 phone numbers. The subscription topic received 1000 events during the month:

Destination instances: 2 

Consumption:

Total Outbound Digital Messages = (number of phone numbers) x (topic events)

In the example, the total outbound digital messages is:

100 x 1000 = 100000 outbound digital messages

You are charged for messages that are successfully sent by the {{site.data.keyword.Bluemix_notm}} push service to the push provider regardless of whether the message was successfully delivered to the local device. So vet your device list carefully to prevent unnecessary charges.

You can monitor your push usage by setting up a monitoring dashboard through the `Actions` menu in the {{site.data.keyword.en_short}} dashboard. See [Monitor Event Notifications service metrics with IBM Cloud Monitoring](/docs/event-notifications?topic=event-notifications-en-monitoring) for details.
