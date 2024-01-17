---
# this is the title
title: "Deep dive: Managed & Unmanaged solutions"
# this is the publishing date of your article, usually this should match "now"
date: 2024-01-10T08:40:00-04:00
# This is your name
author: "Søren Lauszus Weber"
# This is your GitHub name
githubname: powerappsviking
# Don't change
categories: ["Community post"]
# Link to the thumbnail image for the post
images: 
- images/deepdive.png
# don't change
tags: []
# don't change
type: "regular"
---

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">What are solutions?</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>If you are reading this post in hoping to get an answer to the question "What is a solution?" Then I suggest you start with another blog post I made. I covered the basics working with solutions in my <em>Getting Started with Model-Driven Apps </em>series. You can <a href="https://powerappsviking.com/2023/06/12/working-with-solutions/">read that post here</a>.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The purpose of this post is to provide some guidance for citizen developers and Power Platform Developers when things have become a little more advanced. You might be dealing with things such as multiple solution layers, and you need to be able to dig a little deeper. Understanding the overall concept of solution layers is generally important in order to avoid costly mistakes and to ensure that your application actually works the way you intend.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>In this post I will cover the following:<br><br>1. Managed and unmanaged layers, in depth<br>2. Managed solution layering<br>3. Avoiding unmanaged layers<br>4. Issues with managed solutions</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 class="wp-block-heading">Managed and unmanaged layers, in depth</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>First off, we need to start by revisiting my graphic from the previous post, showing the basics of how solution layers work on a Power Platform Environment:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":160,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://powerappsviking.files.wordpress.com/2023/08/2023-08-12_19-51-54.png?w=1024" alt="" class="wp-image-160" /></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 class="wp-block-heading">Avoiding unmanaged layers</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>It should always be the case that you actively avoid making unmanaged layers on your test and production environments. Previously, developers working with solutions in Dynamics would use unmanaged layers throughout the different environments. This would be for a variety of reasons, but most of them involve either overcoming limitations that have now been solved, or are, in my opinion, largely irrelevant for 99% of citizen developers. Therefore, avoiding unmanaged layers should be the way of working going forward.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 class="wp-block-heading">Managed solution layering</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>When importing your own managed solution, it will always be layered in the order that the solution was first added. Let's set up a scenario for this case. <br>We create two solutions, Solution A and Solution B. Both solutions contain a reference to the same column in the systemuser table. In Solution A the "Full Name" column has been renamed to "Legal name". In Solution B the "Full Name" Column has been renamed to "Actual Name".</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Now, use the above graphics as a reference, we do the following thought experiment:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Week 1</strong>: You import the first version (version <strong>1.0.0.1</strong>) of Solution A (as a managed solution) to your test environment. Changing the column name to "Legal Name"<br><strong>Week 2:</strong> You add the first version (version <strong>1.0.0.1</strong>) of Solution B (as a managed solution). Changing the Column name to "Actual Name"<br><strong>Week 3: </strong> You add an update (version <strong>1.0.0.2</strong>) to Solution A to the environment. What happens in this update? Is the name changed back to "Legal name"?</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The answer is that nothing happens in week 3. Solution B is the current top layer and is king and therefore the column is still called "Actual name". <strong>Any changes made to your lower solution layers have no effect if there is also a change to the objects on any layer above it. </strong>This is really important to understand when looking at the graphics above.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 class="wp-block-heading">Avoiding unmanaged layers</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Citizen developers should always avoid using unmanaged layers in Power Platform deployment because it can lead to governance and security risks.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Unmanaged layers can be created by developers who do not have the necessary permissions to modify the solution, which can lead to unauthorized changes being made to the solution. This can result in a lack of control over the solution, which can lead to issues such as data loss, security breaches, and other problems.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>To minimize these risks, citizen developers should use managed solutions instead of unmanaged solutions. Managed solutions provide better control over the solution, which can help to prevent unauthorized changes from being made to the solution. Additionally, using managed solutions is recommended best practice for deploying solutions to different environments, which can help to ensure that the solution is consistent across all environments. This way, citizen developers can trust that their solutions are function the same way across environments and that they meet the needs of their organization.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 class="wp-block-heading">Issues with managed solutions</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Lets go through a couple of different scenarios where managed solutions and solution layering can cause unintended issues, and how to mitigate them. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Connection references</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>When working with Power Automate Flows or anything else that could require a connection reference, you will experience that these need to be changed from time to time. This process will always be an unmanaged change on the environment you are working on, no matter what. This is not an issue in itself, however it can cause problems with keeping track of which objects are actually managed or unmanaged. Which is why I would recommend having an unmanaged solution to keep track of any unmanaged changes happening on your environment. This provides transparency over which objects have been changed in the unmanaged layer on your environment.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Choice fields</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Simply put, if you use a choice field from any managed solution on your dev environment. <strong><u>You will not be able to remove any existing values without changing the original solution containing those choice values</u></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's look at an example:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>You already imported Solution A and Solution B from before. In Solution B there is a choice field which looks like this:<br></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":179,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://powerappsviking.files.wordpress.com/2023/08/image.jpeg?w=708" alt="" class="wp-image-179" /></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>On top of this you create your own customization solution (Unmanaged Solution C in the graphics)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Now, let's say we change it by removing one of the choices. Let's remove the one with three stars, and add our own choice which we now call "option 4".</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":180,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://powerappsviking.files.wordpress.com/2023/08/image-1.jpeg?w=561" alt="" class="wp-image-180" /></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>So we save this, publish all and export it as a managed solution and it works. Easy-peasy right?</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><u>Wrong.&nbsp;</u></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>First, we need to establish that the target environment needs to have all relevant solutions installed as there are solution dependencies. So the target environment will also contain solution A and B as managed solutions. Now if you import <strong>Solution C</strong> as a managed solution to your test or dev environment. (containing Solution B as a managed solution) then as a result of <strong><u>solution layering</u></strong> you will have the following choice field:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":181,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://powerappsviking.files.wordpress.com/2023/08/image-2.jpeg?w=563" alt="" class="wp-image-181" /></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>There are now 5 fields, the 4 original fields, including your own.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>So what do to?</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>If you have a choice field with ANY RISK at all of needing to remove choices in the future, create your own custom choice fields that you can change completely unmanaged on your own dev. I can't stress this enough.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>This is the same issue that we see with security roles. There are just some things which managed solutions, through layering, will still force through, no matter what you do in your own solutions afterwards.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The same challenges apply to other solution objects such as: <br>Calculated Fields, and Security roles.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>For Calculated fields</strong>, once a solution is imported with a calculated field, it is not possible to change the calculation through updates in the managed solution afterwards, this will have to happen in the unmanaged layer (If this has changed recently please let me know and I will correct this)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>For <strong>Security Roles</strong>, even changes in the deeper solution layers will affect how the security role will work. Therefore, if you want to ensure that your top-layer solution provides the correct security role setup I recommend copying the security role and assigning the new role to users instead of the old one.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>There is much more that could be said about solution layering and solution types, and I will make a separate post about patches at some point. If anyone has any information about changes to these topics please let me know.</p>
<!-- /wp:paragraph -->
