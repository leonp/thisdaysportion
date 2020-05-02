---
title: "Lessons learned from developing library self-service software: User testing isn’t as good as user using"
category: web
article: true
featured: true
---

Between December 2016 and May this year we developed a [library self-service progressive web app](/2016/12/managing-self-service-project/). At the time of writing, it's been deployed in 35 of 44 of our libraries, so it's a good time to start thinking about what went right and wrong, and what I could have done better.

My first observation is a simple one, and probably self-evident, and contains a lot of <i>use</i>s:

{% include pull-quote.html text='User testing isn&#8217;t as useful as watching users use your product in real life. <span role="img" aria-label="A look of absolute shock">😲</span>' %}

Over the course of the project I conducted all testing, arranging sessions in libraries with around 15 'real', representative users, from ages 8 to around 70. Libraries are democratic spaces, and if you observe visitors in a busy branch you'll see a very broad demographic. On the one hand it's really exciting to see your product being used by so many different people, on the other it does pose several design challenges (more of which in another post).

{% include figure.html url="kiosk-user.jpg" alt="A person using a self-service kiosk" caption="A new self-service kiosk in use" %}

I have plenty of experience testing websites using a [simple kiosk testing methodology](https://www.nngroup.com/articles/why-you-only-need-to-test-with-5-users/), so I understand the need to get out of the way, not provide hints and phrase tasks in as neutral a way as possible. However, testing self-service software is more challenging than testing a website as there are additional, environmental factors to consider.

For example, self-service users have to manoeuvre physical objects while interpreting information on a screen. They may well be in a queue or using the system with a child. In this case, some have been using the same system for eight years, so when they do get to the machine they'll simply perform _exactly_ the same sequence of movements and screen presses as they have the last several hundred times.

Kiosk tests, on the other hand, take place in isolation. The users have more time to consider what they're doing and they don't have the immediate pressure of children or other users standing behind them. In fact, because they know they're testing something they'll approach it as something to learn, and to take their time over.

No-one wants to learn new UI in the real world unless they know they'll get something back. When buying a new car or phone, for example, or through learning something new. There's little financial or emotional return in self-service kiosks. They're something to use as briefly as possible.

So I quickly found we got by far the most useful feedback once an app change was deployed in the wild. Niggles that had been smoothed over by a patient approach from testers became full blown problems in real life.

It therefore would have made more sense to **go live with new features as soon as possible, and observe them "in the wild"** -- and to make sure changes were made quickly. We worked to fortnightly sprints, so we should have been pushing these new features at the end of each sprint based on feedback from the last sprint. Instead, we too often went on to the next batch of features to implement on our staging site and only made the changes live once we had completed our first version. (Our MVP was too big, but that's for another post as well.)

One word of caution on this though: If you're replacing a mature, well-used product this can be tricky. It's not easy to change a system *and* leave existing features out until they're developed at a later date.
