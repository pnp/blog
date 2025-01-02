---
title: "CLI for Microsoft 365 2024 wrap up"
date: 2024-12-24T01:00:00.000Z
author: "Adam Wójcik"
githubname: Adam-it
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags: [CLI for Microsoft 365]
type: regular
---

[CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. Over this year, we have been working hard to bring you new features, improvements, commands, and bug fixes. Let's have a closer look at some of the significant changes and milestones achieved in 2024.

## Not one, not two but three major releases

You know what they say, "the more the merrier"! This year we released three major versions of CLI for Microsoft 365. Each release brought new features, and improvements, but was also made to adapt CLI for Microsoft 365 to some breaking changes in the Microsoft 365 ecosystem. We are committed to keeping the CLI up-to-date with the latest changes in Microsoft 365 and providing you with the best possible experience.

The first major release this year, v8, was in response to the deprecation of an API that CLI for Microsoft 365 used in Power Automate commands. To find out more go over the [upgrade guidance](https://pnp.github.io/cli-microsoft365/v8-upgrade-guidance/).

The second major release - v9 - was a reaction to an announcement that the PnP Management Shell multi-tenant app will be removed on September 9. Previously you were able to use this app to grant the needed permissions for your scripts or standard usage of CLI for Microsoft 365. Until now it was even used as the default login method. Although using the PnP Management Shell was very convenient it wasn’t the best approach that should be picked especially when running automated scripts on your tenant. In order to improve our customers' security posture the login method was updated to encourage the use of single-tenant apps and just the scopes and permissions that are needed. To find out more go over the [upgrade guidance](https://pnp.github.io/cli-microsoft365/v9-upgrade-guidance).

You may also check out the [Getting started with CLI for Microsoft 365 recording](https://www.youtube.com/watch?v=XFG8gVGvXpA).
{{< youtube XFG8gVGvXpA >}}

The third major release - v10 - was our regular planned major release in which we introduced breaking changes. This time we introduced 34 breaking changes that improved the overall experience of using CLI for Microsoft 365 and aligned it with latest naming in Microsoft 365 like renaming `AAD` to `Microsoft Entra ID`, and also we finally switched from Yammer to Viva Engage.
If you are interested in the full list of changes and improvements, you can check out the [upgrade guidance](https://pnp.github.io/cli-microsoft365/v10-upgrade-guidance).

## Support for using multiple accounts

Over the year we introduced many new features and improvements to the CLI for Microsoft 365 but the one that stand out the most this year is the possibility to sign in to multiple accounts/tenants and then just switch between them without the need to sign out and sign in again. This feature is especially useful for admins who manage multiple tenants, these might by dev, test, and production environments or different client tenants. This is a significant quality-of-life improvement that makes everything much easier and faster.

Check out [this recording](https://www.youtube.com/watch?v=vmtFRnNckGM) to see how it works.
{{< youtube vmtFRnNckGM >}}

To find out even more you may want to check the [m365 connection commands](https://pnp.github.io/cli-microsoft365/cmd/connection/connection-list)

## Added new commands to manage SharePoint Premium and SharePoint Embedded

This year we introduced many new commands but we are always looking for new areas to expand our CLI for Microsoft 365. All in all, the aim is to have a single CLI to manage all Microsoft 365 services. This year we introduced new commands to manage [SharePoint Premium](https://adoption.microsoft.com/en-us/sharepoint-premium/start/) and [SharePoint Embedded](https://learn.microsoft.com/en-us/sharepoint/dev/embedded/overview).

We are only getting started but the `m365 spe` commands will already allow you to manage basic operations on [container types](https://pnp.github.io/cli-microsoft365/cmd/spe/containertype/containertype-add) and [containers](https://pnp.github.io/cli-microsoft365/cmd/spe/container/container-get).

Regarding SharePoint Premium we mainly introduced `m365 spp` commands that allow you manage [document understanding models](https://pnp.github.io/cli-microsoft365/cmd/spp/model/model-get)

## Work done in numbers

This year was very busy for us. To give you a better idea of the extent of our work, here are some numbers:

- 322 PRs merged
- 340 issues closed
- 71 new commands added
- 3 major releases
- 10 minor releases
- 91 beta releases

This year we were thrilled to notice a significant interest increase in our product reaching even +81K downloads in June. If you are interested in more stats regarding CLI for Microsoft 365 we share them in our [repo Discussions](https://github.com/pnp/cli-microsoft365/discussions/categories/stats?discussions_q=is%3Aopen+category%3AStats+sort%3Adate_created)

All this would not have been possible without the help of our amazing community. We would like to thank all the contributors who helped us to make this year so successful. We are looking forward to working with you in the upcoming year.
Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Albert-Jan Schot](https://github.com/appieschot)
- [Arjun Menon](https://github.com/arjunumenon)
- [Herco van Brug](https://github.com/brugh)
- [János Dojcsák](https://github.com/dojcsakj)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [lovyjain](https://github.com/lovyjain)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Loitzl](https://github.com/mloitzl)
- [Martin Machacek](https://github.com/MartinM85)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Michał Kornet](https://github.com/mkm17)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nello D’Andrea](https://github.com/ferrarirosso)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Paolo Pialorsi](https://github.com/PaoloPia)
- [Reshmee Auckloo](https://github.com/reshmee011)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Shantha Kumar T](https://github.com/ktskumar)
- [Smita Nachan](https://github.com/SmitaNachan)
- [Vedant Lakshminarayanan](https://github.com/Vedu1996)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

## 100th release!

This year is special as we are celebrating the 100th release of CLI for Microsoft 365. Over the years, enhanced your experience, expanded our capabilities, and kept pace with the evolving Microsoft 365 ecosystem.

Reaching this milestone is a testament to our community's contributions, our team's dedication, and our users' ongoing support. Thank you for being part of this journey—we’re excited to continue building a brighter future together!

To celebrate this milestone, we’ve prepared a special place in which we started gathering all the positive feedback and testimonials from our users. We’re thrilled to unveil our new community [testimonials page](https://pnp.github.io/cli-microsoft365/testimonials)! This page highlights the experiences and stories shared by users from around the world, showcasing the impact of CLI for Microsoft 365 in real-life scenarios. From solving challenges to streamlining workflows, these testimonials reflect the value the CLI brings to professionals and organizations alike.

## Stay Connected!

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord), or [Bluesky](https://bsky.app/profile/climicrosoft365.bsky.social). Don't hesitate to connect with us, as your input plays a vital role in shaping the future of CLI for Microsoft 365.

## Resources

- [CLI for Microsoft 365 docs](https://pnp.github.io/cli-microsoft365/)
- [CLI for Microsoft 365 GitHub repo](https://github.com/pnp/cli-microsoft365)
- [CLI for Microsoft 365 npm package](https://www.npmjs.com/package/@pnp/cli-microsoft365?activeTab=readme)
- [Microsoft 365 & Power Platform Community](https://pnp.github.io/#home)
- [Join the Microsoft 365 & Power Platform Community Discord Server](https://aka.ms/cli-m365/discord)
- [Join the Microsoft 365 Developer Program]( https://developer.microsoft.com/en-us/microsoft-365/dev-program)
