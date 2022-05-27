## Case Study: WeShare Plus

![weshare-015](https://i.imgur.com/FE5Epkm.jpg)

**Post to WeChat and Weibo at the same time with just one tap.**

[iTunes演示视频](http://v.youku.com/v_show/id_XMzkzMjAwMDkwMA==.html)

## Background

No matter if you use WeChat or not, you might hear of it. WeChat is a messaging and calling app that allows you to connect with family & friends across countries easily. It's the all-in-one communications app for text (SMS/MMS), voice and video calls, Moments, photo sharing, and games. WeChat had hit 1 billion monthly active users in March 2018, which means almost every Chinese mobile user is a WeChat user. Besides connecting with family and friends, WeChat users often share their life via Moments, which is a build-in Facebook-like function in WeChat.

Weibo maybe not as multi-functional and favorite as WeChat, but it is still one of the most popular social media platforms in China. As a China-based microblogs platform, Weibo has over 431 million monthly active users. Different from WeChat, any users can follow other accounts without being friends, which makes it feels more like Twitter: you can follow celebrities or leaders from different domains.

A lot of active internet users in China have both accounts of WeChat and Weibo, and when they share on these two platforms, they need to do it separately. It quite easy to understand: WeChat and Weibo are competitors. That takes a bunch of time if you post on social frequently.

Can we share things on WeChat and Weibo at the same time, for just one post? When I copy and paste my posts to share them on both platforms, I found it is a big user need for me. After talked with some guys on social media, I realised I'm not alone, and there are quite a lot of people have this need too. As a UX designer and a member of an iOS dev team, I decided to create an app for that need: post to WeChat and Weibo at the same time with just one tap. So the project of WeShare+ began.
![weshare-016](https://i.imgur.com/5UeksM9.jpg)


## My Role

I was the product manager, UX /UI designer and marketer of the app. 

## Challenge

### Validate user needs
The first question we need to answer is the critical user need of WeShare+. It not a hard question, because as an active user of WeChat Moments and Weibo, I know exactly what the user need is: Write and send post fast and straightforward. 

However, as a UX designer who was on designing his first owned product, I found it was necessary to validate the needs with users. So I sent invitations on my social media channels inviting potential users to join the WeChat group for discussion and text. After the first round of invitation, we had an online group of 50 active users to help us do some research. 

![weshare-009](https://i.imgur.com/P0radMB.jpg)
![weshare-011](https://i.imgur.com/TW3K2Zw.jpg)

I designed a survey that asked a bunch of questions about social media, and the goal of the survey was to validate the critical user need I presumed: write and send a post to WeChat and Weibo fast and simple. To our surprise, we got some feedbacks which we never thought of. For example, manage and share a post to different WeChat account, or share to more social media platforms such as Facebook, Instagram, Twitter and QQ. 

We ranked the difficulties, benefit for marketing and importance for users, then selected some key features we need to make it best.

![weshare-001](https://i.imgur.com/45mUCpE.jpg)
![weshare-006](https://i.imgur.com/dM3Lscf.jpg)

After that, I built concepts, wireframes and prototypes according to the user research. It took a while before we started the developing, but as a part of user-centred design, it was essential for the whole progress.

![weshare-003](https://i.imgur.com/OP4dvEo.jpg)

### API

As two biggest social network platforms in China, WeChat and Weibo have complex API workflows for developers. The problem was they keep updating it, which made the developing progress took much longer time than we thought. However, everything has two sides. I learned a lot from a product manager's perspective. After figured out the steps we need to do for applying a developer verification, which was essential for WeChat and Weibo related function developing, I carefully arranged our schedule for the productivity. 

![weshare-002](https://i.imgur.com/XuRQ7b7.jpg)

### Limitation and solution

After the user research, we did what our aim at in the first step of using the app: user can write a post with pictures smoothly and straightforwardly. I made the wireframes again and again and tested them with paper and low fidelity prototypes among users. All the steps were optimized for a smooth and fast user experience. 

![weshare-005](https://i.imgur.com/9j29AlR.jpg)

However, the second step, posting to WeChat and Weibo with a single tap, was not that easy. The tough issue was that WeChat doesn't allow any apps to post directly to Moments outside WeChat. To be clarified, the iOS Share function was not released at that time. We managed to solve the problem by saving the texts which user inputted in WeChat to the clipboard of the mobile. When a user writes something in WeShare+ and press the Send button, the text will be shared to Weibo in the background, and the app will jump to WeChat Moments input frame, and the user can tap in the input box to paste the copied text from WeShare+. 

![weshare-014](https://i.imgur.com/9hjx878.jpg)
![weshare-013](https://i.imgur.com/nR8IEU9.jpg)

It was not as we designed, but it was the best solution we could do with WeChat's limitation. It DID increase the complexity for users learning how to use WeShare+ for the first time. So I created a nice gif and video to help the user build the 'mental model' of how to use WeShare+.

![Add_to_Notification_withSpot](https://i.imgur.com/5bVxJgY.gif)


### Good product will do the marketing automatically

Before we released the first version of WeShare+,  we invited all the users from the test group test it via Test Flight, which helped us find some bugs before it online. Because we didn't have enough hands for marketing as a small team, we decided to focus on improving the usability and user experience by updating the app. Then we found the focus on the quality of the product was the best way to market. The app was shared mouth-by-mouth, and after 2 months organic growing of hundreds of active users daily, we surprisingly found the amount of download from App Store was over 250,000.

![weshare-008](https://i.imgur.com/D2FNLtQ.jpg)
![weshare-012](https://i.imgur.com/m1RsGap.jpg)


## Things I learned

* Lean design and develop progress - Keep it simple and fast
* A complete UX design journey - User research, prototype, wireframe, user test, user focus group, usability test, etc.
* How to find a solution within the limitations.
* 
![weshare-018](https://i.imgur.com/w6ONWVt.jpg)

## Result

* WeShare+ was downloaded more than 300,000 times and was the second app on the Social Network billboard in App Store.
* The tech media SSPai [wrote a report about WeShare+](https://sspai.com/post/28753) in April 2015
* After I moved to New Zealand in July 2016, my developer partner and I found it was hard to maintain the app because of the changes of WeChat and Weibo API policies. In 2018, we sold the app to SHENZHEN WIDELY POPULAR SMALL LOAN CO., LTD

![weshare-017](https://i.imgur.com/4Ggk0hF.jpg)

[Check it in App Store](https://itunes.apple.com/cn/app/wei-xiang+/id946806977?l=zh&mt=8)

[Intro video of WeShare Plus](https://v.youku.com/v_show/id_XMzkzMjAwMDkwMA==.html)