---
title: "Get Permission Report for SharePoint Online or OneDrive File using CLI for Microsoft 365"
date: 2021-09-29T03:29:00-04:00
author: "Arjun Menon"
githubname: arjunumenon
categories: []
images:
- images/SP Permission Report - CLI.png
tags: ["CLI for Microsoft 365", "SharePoint"]
type: "regular"
---

There were couple of folks who were asking me whether there are some
ways where we can generate a Permission Report for a particular file in
SharePoint Online either using some scripts or from the User Interface.
 

Well the first thing which comes to your mind is to go look in
the **Manage Access** approach from the User Interface of File sharing
settings. It does gives you a high-level information about the shared
files. But this may get difficult if you want to know how many of those
users were external. Well, using User Interface you will not get that
information and there you have reached a difficult situation. You will
also find it difficult to know about shared details if the file is
shared via Direct Link.
 

There comes [CLI for Microsoft 365](https://aka.ms/cli-m365) for your
rescue. With CLI for Microsoft 365, there is a command via which you can
get the complete sharing report which you will fetch the result
something like below.
 
![SP Permission Report - CLI.png](images/SP Permission Report - CLI.png)

 
When you execute the command


```bash
m365 spo file sharinginfo get --webUrl https://contoso.sharepoint.com/sites/M365CLI --url "/sites/M365CLI/Shared Documents/MySharingCentral.docx"
```


How good is that?! You can get the complete sharing details which even
has external sharing information in a single command.


## Information Not Enough 

If you are not happy with the currently available information available
as text output, you can even get the JSON output from CLI for Microsoft
365 commands via which you can manipulate and process complete business
scenarios. For getting the complete Sharing Information result in a JSON
object, you can use the below command
 

```bash
m365 spo file sharinginfo get --webUrl https://contoso.sharepoint.com/sites/M365CLI --url "/sites/M365CLI/Shared Documents/MySharingCentral.docx" --output JSON
```

You can get more details about this command from [this
link](https://pnp.github.io/cli-microsoft365/cmd/spo/file/file-sharinginfo-get/).

