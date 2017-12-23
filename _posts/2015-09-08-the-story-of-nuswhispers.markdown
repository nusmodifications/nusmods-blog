---
layout: post
title:  "The Story of NUSWhispers"
date:   2015-09-08 10:01:26
author: Yangshun Tay
author_thumbnail: 558978353
excerpt: >
  The confessions wave took the whole Singapore by storm in 2012, and confessions pages were created for organizations on Facebook, so that people could share their darkest secrets and gossips in an anonymous fashion. In 2013, NUS Confessions was launched. It was an instant hit among students, reaching 30,000 likes over the span of a year. However, since the founders of NUS Confessions have graduated, the platform was left unmaintained. We saw the opportunity to build a better version of a confessions site for NUS, and build a platform that is tailored for anonymous sharing of opinions and stories. Thus, NUSWhispers was born.
---

The confessions wave took the whole Singapore by storm in 2012, and confessions pages were created for organizations on Facebook, so that people could share their darkest secrets and gossips in an anonymous fashion. In 2013, NUS Confessions was launched. It was an instant hit among students, reaching 30,000 likes over the span of a year. However, since the founders of NUS Confessions have graduated, the platform was left unmaintained. We saw the opportunity to build a better version of a confessions site for NUS, and build a platform that is tailored for anonymous sharing of opinions and stories. Thus, NUSWhispers was born.

Why did we choose the name *NUSWhispers*? Whispers is defined as speaking very softly using one's breath rather than one's throat, especially for the sake of secrecy; it is a subtle and mysterious way of sharing information that you don’t want everyone to know. We felt that it suitably captured the essence of the platform. Hence, NUSWhispers was chosen as the name for this reboot of a confessions app for NUS.

NUSWhispers aimed to tackle the problems faced by NUS Confessions:

- No indexing of confessions, unable to trace confessions as time goes by and older confessions gets pushed down.
- No categorization of confessions.
- Using Google Forms for collecting posts, unmaintainable as the volume gets larger.
- Posting to Facebook page is a hassle as it has to be done manually.

As CS students, we are empowered with technology to solve problems! We can implement a custom platform that tackles the pain points of NUS Confessions. NUSWhispers was implemented on a Laravel 5 + AngularJS stack, and has the following features:

- Moderation panel to display pending confessions for actions to be taken.
- Approving a confession automatically posts it to our FB page, without the need for manual FB page updates.
- Scheduling of posts to better spread out FB page updates.
- Standalone site that mirrors the content on the FB page. Likes and comments are synced via an hourly CRON job.
- Images can be submitted along confessions.

![NUSWhispers Site](/img/nuswhispers/ui-site.png)

![NUSWhispers Admin](/img/nuswhispers/ui-admin.png)

NUSWhispers was launched on April 7th 2015, and within the first day, it received 500 likes. As a content-heavy application, its value comes from content contributed by users. However, content-heavy applications face the Chicken and Egg problem. Which came first? The chicken or the egg? Likewise, if there is no content, there will not be users using the platform. However, if there are no users, there will not be content. Inspired by Paul Graham's article "[Do Things That Don't Scale](http://paulgraham.com/ds.html)", the development team provided the initial push needed to kick off the viral effect. We took turns to moderate, seeded our database with our own stories, and actively commented on the available confessions. NUSWhispers' popularity grew steadily, and to date, it has over 6200 likes, with over 17000 monthly active users and over 3 million impressions on Facebook!

Slowly, we were receiving stories, questions, and memes! We then came to realize that NUSWhispers was not merely just a confessions platform. It was a way for people to get themselves heard, a way for them to represent themselves. We are glad that our fellow students found value in NUSWhispers and hope that it will continue to serve the students of NUS well.

Most of the NUSWhispers founding team has graduated from NUS and the platform is currently maintained by our juniors. If you would like to help out with the platform, please drop us an email at <a href="mailto:nuswhispers@googlegroups.com">nuswhispers@googlegroups.com</a>!
