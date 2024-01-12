---
title: "Office Add-ins community call -- October 13, 2021"
date: 2021-10-22T01:56:00-04:00
author: "David Chesnut"
githubname: davidchesnut

categories: ["Office add-in developer community call"]
images:
- images/OctAdd-insRecordingThumb.png
tags: []
type: "regular"
---

## ![OctAdd-insRecordingThumb.png](images/OctAdd-insRecordingThumb.png)


## Call summary



This month's community call features presentations - **Word API
updates** (extensibility API updates - Word Online Only APIs, Bookmarks
APIs, Shared Runtime Support, and Upcoming APIs), **Outlook on Mac API
updates** (new extensibility updates -- Mailbox 1.9 GA, Upcoming --
Mailbox 1.10 Signature APIs, and Upcoming - Event-based Outlook
add-ins), and **Demo: Hello World code sample** (deliver the iconic
greeting from Word, Excel, Outlook, and PowerPoint add-ins). This
month's community spotlight recognizes MVP Maarten van Stam and Eric
Legault for their continued contributions. Thank so much! Register for
the [PnP Recognition
Program](https://pnp.github.io/recognitionprogram/). Q&A live and in
chat throughout call. The call was hosted by [David
Chesnut](https://twitter.com/davidchesnut) (Microsoft) | @davidchesnut


## Microsoft Presenters

-   Abid Rahman - Program Manager
-   Ashima Mathur - Program Manager
-   David Chesnut - Senior Dev Writer


## Agenda

-   Word API updates - Abid Rahman, Program Manager (Microsoft) -- 
    [1:07](https://youtu.be/X_hNLKnx_GE?t=67)
-   Outlook on Mac API updates Ashima Mathur, Program Manager
    (Microsoft) - [10:11](https://youtu.be/X_hNLKnx_GE?t=611)
-   Demo: Hello world code sample - David Chesnut, Senior Dev Writer
    (Microsoft) - [19:19](https://youtu.be/X_hNLKnx_GE?t=1159)
-   Community spotlight - Eric Legault, Maarten van Stam --
    [29:31](https://youtu.be/X_hNLKnx_GE?t=1773)
-   Q&A -- [30:27](https://youtu.be/X_hNLKnx_GE?t=1828)

## Actions

-   Please reach out to us to provide input on upcoming Word APIs such
    as the Bookmark APIs: <https://aka.ms/wordextensibilitysurvey> 
-   Give us feedback on the Hello World sample in the PR:
    <https://github.com/OfficeDev/PnP-OfficeAddins/pull/213>
-   Earn contributor badges - sign up for the PnP Recognition
    program: <https://pnp.github.io/recognitionprogram/> 



## Q&A (Question & Answers)


**Can you please demo, or provide sample code for events in Office Word
add-ins?**
Go to <https://github.com/OfficeDev/> and search for "Word" to find
several code samples that may have the information you need in the
archive. For example,
<https://github.com/OfficeDev/Word-Add-in-JavaScript-AddPopulateBindings> shows
how to create and bind to content controls. If there are specific
scenarios you want to see in a demo or sample, please create an issue at
<https://github.com/OfficeDev/PnP-OfficeAddins>. This is where we
publish new samples and it would be great to learn more about what
you'd like to see in the sample!
**Are there any plans to allow activating Outlook add-ins to include
examining email headers? I've raised the issue on Developer Platform
already but wanted to know if it had come up internally.**
We don't have plans to enable examining email headers at this time. It
looks like a feature request was created for this idea at
[https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/activate-contextual-add-ins-using-regex-based-on-headers-in/idi-p/2781149](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/activate-contextual-add-ins-using-regex-based-on-headers-in/idi-p/2781149).
If developers can upvote or tell us more about this scenario that will
help in our planning down the road.

\
**Can we please have the ability for admins to pin Office Add-ins to the
toolbar in the new Outlook experience?**
We don't have plans to support pinning Office Add-ins at this time. If
you could create a feature request at
<https://aka.ms/m365dev-suggestions> and tell us more about this
scenario that will help in our planning.

\
**Following up on questions from the November 2020 Call: Could we have a
method for Word, Excel, and PowerPoint to save a file? Word and Excel
have context.document.save() and context.workbook.save() but they lack
options for similar behavior (eg. skip save dialogue). PowerPoint does
not have context.presentation.save() yet. Could we have an equivalent
method for all 3 (Word, Excel, PowerPoint) with similar
options/behaviors? This is really needed for developers. Similar to the
previous question, could we have an equivalent method for all 3 (Word,
Excel, PowerPoint) to close files with similar options/behaviors? **


Back in November 2020, we had PowerPoint save and close methods on the
roadmap. Unfortunately, we had to shift resources and reprioritize, and
these are no longer on the roadmap. So we apologize about the confusion
on the planning for these methods. We can't guarantee the roadmap
won't change over time but we try to stick to the roadmap as much as we
can.

The best way to keep these methods on our planning radar is to request
them at <https://aka.ms/m365dev-suggestions>. It looks like there is
already a feature request for these methods at
[https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/office-js-save-and-close-methods-for-word-excel-and-powerpoint/idi-p/2800214](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/office-js-save-and-close-methods-for-word-excel-and-powerpoint/idi-p/2800214).
So if you or anyone is interested in these methods, please upvote and
let us know more about your scenarios.

\
**We'd like to hear more about the roadmap of Office.js development for
PowerPoint automation. We're interested in the following
functionalities: Creating new slides based on different master slide
templates, mass updates of footers, and mass updates of text string that
follow certain logic (similar to Word placeholders).**
To insert slides from different slide masters, use the
[insertSlidesFromBase64()](https://learn.microsoft.com/javascript/api/powerpoint/powerpoint.presentation?view=powerpoint-js-preview#insertSlidesFromBase64_base64File__options_)
API which supports [slide master
options](https://learn.microsoft.com/javascript/api/powerpoint/powerpoint.addslideoptions?view=powerpoint-js-preview#slideMasterId)
(currently in beta).

We don't have footer manipulation APIs, or find and replace logic
similar to PowerPoint. Please tell us more about these scenarios by
creating a feature request at <https://aka.ms/m365dev-suggestions>.

\
**Are the new Word APIs available cross-platform?**
In general, new Word APIs are available on Word on the web first. Later
they are available for other platforms. The Comments and Footnotes APIs
are only available on Word on the web at this time. We do plan to make
them available cross-platform in the future.

**Is it possible to download the full beta API library locally instead
of using the CDN endpoint at
<https://appsforoffice.microsoft.com/lib/beta/hosted/office.js>? The
non-beta library can be downloaded using NuGet, but I can't seem to
find the beta.**
We don't provide a preview (beta) version of the office.js library to
be used in offline scenarios. For more information on offline target
scenarios, see <https://www.npmjs.com/package/@microsoft/office-js>.

Trying out preview APIs requires that you reference the beta endpoint.
For more information on how to reference release and preview versions of
the APIs, see [Referencing the Office JavaScript API
library](https://learn.microsoft.com/office/dev/add-ins/develop/referencing-the-javascript-api-for-office-library-from-its-cdn).


**Will the BeforeSave and BeforeClose events be coming for Excel? Will
the ability to turn AutoSave off and on be coming for Excel?**
The BeforeClose event is on our backlog, but we don't yet have an ETA
for when it will be ready.
The BeforeSave event is not on our roadmap. The ability to turn AutoSave
off and on is also not on our roadmap. Currently, we're focusing on
building out APIs that apply to all platforms (web, Windows, Mac,
mobile.) These features only apply to desktop platforms because web is
AutoSave by default. But we'd like to understand more about your
scenario. Please submit a feature request for this at
<https://aka.ms/m365dev-suggestions>.


## Resources

### Word Extensibility (API) Updates

-   Documentation -- [Word.Comment
    class](https://learn.microsoft.com/javascript/api/word/word.comment?branch=master&view=word-js-preview)
-   Documentation -- [Word.NoteItem
    class](https://learn.microsoft.com/javascript/api/word/word.noteitem?branch=master&view=word-js-preview)
-   GitHub Feedback -- [office-js
    issues](https://github.com/OfficeDev/office-js/issues)
-   Article -- [Use the shared JavaScript runtime to improve the UI
    experience of your Office
    Add-in](https://devblogs.microsoft.com/microsoft365dev/use-the-shared-javascript-runtime-to-improve-the-ui-experience-of-your-office-add-in/)
-   Documentation -- [Configure your Office Add-in to use a shared
    JavaScript
    runtime](https://learn.microsoft.com/office/dev/add-ins/develop/configure-your-add-in-to-use-a-shared-runtime)
-   Survey -- [Word Extensibility
    Survey](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRzgiSwR_LJpPryfdZMes2zpUNVVIT0hKMlFSQjA1TEtUWlZYNEo2TzFSQS4u%C2%A0)

### Outlook extensibility on Mac API updates

-   Article -- [The new Outlook for
    Mac](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439)
-   Documentation -- [Outlook add-in API requirement set
    1.9](https://learn.microsoft.com/office/dev/add-ins/reference/objectmodel/requirement-set-1.9/outlook-requirement-set-1.9)
-   Documentation -- [Outlook add-in API requirement set
    1.10](https://learn.microsoft.com/office/dev/add-ins/reference/objectmodel/requirement-set-1.10/outlook-requirement-set-1.10)

### Demo: Hello World code sample

-   Repo -- [Hello world
    samples](https://github.com/OfficeDev/PnP-OfficeAddins/pull/213)
-   Article -- [Office Add-ins platform
    overview](https://learn.microsoft.com/office/dev/add-ins/overview/office-add-ins)

### Office Add-ins community call

-   [Upcoming agenda and previous call
    resources](https://aka.ms/officeaddinsagenda)
-   [Recurring, monthly community call calendar
    invite](https://aka.ms/officeaddinscommunitycall)
-   [Community call topic requests and
    questions](https://aka.ms/officeaddinsform)
-   Community call recordings on the [YouTube Microsoft 365 community
    channel](https://www.youtube.com/channel/UC_mKdhw-V6CeCM7gTo_Iy7w)

### Office Add-ins feedback

-   Technical questions -- Microsoft Q&A
    ([office-js-dev](https://learn.microsoft.com/answers/topics/office-js-dev.html)),
    ([office-addins-dev](https://learn.microsoft.com/answers/topics/office-addins-dev.html))
-   Issues -- [GitHub](https://github.com/OfficeDev/office-js/issues)
-   Recommendations and suggestions -- [Microsoft 365 Developer Platform
    ideas](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform)
 
