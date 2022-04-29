---
title: "Introduction to tokens"
date: 2021-04-12T07:44:00-04:00
author: "Lee Ford"
githubname: LeeFord
categories: ["Community post"]
images:
- images/01ed60e47ba84e66b302a6ef0e9035d2.png
tags: []
type: "regular"
---

## Introduction 

> This article is written to explain OAuth 2.0 and OpenID Connect bearer
> tokens (JWT) and concepts relating to Microsoft Azure AD and related
> technologies, but can most likely be applied elsewhere too.

Tokens are everywhere on the Internet. Even if you don't realise it,
you may have just used one on the way to read this article! You may ask
*"What is a token and what do I need it for?"* and my answer would be
*"Which token?"*. You see, there are different types of tokens all
with their use cases.

This article is here to break down the different types, how and when
they are used and what a token is comprised of. Hopefully this article
will help you better understand tokens and apply this to getting started
with other technologies such as Microsoft Graph.

## What is a token? 

A token is a list claims of *something*. A real world analogy could be a
receipt from a purchase of goods you made. Let's say you needed to
prove that you bought to goods to return something. The receipt would
most likely contain the date of purchase, the price you paid and most
importantly, the goods purchased. Essentially, you are making a claim of
ownership using the receipt. A token works in a similar way - it is a
way to claim *"I am me"* or *"I am allowed to do this"*.

### Token types 

As explained in the introduction, there are many different types of
tokens. This article will concentrate on the 3 most commonly used tokens
in Azure AD:

#### ID tokens 

ID tokens are used by a client to provide a user's identity. This is
referred to as **authentication**. One example is a user entering their
credentials in to a client and being given an ID token on sign-in
success. By then having an ID token, the client then can access
resources as the signed-in user without prompting the user.

> **Important Note:** ID tokens should only be used for identity
> purposes and NOT be used to grant access to additional resources. This
> will be covered next

#### Access tokens 

Access tokens are used by a client to obtain access to *additional*
resources e.g. a protected API such as Microsoft Graph. This is referred
to as **authorization**. With an access token, you can have a list of
permissions (scopes) granted to you against a resource. You can then use
these permissions in the access token to access protected resources that
you would not be able to access with an ID token.

If you are still confused of the difference between **authentication**
and **authorization**, [@LuiseFreese](https://twitter.com/LuiseFreese)
sums it up perfectly:
![01ed60e47ba84e66b302a6ef0e9035d2.png](images/01ed60e47ba84e66b302a6ef0e9035d2.png)

> The term "auth token" is widely used can become misleading as it
> could be interpreted as an **authentication** (ID) or
> **authorization** (access) token. It is important to distinguish the
> difference between the two and try to avoid using the term "auth
> token".

#### Refresh tokens 

Refresh tokens can be issued with ID and access tokens. Tokens have a
fixed lifetime and expire, but with a refresh token a client can obtain
a token without prompting the user for input. A basic example could be
you are signed in to a client and it is using an access token with
Microsoft Graph. On expiry of the access token, instead of interrupting
the user, a new access token is silently obtained before the old access
token expires using the refresh token from the original access token.

## What makes up a token? 

Let's look at a sample token:
 
``` {.lia-code-sample .language-applescript}
eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImtpZCI6IjFMVE16YWtpaGlSbGFfOHoyQkVKVlhlV01xbyJ9.eyJ2ZXIiOiIyLjAiLCJpc3MiOiJodHRwczovL2xvZ2luLm1pY3Jvc29mdG9ubGluZS5jb20vOTEyMjA0MGQtNmM2Ny00YzViLWIxMTItMzZhMzA0YjY2ZGFkL3YyLjAiLCJzdWIiOiJBQUFBQUFBQUFBQUFBQUFBQUFBQUFJa3pxRlZyU2FTYUZIeTc4MmJidGFRIiwiYXVkIjoiNmNiMDQwMTgtYTNmNS00NmE3LWI5OTUtOTQwYzc4ZjVhZWYzIiwiZXhwIjoxNTM2MzYxNDExLCJpYXQiOjE1MzYyNzQ3MTEsIm5iZiI6MTUzNjI3NDcxMSwibmFtZSI6IkFiZSBMaW5jb2xuIiwicHJlZmVycmVkX3VzZXJuYW1lIjoiQWJlTGlAbWljcm9zb2Z0LmNvbSIsIm9pZCI6IjAwMDAwMDAwLTAwMDAtMDAwMC02NmYzLTMzMzJlY2E3ZWE4MSIsInRpZCI6IjkxMjIwNDBkLTZjNjctNGM1Yi1iMTEyLTM2YTMwNGI2NmRhZCIsIm5vbmNlIjoiMTIzNTIzIiwiYWlvIjoiRGYyVVZYTDFpeCFsTUNXTVNPSkJjRmF0emNHZnZGR2hqS3Y4cTVnMHg3MzJkUjVNQjVCaXN2R1FPN1lXQnlqZDhpUURMcSFlR2JJRGFreXA1bW5PcmNkcUhlWVNubHRlcFFtUnA2QUlaOGpZIn0.1AFWW-Ck5nROwSlltm7GzZvDwUkqvhSQpm55TQsmVo9Y59cLhRXpvB8n-55HCr9Z6G_31_UbeUkoz612I2j_Sm9FFShSDDjoaLQr54CreGIJvjtmS3EkK9a7SJBbcpL1MpUtlfygow39tFjY7EVNW9plWUvRrTgVk7lYLprvfzw-CIqw3gHC-T7IK_m_xkr08INERBtaecwhTeN4chPC4W3jdmw_lIxzC48YoQ0dB1L9-ImX98Egypfrlbm0IBL5spFzL6JDZIRRJOu8vecJvj1mq-IUhGt0MacxX8jdxYLP-KUu2d9MbNKpCKJuZ7p8gwTL5B7NlUdh_dmSviPWrw
```
 
Makes sense, right? Of course not. Azure AD ID and access tokens are
also referred to as \"JWTs\" or JSON Web Tokens. This means that the
token is formatted as a JSON object and then \"base64Url\" encoded and
signed and with a bit of extra security (we'll cover this soon), the
end result is what we have above.

> For an introduction in to JSON, I highly recommend [Bob German's
> article](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/introduction-to-json/ba-p/2049369).

### Decoding a token

Taking the sample above and putting in in to [jwt.ms](https://jwt.ms),
it is possible to decode from "base64url" back to human-readable JSON.
![e738e6ef6d6f41ab9e811c7d4e8d5371.png](images/e738e6ef6d6f41ab9e811c7d4e8d5371.png)

You will now see a JWT is made up of 3 parts:

-   Header (red text)
-   Payload (blue text)
-   Signature (green text)

In the next two sections, we'll cover off each part.

### Payload 

A payload or body is the content of the token where the claims are
stored. Most tokens contain standard claims such as:

-   "iss" - Identity of the service that issued the token e.g.
    `https://login.microsoftonline.com/9122040d-6c67-4c5b-b112-36a304b66dad/v2.0`
-   "sub" - The subject of the token e.g. the user
-   "aud" - The audience of the token, who the token is intended for.
    This is usually the client and not the user
-   "exp" - Expiry date of token in seconds since the [Unix
    epoch](https://en.wikipedia.org/wiki/Unix_time)
-   "iat" - Time token was issued (Unix epoch seconds)
-   "nbf" - Time token is valid from (Unix epoch seconds)

In addition to standard claims, there are custom claims in Azure AD
tokens such as:

-   "name" - Name of the subject
-   "oid" - Azure AD object ID of the subject
-   "tid" - Azure AD tenant ID of the subject

> One great feature of [jwt.ms](http://jwt.ms) is that you can view
> detailed descriptions of standard and Azure AD claims.

### Validating a token 

You may be thinking: I just decoded a token on a webpage - how is that
secure? JWTs are typically \"signed\" (not encrypted) with an algorithm
and private key by the issuer of the token. This doesn't stop any of
the payload or header from being decoded as the aim of a token isn't to
hide information, but provide validity to it.
> Never store secret information in a payload of a token as it can be
> easily decoded.

It is up to the recipient e.g. your client to validate the token to
ensure it can be trusted.

There is a bit more nuance to the process than outlined here, but here
is the summary on how to validate a token. Within the header part of the
JWT, it contains the information on how the JWT was "signed" (what
algorithm and private/public key pair was used). With this information
it is possible for the client (if it has access to the public key) to
validate the signature part of the JWT.

In addition to the signature, validation should also be taken place on
the payload such as expiry time, audience and issuer.

### Token usage 

Now we are familiar with tokens. Let's cover how they could be used in
a couple of scenarios:

## OpenID Connect 

[OpenID Connect](https://openid.net/specs/openid-connect-core-1_0.html)
is a way to sign a user in to an application. It is used for
authentication only and not authorization. In this example, the end-user
(user-agent) requests access to an application. The application requires
authentication, so the end-user is redirected to authenticate at the
authorization server (I know, confusing). If successful, an ID token is
returned and then validated by the application. If it passes validation,
access is granted to the application.
![openidconnect.png](images/openidconnect.png)

## OAuth 2.0 auth code grant 

[Auth code grant](https://tools.ietf.org/html/rfc6749#section-4.1) flow
is where a user is asked to sign-in at the authorization server (Azure
AD). This time, however, instead of an ID token being returned, an
authorization code is returned. A second request is then made to the
authorization server with the authorization code, but this time an
access token is returned. With the access token, a protected API can
then be accessed.

![LeeFord_0-1641203766651.png](images/LeeFord_0-1641203766651.png)

## Wrap up

I hope you found this useful and understand more around what tokens are,
the different types of tokens and how they are used.
