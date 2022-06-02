![Bonding Health Logo](https://user-images.githubusercontent.com/146778/150411981-a07f26ad-93e7-45e0-91dc-48eb3296fd73.png)

# Bonding Health

A parent centric ADHD mobile app.

## Bonding Health Features

### Reporting

We will be storing child behaviors, from the perspective of the parent, along with the child's treatment regime.  This will help improve treatment adherance.  This will give parents a tool to refer back to for historical retrospective.  This will also give the parents the ability to provide their doctors with a historical data.  

Please download the [Dashboard design](design/dashboard.jpg) for details.
### Educational Content & Exercises

Our educational content is split between two different types of audio content.

1. Users will listen to 30 second audio that is used to provide them with guidance.
2. Users will listen to a guided exercise that includes our 7 motivational enhancement questions.  For more details [see below in variables](#data-variables).

[Our exercises can be seen here](README-exercises.md)

Please download the [Education design](design/education.jpg) for details.

### Analysis

Once users have input their children, added behaviors and treatments, and interacted with some of our educational content we will be able to display trends and historical data on both graphs and calendars.

[See below for details on what variables we plan to store.](#data-variables)

Please download the [Analysis design](design/analysis.jpg) for details.

### Onboarding

After parents have created their accounts they will be prompted to add a child.  For each child that they add the parent will complete [an intake form](README-intake.md) that we will store to develop a persona of that child for future data suggestion.

Parents will be able to easily create their accounts so as to reduce the time for them to have the "aha!" moment.  We will pressure users to create an account only after they try to save data within the app.
### Bonding Community **post mvp**

These discussionary group sessions will be pre-scheduled events led by a therapist and mediator to enable group discussion between users around specific child issues.  Imagine 5 people joining a moderated group audio phone call.


Please download the [Onboarding design](design/onboarding.jpg) for details.
## Technical Structure

- [Expo](https://docs.expo.dev/)
- [React Native](https://reactnative.dev/)
- [TypeScript](https://www.typescriptlang.org/)
- [React Hooks](https://reactjs.org/docs/hooks-intro.html)
- [Apollo GraphQL](https://www.apollographql.com/)
- [Firebase](https://firebase.google.com/) Cloud Functions host GraphQL server
- [Firebase](https://firebase.google.com/) Firestore host the database
- [Firebase](https://firebase.google.com/) Auth handles user authentication
- [Segment](https://segment.com/catalog/) (event tracking)
- [SplitIO](https://www.split.io/) (AB Testing kit)
- [Google BigQuery](https://cloud.google.com/bigquery) (data analysis and warehouse)

## Why React Native?

We opted to use React Native because of a few reasons.

1.  we are not displaying any 3D, GPU intensive experiences.
2.  We can deploy our application to multiple platforms: iOS, Android & Web.
3.  There is a large open source community with documentation.
4.  The code is mostly JavaScript, which is a relatively cheaper and easier coding language to hire for.
5.  We can build a product quickly and validate our hypothesis so that if we want to we can adapt to a native solution in the future.

## Why Expo?

Speeds up the compile times for faster Native development.

## Why TypeScript?

We decided to write (most of) our code in TypeScript because it will improve the performance of our testing libraries, Continuous Integration (CI) and Continuous Deployment (CD) pipelines. It also will help maintain code quality amongst our engineers and ensure each deliverable does not break out application. TypeScript also works with JavaScript so we can work with both for the time being to maintain a high velocity.

## Why GraphQL?

We chose GraphQL to make the transfer of data between our Backend and our Native app, as well as our CMS. This allows us to easily change Backend protocols from what we have now, which is Google Cloud Platform with NodeJS, and something different like Ruby or Java etc. By creating the GraphQL schema we have compartmentalized our frontend code such that if our backend database structure changes our apps will continue to function as expected. This provides us with technical agility and also makes the structure easier to comprehend.

## Why Google Cloud Platform?

A large array of services at affordable pricing considering the stages of development. Would not be difficult to switch to AWS if decided upon later.

## Why Firebase?

Free tier keeps our costs low. Easier setup for various services increases our velocity. Robust documentation

## Why Segment?

Segment aggregates data into a single source that can be shared amongst many data platforms such as Looker, Google Analytics, BigQuery and much more.

## Why BigQuery?

Serverless, highly scalable, and cost-effective multicloud data warehouse designed for business agility. Includes great tools for analysis of data at affordable prices.

## Why SplitIO?

SplitIO has easy to integrate component library that [works well with Segment](https://www.split.io/product/integrations/segment/) and React Native.


## [Backend API](https://github.com/BondingHealth/documentation/tree/main/api)


## Data variables

- child persona is determined by the [child intake form here](https://github.com/BondingHealth/documentation/blob/main/README-intake.md)
- exercises
  - Parent mood before and after each exercise is logged
  - Unique audio content will ask the user 7 questions [see exercises](https://github.com/BondingHealth/documentation/blob/main/README-exercises.md)
  - version 1: Audio only **MVP**
  - version 2: Audio & Text **post** mvp
  - version 3: Audio/Text, & Interactive Data Aggregation [see Exercise Readme](https://github.com/BondingHealth/documentation/blob/api/exercises/README.md) **post** mvp
- behavior reporting:
  - what behavior (options are maintained via the CMS)
    1. attention
    2. doesn't listen
    3. not following instructions
    4. organizing
    5. loses things
    6. fidgets
    7. on the go
    8. talks too much
    9. interrupts
    10. and more...
  - when was the behavior exhibited
    1. Date
    2. Time (optional)
  - where was the behavior witnessed (options are maintained via the CMS)
    1. Home
    2. School
    3. Park
    4. Therapist
    5. Friend's house
    6. Other
- treatment scheduling:
  - what treatment, and what dose (options are maintained via the CMS)
    1. An exhaustive list that cannot be outlined here...
  - when is treatment being administered
    1. Date
    2. Time (optional)
  - is treatment working as expected? yes/no?
- parent mood
  - before and after listening to audio content rate mood (rating is 0 or 1/happy or not)
- precision based inquiry
  - after specific events an in-app popup will appear with a simple question
  - these inquiries are managed by the CMS

## Dependencies

- NODE 14.16.0 because (at the time) this was the node version allowed by Google Cloud Platform.

## Local Development (see installation steps below first)

Note: You will need the API keys. Please ask an administrator for these.

1. In one terminal window, at the app root directory, start the local backend development server

   `$ yarn backend-start`

2. In one terminal window, at the app root directory, start the local frontend development server

   `$ yarn native-start`

3. To test locally on iOS Simulator press `i`, in the same terminal window as step 2, to automatically start the simulator.

   `$ i`

4. Start test runner (jest):

   `$ yarn test`

5. API GraphQL "emulator" server will be hosted at [http://localhost:5001/bondinghealth/us-central1/api](http://localhost:5001/bondinghealth/us-central1/api)
   Note: Local development is connected to a local database and local cloud functions.
6. Enable Expo's Remote Debugger within Expo client to see console logs. You must have this window in the foreground for it to function; it will notify you as such.

## Eslint

[rules](https://github.com/BondingHealth/documentation/blob/main/.eslintrc.json)

## Installation steps

1.  Install [VS Code IDE](https://code.visualstudio.com) (optional, you can use an IDE of choice but we used VSCode while building this app)
2.  Install [iTerm2](https://www.iterm2.com) (optional, convenient way to style your terminal)
3.  Install [Oh My Zsh](https://github.com/robbyrussell/oh-my-zsh/wiki/Installing-ZSH) (optional, lets you easily style your terminal)
4.  Install [Homebrew](https://brew.sh)
5.  Install [NVM](https://github.com/nvm-sh/nvm)

```
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
```

6.  Install NVM continued: Update `~/.zshrc` (this may happen automatically)

```
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```

7.  Install NODE using NVM

```
$ nvm install 14.16.0
$ nvm use 14.16.0
```

8.  Install [Yarn](https://yarnpkg.com/lang/en/) using Homebrew `$ brew install yarn`
9.  Install [Firebase CLI](https://firebase.google.com/docs/cli) `$ npm install firebase -g` `$ npm install -g firebase-tools`
10. Install [Apollo CLI](https://www.npmjs.com/package/apollo) `$ yarn global add apollo`
11. Install [Expo CLI](https://docs.expo.dev/workflow/expo-cli/)
12. Install [VS Code Apollo](https://marketplace.visualstudio.com/items?itemName=apollographql.vscode-apollo)
13. Install [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) - configure in VSCode settings
14. Install [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) - configure in VSCode settings
15. Install [husky](https://typicode.github.io/husky/#/?id=install-1) `$ yarn prepare`
16. Clone the repo `$ git clone git@github.com:BondingHealth/app.git`
17. Install dependencies from the app directory (bondinghealth/app) `yarn run install`

## Deployment

To update the production app both the frontend and backend must be on the server. To make this easy, there is one terminal command that updates both:
`$ yarn deploy`

## Folder Structure

```
root
├── package.json
├── static.json // used by CRA
├── .eslintrc.json
├── .prettierrc
├── packages
│   ├── native // Native mobile app
│   │   ├── package.json
│   │   ├── app.json
│   │   ├── babel.config.js
│   │   ├── metro.config.js
│   │   ├── App.tsx
│   │   ├── src
│   │   │   ├── core
│   │   │   ├── apps
│   │   │   ├── navigation
│   │   │   ├── assets
│   │   │   ├── jest
│   │   │   ├── AppAuthenticated.tsx
│   │   │   ├── AppUnauthenticated.tsx
│   ├── frontend // CMS
│   │   ├── package.json
│   │   ├── Procfile
│   │   ├── ...
│   ├── backend
│   │   ├── package.json
│   │   ├── src
│   │   │   ├── domains
│   │   │   ├── seed
│   │   │   ├── enums
│   │   │   ├── lib
│   │   │   ├── resolvers.js
│   │   │   ├── schema.js
│   │   │   ├── server.js
│   │   ├── ...
└── yarn.lock
```

## App Structure

![Bonding Health C1 Context Diagram](https://github.com/BondingHealth/documentation/blob/main/diagrams/diagram-context.png)
![Bonding Health C4 Component Diagram](https://github.com/BondingHealth/documentation/blob/main/diagrams/diagram-data-containers.jpg)

#### old

![Bonding Health Reporting](https://github.com/BondingHealth/documentation/blob/main/diagrams/diagram-dashboard-flow.png)
![Bonding Health Exercises](https://github.com/BondingHealth/documentation/blob/main/diagrams/diagram-exercises-flow.png)
![Bonding Health Settings](https://github.com/BondingHealth/documentation/blob/main/diagrams/diagram-settings-flow.png)

## Server cost breakdown:

### Firestore Costs & Usage estimate (wip)

!NOT! Cloud Storage

Overall it is better to reduce the number of reads and increase the storage, since sortage is cheaper as per this [pricing info](https://firebase.google.com/docs/firestore/pricing)

#### Free quota:

Stored data 1 GiB
Document reads 50,000 per day
Document writes 20,000 per day
Document deletes 20,000 per day
Network egress 10 GiB per month

#### Pricing beyond the free quota

Document reads $0.06 per 100,000 documents
Document writes $0.18 per 100,000 documents
Document deletes $0.02 per 100,000 documents
Stored data $0.18/GiB/month

#### User estimates

A = 10,000
B = 100,000

##### Below estimates are estimating the maximuma field could be

##### TransactionEvents

- createdDate: 25 bytes
- updatedDate: 25 bytes
- childId: 30 bytes
- dose: 10 bytes
- treatment: 30 bytes
- dates:
  10 bytes per array element
  roughly a max of 400 entries
  total: 4000 bytes
  = 4120 bytes = 4 kb

10,000 users: 40,000 kb = 40 mb

100,000 users: 400,000 kb = 400 mb = .4 gb

##### Children

- createdDate: 25 bytes
- updatedDate: 25 bytes
- parentId: 30 bytes
- gender: 12 bytes
- age: 5 bytes
- image: 100 bytes
- name: 30 bytes
- title 30 bytes (this could be deleted???)
  = 257 bytes = .3 kb

10,000 users: 2.57 mb (1 child per user)

100,000 users: 25.7 mb = 0.0257 gb (1 child per user)

##### BehaviorEvents

- behaviors 20 bytes x the number of rows
- childId: 30 bytes
- createdDate: 25 bytes
- updatedDate: 25 bytes
- when: 15 bytes
- where: 15 bytes
  = 150 bytes (2 behaviors per event)

10,000 users: 1.5 mb

100,000 users: 15 mb

#### Cost estimate:

##### Storage

10,000 users: 45 mb

100,000 users: 0.4257 gb 0.18/4 = $0.4 / month
