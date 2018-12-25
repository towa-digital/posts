# Deploy early and often

I want to talk about an advice we believe in and which is also stated in the book *97 Things Every Programmer Should Know*. It states **Deploy Early and Often**.

## Assumption

The team has everything under control. Features and bugfixes are developed by a strategy like git-flow. Local and testing stage are working perfectly fine and everyone is happy. One day before the official launch of the new website or application, the team triggers the deployment for the production environment. Deployment starts as expected and one task after antoher is finished successfully. You open up your browser and hit the beta link. An empty blank page or probably one of the most frustrating phrases in the developers life "500 Internal Server Error" appears - **yikes**.

## Cause & what you actually loose - Business Value

The deployment to the final environment is probably one of the last things you or your team does for the project. Doing this step at the end can cause some unseen and probably unnecessary troubles which additionally lead to bad mood. Have to admit here, that we still do this on several projects or project-types - but not for long. To prevent this, we are shifting to the mindset of **deploy early and often**.

### What you actually loose - Business Value

Besides the troubles for the development & DevOps team and the bad mood, you actually can't deliver actual **business value** for the customer. The application up & running on the developers machine or staging is just half the truth. Until it's not up and running on the final environment, you still have work to do - you didn't deliver.

## First steps to deploy early and often

First thing in a new project we do is to set it up locally. After that, the deployment to staging and also production environment should follow. To accomplish this, we you need the right infrastructure. Assuming you have some kind of infrastructure for your testing & production environments, we want to show you, how we handle website-projects at the moment.

For our website-projects we have a built-in configuration in our boilerplate for the deployment service [Buddy](https://buddy.works/). Buddy is our service to go at the moment. Our configuration looks something like:

![Example Configuration][example-configuration-buddy]

The configuration has two default pipelines defined out of the box. First one is for the staging environment, last one for the production environment. The differences are in the specific configuration-keys like server-host or actions like the composer-command which is described with all the flags. Also when to trigger the pipelines differ. All up to you.

We are evaluating and improving the piplines continously. Our goal is to have a 100% infrastructure-as-code approach, where we can spin up environments as needed fully automated. If we achieve this, topics like feature-based environments are just a matter of configuration.

> We test and refactor the source code throughout a project. The deployment deserves no less. - *STEVE BERCZUK*

## Conclusion

Don't treat deployments as an extra or on-top task. It's part of the application/website itself as the core-code is. If the deployment is easy, you don't have a reason to not deploying early and often. If the deployment is complex, you want to find out all the trade-offs sooner than later.

## Resources

+ [97 Things Every Programmer Should Know](https://www.amazon.de/Things-Every-Programmer-Should-Know/dp/0596809484)
+ [Buddy](https://www.buddy.works)

[example-configuration-buddy]: example-config.png "Example configuration buddy"