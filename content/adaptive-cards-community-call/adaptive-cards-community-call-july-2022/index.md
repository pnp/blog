---
title: "Adaptive Cards community call – July 2022"
summary: "Action.ToggleVisibility Deprecation (a non-breaking change for a control that needs to support accessibility requirements for all users), Adaptive Cards Handle Responses Connector now GA, React Native Adaptive Cards Renderer next month and 10-minute Q&A."
date: 2022-07-17T04:40:00-05:00
author: "J.P. Roca"
githubname: JeanRoca
categories: ["Adaptive Cards community call"]
images:
- images/recording-adaptive-cards-july-call.png
tags: ["Adaptive Cards", "Community Call", "Microsoft 365"]
type: "regular"
videos:
- https://www.youtube.com/watch?v=YtnW60YHwS8
- draft: false
---

## Call summary

In this month’s community call the following topics were presented - Action.ToggleVisibility Deprecation (a non-breaking change for a control that needs to support accessibility requirements for all users), GA release for Adaptive Cards Handle Responses Connector, teaser on the React Native Adaptive Cards Renderer capability used in Microsoft Viva Connections mobile app to be demoed next month, and a 10-minute Q&A covering a host of topics - release schedule, integration, challenges and demo requests. This call was hosted by [J.P. Roca](http://twitter.com/jpthepm) (Microsoft) \| @jpthepm. Recorded on July 14, 2022.

{{< youtube YtnW60YHwS8 >}}

## Agenda

* Action.ToggleVisibility Deprecation – [00:34](https://youtu.be/YtnW60YHwS8?t=34)
* Adaptive Cards Handle Responses Connector in GA – [04:18](https://youtu.be/YtnW60YHwS8?t=258)
* React Native Adaptive Cards Renderer – [05:35](https://youtu.be/YtnW60YHwS8?t=335)
* Q&A – [06:14](https://youtu.be/YtnW60YHwS8?t=374)

## Topic summaries

* **Action.ToggleVisibility Deprecation –** introduced in schema 1.2, Toggles (trigger action) the visibility of associated card elements. Why deprecating? The content changes on screen are not detectable by screen readers. Impact on card authors? None while developing a proper expander control that meets accessibility requirements. Let us know how you are using this capability today - issue 7678. This is a formality, not a breaking change.
* **Adaptive Cards Handle Responses Connector in GA –** the connector has been released into production, blog post coming soon, get an MSA account and try it at flow.microsoft.com. You can find learn more in the Microsoft Teams connector trigger documentation focused on responding to an Adaptive Card.
* **React Native Adaptive Cards Renderer** – developed and maintained by BigThinkCode and recently used in a Microsoft Viva Connections mobile app. Join the Adaptive Cards call next month to see a demo delivered by Vasanthakumar Sarpasayanam, CEO & Founder at BigThinkCode Technologies about using this capability.
* **Q & A –** topics include availability of WinUI 3 Renderer and v1.6 schema, adoption of latest GA schema version (v1.5) by Viva Connections (presently using V1.3 today) and by other groups in general - release schedule coordination. Incorporation of Microsoft Loop components, building Adaptive Cards presentations, and getting a Power Virtual Agent speaker on this call.

## Topic references

* **Action.ToggleVisibility Deprecation**
    * Tool – [Adaptive Cards Schema Explorer](https://adaptivecards.io/explorer/Action.ToggleVisibility.html)
    * Feedback - [[Feature Request] Action.ToggleVisibility -\> Expander Control \#7678](https://github.com/microsoft/AdaptiveCards/issues/7678) Adaptive Cards
* **Handle Responses Connector in GA**
    * Website – [Power Automate](https://powerautomate.microsoft.com/) \| flow.microsoft.com
    * Documentation Trigger - [When someone responds to an adaptive card](https://learn.microsoft.com/connectors/teams/#when-someone-responds-to-an-adaptive-card)
    * May call - [Handling multi-user responses for Adaptive Cards in Microsoft Teams](https://youtu.be/V0iTtOYcP6w) **-** [Josh Friedman](https://www.linkedin.com/in/josh-friedman-2a812254) (Microsoft)
    * MSA Account - [Getting Started with Group Managed Service Accounts](https://learn.microsoft.com/windows-server/security/group-managed-service-accounts/getting-started-with-group-managed-service-accounts)
* **React Native Adaptive Cards Renderer**
    * Tool npm - [adaptivecards-reactnative](https://www.npmjs.com/package/adaptivecards-reactnative)
    * Repo - [BigThinkcode/AdaptiveCards](https://github.com/Bigthinkcode/AdaptiveCards/tree/main)
* **Q&A**
    * Preview – [Adaptive Cards Designer v1.6 (windows.net)](https://adaptivecardsci.z5.web.core.windows.net/designer)
    * Article - [Announcing Adaptive Cards 1.5 GA](https://adaptivecards.io/blog/2021/Announcing-1.5/)
    * Microsoft Build Presentation: [Building great apps with the open platform of Windows (microsoft.com)](https://mybuild.microsoft.com/en-US/sessions/3a0b225f-279e-4973-8106-20ce58f16ed1?source=/home) (Windows 11 Widgets - a.k.a., Adaptive Cards at 40:56)
    * Feedback Portal – [Microsoft Viva Connections](https://feedbackportal.microsoft.com/feedback/forum/5092ec4b-1d1c-ec11-b6e7-0022481f8472)

## Actions

* Opt into PnP Recognition Program \| <https://aka.ms/m365pnp-recognition>
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Request a Demo spot on the call – <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call – <http://aka.ms/spdev-sig-call>
* Join us on August 11th at 09:00 am PT, Download the recurrent invite for this call – <https://aka.ms/adaptivecardscommunitycall>

## Resources in general

* Let us know the features you need <https://aka.ms/ACRoadmap>
* Schema Explorer - <https://adaptivecards.io/explorer/Action.Execute.html>
* Designer - <https://adaptivecards.io/designer/>
* Get started with Templating - <https://aka.ms/ACTemplating>
* Browse the Adaptive Cards Code & Contribution Guidelines -
    <https://aka.ms/ACRepo>
* Find tools, sample cards and more -
    [https://www.madewithcards.io](https://www.madewithcards.io/)
* Issues creating AC interfaces
    <https://github.com/microsoft/AdaptiveCards/discussions>

## Stay connected

* Twitter -
    [https://twitter.com/microsoft365dev](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbkdvcDJHcGdzM2VIUkwzU3lOYkJaVFEzM0Q2QXxBQ3Jtc0ttM1NyaTQ2RjFSOFh3a0l4c1pralBRQVI1bDNSQ2RaVm9OdzJrRkdtV1Z1SW5VdmdwamNNLTBEaFdaSmZMc0lQNzdRZ2dDYV9WZVF1ZVIwc2dPQTZBRUZ3b3hoWUVJdDJoQWZUcWdCR2JKdmwtUU43RQ&q=https%3A%2F%2Ftwitter.com%2Fmicrosoft365dev)​​
* Recurrent Invite - <https://aka.ms/adaptivecardscommunitycall>
* Next call – August 11th at 09:00am PT

## Learn more

* Microsoft 365 Unified Sample gallery - <https://aka.ms/m365/samples>
* Microsoft 365 Platform Community in YouTube - <https://aka.ms/m365/videos>
* Microsoft 365 Platform Community - <https://aka.ms/m365pnp/community>
