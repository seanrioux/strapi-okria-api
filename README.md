# OKRIA API
An open-source API solution for managing and integrating OKRs, initiatives and activities into your applications.

## Table of contents
- [Introduction](#introduction)
- [Getting started](#getting-started)
- [Appendix](#appendix)

## Introduction
OKRIA is a setting and strategic planning model designed to better the objectives and key results model popularized by John Doerr.

### What is OKRIA?
If you’re familiar with OKR, it’s pretty easy to summarize OKRIA (it’s in our name). OKRIA stands for Objectives and Key Results, Initiatives and Activities.

In the OKRIA model, we have explicitly delineated the (often compounded) process of planning initiatives and activities from that of setting objectives and key results. In doing so we have worked to define a more holistic strategic planning model. Following the OKR example, we’ve defined simple (but opinionated) rules for the application of the process, considering organizational hierarchy and scalability, e.g.:

#### Initiatives
Initiatives are the projects, products, or product features that will be undertaken to increase, decrease or maintain key results. Initiatives are:
- **Clear in scope:** i.e. specific in terms of channel, activity and feature.
- **Segmented:** i.e. specific in terms of audience.
- **Deadlined:** i.e. time-bound; completed for a specific date.
- **Completable:** i.e. they can be completed; done.

#### Activities
Activities are the actions we take towards completing initiatives. Activities are:
- **Action-oriented:** i.e. defined by the specific work performed.
- **Resourced** i.e. identifying the specific team, or _resource_ responsible.
- **Atelic** i.e. represent an ongoing activity of business (one without a specific end in and of itself)

Put simply, we’ve extended OKR to help connect the dots (and ensure a clear separation) between the goals companies set and the work teams do to achieve them.

### What is OKRIA API?
OKRIA is committed to offering free tools to help support the adoption of the model. You can learn more about OKRIA [here](https://okria.io/). To help companies adopt the model in software applications, We've created this open-source Strapi based OKRIA management solution.

#### Use case
OKRIA API provides an API first CMS to help product managers and developers:
1. Create and manage OKRs
2. Plan initiatives and activities
3. Integrate these concepts with custom apps, or third-party tools

#### Features
OKRIA API has everything you need to get started:
- Strapi based CMS interface for product managers
- RESTful (or GraphQL) API for developers
- Authentication, User management, plugins, and more...

Learn more about the powerful Strapi CMS [here](https://strapi.io/documentation/3.0.0-beta.x/getting-started/quick-start.html) for full documentation and features.

## Getting started
Follow these step by step instructions to get started running OKRIA API in your local development environment.

### 1. Install
First, we'll install the required dependencies:

#### 1.1. Install Strapi
First, install Strapi globally using npm.
```
npm i strapi -g

```
#### 1.2 Install OKRIA API
The OKRIA API repo contains a package.json file with additional application dependencies as well as Strapi configuration files specific to the OKRIA API.

Clone the repo and install the dependencies as follows:

```
git clone git@github.com:okria/okria-strapi.git
cd okria-strapi
npm install
```

**Note:** If you intend to use OKRIA API in production (and develop it further) you may wish to fork the repo instead.

### 2. Run the application
Strapi includes a cli and a user interface to be accessed in the browser.

#### 2.1 Run in development
To run Strapi and ORKIA API in development mode:

```
strapi develop
```

**Note:** To review all commands enter `strapi`.

### 2.2 Login as Administrator
You will then be provided with a URL as follows to access the interface in the browser http://localhost:1337.

Visit this URL in the browser, and follow the provided link to navigate to http://localhost:1337/admin to create an administrative account and access the interface for the first time.

### 3. Create and Manage
Once you've logged in you will be presented with the Strapi interface. You'll find 4 content types that will allow you to create OKR, initiatives and activities. Let's walk through the complete process so you can see how the OKRIA API works:

#### 3.1 Create an initiative
The first thing we will do is create a master initiative. This typically is a project, product, product feature or another company initiative. We will use this to organize objectives and key results, and plan activities:

1. Click `Initiatives` in the sidebar and click the `Add New Initiative` button
2. Add an initiative name in the `Initiatives` field
   - e.g.  `Redesign of customer on-boarding experience`
3. Set a date for the completion of this initiative (typically an annual or quarterly interval)
4. Initiatives also have `Activities` for now, let's leave this field array blank for now
5. Save your initiative by clicking the `Save` button
6. You can now access this and other initiatives by clicking `Initiatives` in the sidebar

#### 3.2 Create an objective
Second, we'll create an objective for the initiative. An objective is a qualitative goal to give purpose to our initiative.

1. Click `Objectives` in the sidebar and click the `Add New Objective` button
2. Add an objective name in the `Objective` field
   - e.g.  `Release a more delightful onboarding experience`
3. Set a goal date for the completion of this objective (corresponding the initiative date)
4. Initiatives also have `Results` (key results). Leave this field blank for now
5. Save your objective by clicking the `Save` button
6. You can now access this and other objectives by clicking `Objectives` in the sidebar

#### 3.3 Create a metric
Before creating a key result we'll want to identify the key metrics which we'll use to measure our objective. A key metric is a quantitative measure which we will increase, decrease, or maintain through our activities and which will be used to measure achievement of our objective (as a key result).

1. Click `Metrics` in the sidebar and click the `Add New Metric` button
2. Add a metric name in the `Metric` field
   - e.g. `customer onboarding support requests` or `customer onboarding completion rate`
3. Add a unit in the `Unit` field
   - i.e. the unit name used for the type of metric
   - e.g. `count` or `percentage`
4. As relevant, add a unit symbol in the `Symbol` field
   - e.g. `$`, `%` or `kg`, etc.
5. If a symbol has been identified, we can also configure positioning for the symbol:
   1. Add a symbol `Position` i.e. `before` or `After`
   2. Indicate if the symbol requires a space between the metric value i.e. `10 kg` or `23.4%`
6. Once you have completed all the required fields, save the metric.
7. You can now access the metric by clicking `Metrics` in the sidebar

#### 3.4 Create key results
Once an objective and one or many key metrics have been created you can begin to define key results. Key results allow you to define the quantitative evidence that an objective has been achieved.

1. Click `Objectives` in the sidebar and navigate to edit your previously created objective
2. Under `Result` click `Add new entry` to add a key result
3. Select a `Direction` for your key metric
   - e.g. `increase`, `decrease`, or `maintain`
4. Select a `Metric` you created in the previous step
5. Identify the `Start` value and a `Goal` value used to grade achievement
6. Set a `Date` for the key result (considering the goal date of the objective)
7. Add additional key metrics (typical 2-3) by clicking `Add new entry`
8. Save the objective to save your key results

#### 3.6 Create resources
To complete planning our initiative activities to drive key results, we will have to engage team teams or team members (our resources).

1. Click `Resources` in the sidebar and click the `Add New Resource` button
2. Add a resource name in the `Resource` field
   - e.g. `marketing team`, `product team`, or `sales team`
3. Save your resource

#### 3.7 Create activities
Now we will return to our initiative to define the activities that will be required to complete the initiative.

1. Click `Initiatives` in the sidebar and navigate to edit your previously created initiative
2. Under `Activity` click `Add new entry` to add an activity
3. Select a previously created `Resource` from the list
   e.g. `design team`
4. Identify a `Task` that the selected resource must do to complete this initiative
   - e.g. `wireframe a new onboarding experience`
5. Estimate the amount of time the task will take by identifying:
   1. The activity `Cadence`
      - i.e. the time interval typically used to estimate this type of task
      - e.g. `day`,`week`,`sprint`, etc.
   2. An `Estimate` corresponding to the cadence
      - e.g. `2 days` or `2 sprints`, etc.
6. Save your initiative to save your activities.

### 4. API
Now that you have created example objectives, key results, initiatives and activities you will be able to interact with this content via a RESTful API. This will allow you to integrate the content in front-end or third-party applications.

#### 4.1 Manage permissions
In production, it will be important to ensure proper authentication of the API endpoint to ensure the security of critical data. While testing in our local environment, however, we'll use a public endpoint as a proof of concept.

To configure access to the various endpoints, we'll use the administrative interface:

1. In the sidebar click `Roles & Permissions`
2. Navigate to `Public` to manage public user role access
3. In the permissions section of the page, we'll activate the `find` permission for the resource endpoints we wish to access. In this case:
   - Initiative
   - Metric
   - Objective
   - Resource
4. Once the `find` permissions have been selected, click `Save`

#### 5.1 Test endpoints
We can now access endpoints for each of our content types in the browser or using an API tool (e.g. Postman) to consume the input content, via any front-end or third-party application.
1. Find all objectives via a `GET` request to `http://localhost:1337/objectives`
2. Find all initiatives via a `GET` request to `http://localhost:1337/intiatives`
3. Find all resources via a `GET` request to `http://localhost:1337/resources`
4. Find all resources via a `GET` request to `http://localhost:1337/metrics`

## Appendix
OKRIA API is new, but we will continue to enhance the offering with further customization to the Strapi interface, documentation, and use case example (including code). For now, please feel free to [reach out](mailto:info@okria.io) with comments or questions and to browse the resources below to explore further.

### Additional documentation
1. [Strapi documentation](https://strapi.io/documentation/3.0.0-beta.x/getting-started/introduction.html)
2. [Introduction to OKRIA concepts using the OKRIA canvas](https://okria.io/blog/introducing-okr-initiatives-activities-canvas)

### Authentication
To access the API securely, you'll want to set up authentication using one of the recommended authentication [methods](https://strapi.io/documentation/3.0.0-alpha.x/guides/authentication.html#authentication).

The process is (at a high level) as follows:

1. Navigate to the `Roles & Permissions` page and set authenticated user permissions.
2. Create a user with the authenticated user role
3. Retrieve PWT token with `POST` request passing user `identifier` and `password` to the `http://localhost:1337/auth/local` endpoint (note: parameters should be passed in the request body)
4. Access content endpoints with token in header (bearer token)

### Deployment and database
Deploying Strapi to production can be achieved with a range of possible [hosting](https://strapi.io/documentation/3.0.0-alpha.x/guides/deployment.html) and [database](https://strapi.io/documentation/3.0.0-alpha.x/guides/databases.html) configurations.

### Additional users and roles
Before on-boarding product managers or other user roles to the OKRIA API, you should create a safe permission set that ensures users can create content, but not manage other administrative functions.

We recommend creating a `manager` role, restricting access to the following permission categories:

- **CONTENT-MANAGER**
  - Contenttypes
  - Generalsettings
  - Groups
- **CONTENT-TYPE-BUILDER**
  - Contenttypebuilder
  - Groups
- **EMAIL**
  - All
- **USER-PERMISSIONS**
  - User (all except `me`)
  - Userpermissions (all except `init`)
