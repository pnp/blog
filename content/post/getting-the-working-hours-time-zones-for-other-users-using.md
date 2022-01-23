# Getting the working hours/time zones for other users using Microsoft Graph API

In a recent discussion on Twitter, we were exploring approaches on how
to get the working hours and time zone for another user (not the current
logged user) in Microsoft Graph.
This information could be useful to warn users about the availability of
our colleagues (especially when there are people in the team working in
different countries) or use this information and delay actions until the
person is available (for example, do not send emails out-of-hours).
When searching for this option on the web, most of the references will
mention
the **[mailBoxSettings](https://docs.microsoft.com/en-us/graph/api/user-get-mailboxsettings?view=graph-rest-1.0&tabs)**
object available through the user properties in Graph:

**/users/{id\|userPrincipalName}/mailboxSettings**

This gives us a response in the following format, and those details are
available (sample test using Graph Explorer):

![01_Mysettings.PNG](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/317868i0DB9879A0906C3B5/image-size/large?v=v2&px=999 "01_Mysettings.PNG")

However, using delegated permissions, the current user can only access
their own settings.
If I try to access the same information for another user \'Carlos\'
under the tenant, the access will be denied, even with all related
permissions granted to the current app:

![02_OtherUsers.PNG](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/317869i528179B823E6FC8B/image-size/large?v=v2&px=999 "02_OtherUsers.PNG")

Most of the operations that access Exchange Online with delegated
permission will work only for the current user\'s data.

## The alternative

By using the
**[calendar/getSchedule](https://docs.microsoft.com/en-us/graph/api/calendar-getschedule?view=graph-rest-1.0&tabs=http)**
action it is possible to get not only the user\'s free/busy schedule but
also the working hours and time zone for any user in the tenant, using
delegated permissions in Microsoft Graph.
To use this action we need to do a post request to one of the following
graph endpoints:

**/me/calendar/getSchedule\
/users/{yourCurrentUserEmail}/calendar/getSchedule**
And use the request body in the following format (use an array of a
single user email address if you want to retrieve only one user):

![03_CarlosPostBody.PNG](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/317870i80D7D671043C23A2/image-size/large?v=v2&px=999 "03_CarlosPostBody.PNG")

Simply check for a user's schedule and the working hours will be
returned together with the schedule. You can use any valid dates/time
zones in the request JSON body for this purpose, even though there can
be no items in the schedule, the time zone and working hours will be
returned.
In this example, we used a date range for 20 years ago on purpose, so
the query wouldn\'t bring any schedule items info.
In the response to the query mentioned above, no schedule item is
returned but the working hours property is still correctly provided:

![04_CarlosResponseBody.PNG](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/317871i540A3DB7E51425A4/image-size/large?v=v2&px=999 "04_CarlosResponseBody.PNG")

## Conclusion

By using this approach we are able to obtain the working hours and time
zone for another Microsoft 365 user in the same tenant (given that the
user has Exchange Online active).
