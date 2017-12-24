---
layout: post
title:  NUSMods R - The Engineering Behind
date:   2017-12-25 00:00:00
author: Yangshun Tay
author_github: yangshun
author_thumbnail: 558978353
excerpt: >
  Today we are very excited to be releasing a new version of NUSMods for everyone to use. This release is NUSMods' third version since the project was originally started in 2012 by Beng, founder and creator of NUSMods. NUSMods R has been in development for over a year and will finally be available for use thanks to the hard work of a team of young and talented developers from School of Computing.

---

Over the period of a year from Jul 2016 to Jul 2017, NUSMods saw over 2.5 million sessions, over 250,000 users (including returning users) and over 9 million pageviews, with the peak periods being the start of the semesters. Freshmen often have difficulty understanding the module and bidding system but with NUSMods the process is made much smoother. Many seniors recommend the freshmen to use NUSMods for module planning purposes. Even exchange students use NUSMods and they often exclaim that they wished they had such a platform back in their own university. The immense popularity and usefulness of NUSMods and the impact that NUSMods has over the school population drives us to keep innovating and making NUSMods better. Another goal of NUSMods is to provide a platform to encourage students to experiment and create original community-engaging work via the [NUSMods API](https://github.com/nusmodifications/nusmods-api).

Today we are very excited to be releasing a new version of NUSMods for everyone to use. This release is NUSMods' third version since the project was originally started in 2012 by [Beng](https://github.com/ahbeng), founder and creator of NUSMods. NUSMods R has been in development for over a year and will finally be available for use thanks to the hard work of a team of young and talented developers from School of Computing. NUSMods is a student-initiated project driven by the needs of students and desire of individuals to solve common university life problems with technology. The NUSMods core team has put in a tremendous amount of time and effort over the past year during both semester period and holidays to make this possible. Many thanks to the people involved in the development of NUSMods R - [Zhang Yi Jiang](https://github.com/zhangyijiang), [Li Kai](https://github.com/li-kai), [E-Liang Tan](https://github.com/taneliang), [Ng Zhi An](https://github.com/ngzhian), and [Yangshun Tay](https://github.com/yangshun).

The new version brings about some much needed enhancements such as multi-platform compatibility, performance improvements, increased customizability, and solves many of the pain points of the previous version. We redesigned the user interface, rethought the user experience, rewrote the entire code base and removed a number of features that were not commonly used among students so that your usage experience will be greatly enhanced. Here are some of the highlights in the new release:

## Timetable Re-hauled

![NUSMods Desktop Screenshot](/img/nusmods-r/timetable-desktop.png)

The previous timetable was written in 2014 when v2 was release. While it is a robust implementation and it worked, it wasn't mobile responsive and was tougher to improve upon. [Yangshun](https://github.com/yangshun) took the chance to re-haul the timetable in terms of implementation, design and user experience, rewrote the timetable into a reusable component that would look great on both desktop and mobile devices, yet retaining its snappy performance.

One major change we made was to **kill Drag and Drop**. To change lessons, you would have to tap on the lessons to view the alternative slots and tap on the intended slot to confirm the selection. Drag and drop was not a suitable interaction on mobile for scrollable interfaces. Killing Drag and drop and reverting to good old tap and select allowed us to keep the interactions across the various supported platforms consistent. Drag and drop is also not great when there are many alternative slots and you just want to view them without changing your existing selection.

We have received feedback from students that they preferred a vertical orientation for the timetable because it was more similar to Google Calendar/iCal. We contemplated switching to a vertical orientation but feared upsetting those who preferred and were used to the horizontal version. To make everyone happy, we now allow you to toggle the timetable orientation! Implementing this was a technical challenge for us and we are pretty proud of the approach we took to solve it.

<div class="text-center">
  <img src="/img/nusmods-r/timetable-iphone.png" alt="NUSMods iPhone Screenshot" style="width: 50%">
</div>

Lastly, we now let you customize the colors of the lessons on the timetable. No longer do you need to refresh the page repeatedly just to get a colour combination that you like before exporting the timetable. You may also hide certain modules from the timetable if you wish.

*Many thanks to [Yangshun Tay](https://github.com/yangshun), [Zhang Yi Jiang](https://github.com/zhangyijiang), [Li Kai](https://github.com/li-kai), [Ng Zhi An](https://github.com/ngzhian) and [E-Liang Tan](https://github.com/taneliang) for their work on the timetable.*

## Module Finder and Module Pages

![NUSMods Desktop Screenshot](/img/nusmods-r/module-page.png)

The module finder has been one of the unique selling points of NUSMods. We allow students to filter modules according to a list of criteria that CORS does not allow you to, such as by levels, number of MCs, lecture and tutorial timings so that you can find the perfect module that lets you have a three-day week. Yi Jiang revamped the module search experience such that it is now much faster and you can easily find a module that meets your criteria, by filtering with keywords which match module descriptions and titles. Did I also mention that the module finder page works really well on mobile?

On the module page, Li Kai rewrote the module Prequisite Tree section with a custom implementation we thus removed the need for D3, a large charting library, shaving off over 100kb in payload size sent to clients. Yi Jiang put the whole page together and redesigned the CORS Bidding Statistics section such that the data was grouped by rounds and faculty, making it easier to read.

*Many thanks to [Zhang Yi Jiang](https://github.com/zhangyijiang), [Li Kai](https://github.com/li-kai) and [Ng Zhi An](https://github.com/ngzhian) for their work on the Module pages.*

## Venues

![NUSMods Desktop Screenshot](/img/nusmods-r/venues-page.png)

The venues feature is one of my favourite features in NUSMods and probably one of the most underrated ones. The venues feature shows you what class is going on right now (or really, any time of the week) for a particular venue, and the venues data is reverse engineered from the lesson timetables of all the modules. In NUSMods v2, the venues timetable was using a separate component and did not have colours. Although E-Liang was new to the NUSMods code base, he ported the Venues page extremely quickly, reusing the main timetable component and at the same time, improving the design of the page.

Yi Jiang also ported the venue availability feature, so that you can find unoccupied venues to crash during your long breaks between lessons.

*Many thanks to [E-Liang Tan](https://github.com/taneliang) and [Zhang Yi Jiang](https://github.com/zhangyijiang) for their work on the Venues pages.*

## Performance and Infrastructure

Aside from enhancing the product itself, we have channeled a fair bit of effort in improving the developer experience and app infrastructure. We believe that taking a step back and improving on our tools will enable to move even faster in the long run and iterate quickly on the product. NUSMods R makes use of the latest and greatest tools out there - React, Redux, Jest, Flow, webpack, Yarn, Babel, etc. Most of these tools are built by [Facebook](https://code.facebook.com/projects/) and have an awesome developer experience.

While developing, we encountered some performance issues with our development tools and used/built some tools to solve them:

- Slow webpack boot up time. Solved by integrating the webpack DLL plugin, restricting webpack loader search space and caching Babel and ESLint parsing artifacts.
- Slow Flow boot up time. Solved by not checking `node_modules` directory on boot with the help of [flow-scripts](https://github.com/yangshun/flow-scripts) written by Yangshun.
- Cache ESLint result across runs.

Li Kai extracted the best parts of [create-react-app](https://github.com/facebookincubator/create-react-app) webpack's configurations, integrated it into our webpack configurations. He also integrated [Netlify](https://www.netlify.com/) so that each Pull Request made is automatically deployed somewhere for previewing. This allows Pull Request reviewers to test the changes online without having to patch and test locally.

*Many thanks to [Li Kai](https://github.com/li-kai) and [Yangshun Tay](https://github.com/yangshun) for their work on the performance and infrastructure aspects of NUSMods R.*

## Better Engineering

With many years of experience in building and maintaining NUSMods, we were well aware of the problems with the existing code and set to solve them in the rewrite. NUSMods R was rewritten with better engineering practices, performance and code maintainability in mind.

Team members come and go and the [current team](https://nusmods.com/team) represents the third generation of developers since NUSMods' inception. Hence, it is especially important to write future-proof code that withstands the test of time and changing members. Front end developers with a fair amount of experience but are new to the NUSMods code base should be able to understand the code easily, add new features with the confidence that they won't break existing stuff. We have also enforced a code review process so that the team is aware of what each other is working on and any design mistakes are caught earlier, at a stage where they are the least costly to fix. Lastly, we hope that we won't have to rewrite NUSMods ever again and instead, evolve it incrementally as new technologies emerge.

In a nutshell, our code had to be:

1. Readable and documented
1. Easily onboard new developers
1. Robust and well-tested
1. Good performance - load fast and run fast
1. Easily improved with newer technologies

With these considerations, we evolved our engineering stack:

<table class="table">
  <tr>
    <th></th>
    <th>NUSMods 2.0</th>
    <th>NUSMods R</th>
  </tr>
  <tr>
    <td>Bundler</td>
    <td>Grunt + Browserify</td>
    <td>webpack</td>
  </tr>
  <tr>
    <td>Language</td>
    <td>ES5</td>
    <td>ES6 / Babel</td>
  </tr>
  <tr>
    <td>Packager</td>
    <td>NPM</td>
    <td>Yarn</td>
  </tr>
  <tr>
    <td>Application</td>
    <td>Backbone + Marionette</td>
    <td>React + Redux</td>
  </tr>
  <tr>
    <td>Styles</td>
    <td>Sass</td>
    <td>Sass + CSS Modules</td>
  </tr>
  <tr>
    <td>Linting</td>
    <td>JSHint</td>
    <td>ESLint</td>
  </tr>
  <tr>
    <td>Types</td>
    <td>N/A</td>
    <td>Flow</td>
  </tr>
  <tr>
    <td>Tests</td>
    <td>N/A</td>
    <td>Jest + Enzyme</td>
  </tr>
</table>

Why we are using what we are using:

- React is great for writing modular, encapsulated UI and is extremely hot these days in the front end scene. A functional and declarative UI paradigm results in fewer hops in logic and makes our code more predictable.
- As a non-trivial interactive application, Redux came in very handy in keeping our data in sync for different parts of the application.
- React and Redux code are also generally easy to test because they are nicely layered with clear separation of concerns.
- Jest made testing fun and easy to do, with a watch mode and snapshot testing.
- CSS Modules fixes the problem of global namespace in CSS and lets you write styles that are local by default and encapsulated to your component.
- ESLint standardized our coding style so as to improve code readability and reduce the amount of stylistic nits during Pull Requests reviews.
- Flowtypes (although annoying at times), allowed us to add static types to our code so that bugs can be caught earlier during development rather than during runtime.
- webpack enabled us to create modular and optimized bundles of code for deployment.

We're pretty happy with the tech stack we have chosen and strongly believe that we have made the right choices in achieving our goal of better engineering.

## NUSMods R By the Numbers

- [**9 contributors**](https://github.com/nusmodifications/nusmods/graphs/contributors?from=2016-08-22&to=2017-12-23&type=c) to the code
- **386** commits made
- **113049** lines of code added. **43097** lines of code removed
- **393216** ways to customize your timetable (assuming a normal workload of 5 modules)
- Initial load time of **885ms**
- Bundle size of **605 KB** (after Gzip)

We've already heard from many voices about NUSMods R while it was in beta, and here’s what they have to say:

> **Get your school life in order with NUSMods R**
>
> *- Ng Zhi An, Software Engineer at Google*

> **The only working planner**
>
> *- Yeo Quan Yang, Security Engineer at Apple*

> **What? A responsive timetable planner? Shut up and take my money!**
>
> *- Yangshun Tay, Front End Engineer at Facebook*

> **Best in class in a monopoly market 🌝**
>
> *- Karen Ang, Ex-Software Engineering Intern at Google*

## To Infinity and Beyond

NUSMods R marks a major milestone for us and is a huge improvement in terms of both product and engineering. This would not have been possible without the dedication of the NUSMods core team and hard work they have put in over the past year. Moving forward, NUSMods will be led by [a new generation](https://nusmods.com/team) of student developers from School of Computing - [Li Kai](https://github.com/li-kai), [Zhang Yi Jiang](https://github.com/zhangyijiang) and [E-Liang Tan](https://github.com/taneliang). There is still a ton of work left to be done, such as further improving the performance and writing more tests. We also have the intentions to revamp the API using GraphQL so as to batch API requests on the client. Do reach out to them if you are interested in contributing to or collaborating on the project.

With this release, we hope that students of NUS enjoy using NUSMods more than ever and also hope to inspire budding developers with our engineering culture and practices!
