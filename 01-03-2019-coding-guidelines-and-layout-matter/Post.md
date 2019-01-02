# Coding Guidelines and Layout Matter

Probably you already heard and saw a lot of coding guidelines and content about code-formatting and similar. And it's good that there is a lot of content available, because it matters.

## It matters

If you have an experienced developer in your team or if you know one, you may see different types of configurations specificly for coding guidelines and formatting. There is a valid reason behind it: sustainability, maintability and efficiency. Additionally there is probalby some kind of tooling in place, e.g. some pre-commit hooks for git, to automate related tasks.

Aufbau:

- intro
- um was gehts
- warum guidelines wichtig sind
- warum das ästhetische wichtig ist
- warum das ganze automatisiert werden sollte

![Example Configuration][example-configuration-buddy]

The configuration has two default pipelines defined out of the box. First one is for the staging environment, last one for the production environment. The differences are in the specific configuration-keys like server-host or actions like the composer-command which is described with all the flags. Also when to trigger the pipelines differ. All up to you.

We are evaluating and improving the piplines continously. Our goal is to have a 100% infrastructure-as-code approach, where we can spin up environments as needed fully automated. If we achieve this, topics like feature-based environments are just a matter of configuration.

> We test and refactor the source code throughout a project. The deployment deserves no less. - *STEVE BERCZUK*

## Conclusion

Don't treat deployments as an extra or on-top task. It's part of the application/website itself as the core-code is. If the deployment is easy, you don't have a reason to not deploying early and often. If the deployment is complex, you want to find out all the trade-offs sooner than later.

## Resources

- [97 Things Every Programmer Should Know](https://www.amazon.de/Things-Every-Programmer-Should-Know/dp/0596809484)
- [Buddy](https://www.buddy.works)

[example-configuration-buddy]: example-config.png "Example configuration buddy"