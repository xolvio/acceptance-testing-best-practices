# Automated Testing Best Practices by [Xolv.io](http://xolv.io)
![Circle Build](https://circleci.com/gh/xolvio/automated-testing-best-practices.svg?style=shield&circle-token=:circle-token)

We at Xolv.io are testing and automation geeks that help other companies deliver higher quality, faster. We wrote [Chimp.js](http://chimpjs.com) to help us with this mission and we would like to show you how to use it properly **and be awesome at testing!**. This repository is a complete modern Agile development and testing setup that allows you to release features at high speed, and maintain that speed as the complexity of your team, codebase and domain increases.

Just like snowboarding or driving a car, your chances of forming good habits starts with knowing what the good habits are and then practicing them. We cannot emphasise enough the importance of testing. Too often we're called in to enterprise projects and asked "will the patient live?", and every single time, the root causes are the lack of automated tests and automation in general. 

The key to succeeding long-term, is knowing what makes your tests work with you and not against you. So we ask that you **read everything** on our [testing success factors](./content/TESTING-SUCCESS-FACTORS.md) page prior to digging into the codebase. You are going to know a lot more about a high-performance engine or snowboard if you RTFM!

We frequently meet developers that think they know how to do automated testing. When we dig deeper, we find they know how to do unit testing, but the distinction between acceptance and end-to-end testing is blurry for them. They have the best intentions but unfortunately they end up **building technical debt without knowing it**.

We are on a mission to fix this problem, and we're setting the example in this repository to show the way we do it. We also welcome and encourage all feedback as we have plenty to learn from the community.

\- Your friends at Xolv.io :)


#### Technologies & Tools

##### Meteor
In our view, JavaScript is currently the best language choice for modern web application development. It provides the ability to write code on the server, client, database and even build scripts. This reduces the cognitive load on developers that comes from context switching, and increases code reuse, both of which lead to higher productivity. 

Meteor embraces this view. It is a complete Node.js based full-stack JavaScript framework that emphasises fast feedback and a great developer experience. It has a great package system as well as being compatible with NPM. 

##### Packages

* **[Astronomy](http://astronomy.jagi.io)**<br/>
  Model layer for Meteor. Not only does this package allow you to write less code, it also makes it much easier to use techniques like Modelling by Example.
* **[React](https://facebook.github.io/react/)**<br/>
  Great view layer with some great design principles. It comes with built-in testing support and is testable entirely independently without needing to run Meteor. 

##### Testing Tools

In this repository, we have created a great developer experience for unit, acceptance and end-to-end testing, with super fast feedback. Here are the tools choices:

* **[Wallaby](http://wallabyjs.com/) (premium)**<br/>
  An IDE extension that gives you realtime feedback for your unit tests. Real realtime! You break a test, you instantly know. It also shows you which lines of code you don't have coverage for yet. You should seriously check this out if you haven't already. It will speed your entire get up!
* **[Karma](http://karma-runner.github.io/)**<br/>
  Used to run the unit tests in CI mode or when doing a full run locally. If you don't use Wallaby, you can also use Karma to run all the tests everytime you save a file.
* **[Chimp](https://github.com/xolvio/chimp/)**<br/>
  Our very own OSS package. Chimp allows you to drive the development of new features with quality built in from the outset. We have configuredit in this repository to drive the domain development first, then the UI for critical scenarios. 
* **[Whirlwind](https://github.com/xolvio/whirlwind)**<br/>
  Another package of our own, Whirlwind reduces test run times from hours to minutes using parallelization. It basically spreads the load of tests across CI nodes, and within them too.   
* **[Meteor Jasmine](https://github.com/xolvio/meteor-jasmine/)** *- Temporary until Meteor 1.3 is released*<br/>
  Meteor will soon support an app-testing mode as well as modules. As and when we understand the exact mechanics, we will change our strategy. For now, Velocity is the most effective way to do app-level tests.

## Installation & Usage

Please remember to **read everything** on our [testing success factors](./content/TESTING-SUCCESS-FACTORS.md) before proceeding.

#### Locally
1. Clone this repo<br/>
   ```
   git clone https://github.com/xolvio/automated-testing-best-practices.git
   cd automated-testing-best-practices
   npm install
   ```

2. Start the unit testing runner by either starting Wallaby from your IDE (highly recommended! See above), or you can start Karma with:
   ```
   node_modules/.bin/karma start
   ```
   
3. Start Chimp + Meteor without Mirror<br/>
   ```
   npm start
   ```
   Or if you like to have a Mirror (another Meteor app for Chimp to run against):<br/>
   ```
   WITH_MIRROR=1 npm start
   ```
   
4. Test and Develop!

If you'd like to run a full build locally, exit the scripts aboe and type:

```
npm test
```

#### On CI

TODO: Add sample `circle.yml` and `travis.yml` files

```
npm install
CI=1 npm test
```

More soon!
