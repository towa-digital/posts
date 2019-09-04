# Our WordPress CMS Setup - Part I - The Introduction

Boilerplates - probably the holy grail of frameworks to get started.
They have their *raison d'être* and therefore we here at TOWA also do have one.

## Intro

We would love to give you some insights, how we work in our WordPress CMS projects. Therefore we decided to publish a couple of blog-posts and guide you through our current CMS boilerplate. In that process, we also open source the boilerplate, which we are really excited about. In this post, we are mainly going to talk about the main structure and different parts.

## Need followed by action

Over the years, we worked on a various kind of projects, from small to big, from one-pager to a whole plattform, from a "poster" website to one which included several 3rd party services. While working on these projects, our development team created a need for some common ground, so that we don't repeat our code and work over and over again. With that need, the team realized, that having a common ground, a standardized way of working, would be a real benefit for the whole team and also for all the projects we would work on.

So the need was there. The awareness that something standardized should be there also. What was missing was the actual way. To keep it short, the first boilerplate at TOWA was born. The first version of our boilerplate was pretty straight forward and had some neat features. We introduced `gulp` as a task runner and built our development workflow based on it. We also had stuff like `scss`, `browsersync` and different tasks for a local and production environment. It was only the beginning where we would head to.

Because this post should introduce our current boilerplate and the roadmap we have in mind, we will take a big step forward to the year 2019 and show you, how we currently work and we also would love to give you some insights what we have in mind for the future.

## TOWA Boilerplate 2019

So welcome to the important part of this post. :) First of all, let us list the technologies and things we have in place. After that, we will explain what we like about that.

Stuff we have in place:

- our main structure is based on [bedrock](https://roots.io/bedrock)
- our custom theme is inspired by vuejs & laravel
- our build workflow is based on laravel mix
- technologies, frameworks, tools & topics we've integrated:
  - composer, webpack, yarn, scss, es6, twig,
  - prettier, stylelint, eslint, markdownlint, php-cs-fixer
  - buddy (ci/cd), documentation-guidelines, commit-hooks

![TOWA Boilerplate][towa-boilerplate]

### The good parts

Above you can see that we have some well-known tooling and frameworks in place. It was quite a way to find a good way to get them work well together. At the end, we combined different technologies and tools into one boilerplate. All the different parts have their own advantages. Let's talk about them.

#### The structure

The whole structure of the boilerplate is based on [bedrock](https://roots.io/bedrock) and has a couple of neat features included. First of all, `composer`, which also has WordPress itself as a dependency included. What a relief!
Another really neat feature is the whole separation of configuration and application files which gives us some additional security for hosting the projects. Simply explained: WordPress is installed in a subfolder and all configuration files (credentials, app-settings, etc) are placed in the root of the project. The entry point for serving the application is `/web` and therefore the configuration part is isolated to a certain point.
If you want to know more about bedrock, we would love to guide you to their website: [bedrock](https://roots.io/bedrock). Give them some kudos, they do a really great job!

#### Our Theme

The piece of gold in our boilerplate. Our theme setup has seen a lot. Over the last two years it got stable and we improved it bit by bit and we do have some further ideas on the roadmap. One of the most interesting things is probably that we use a combination of webpack + vuejs + twig. Also, we follow some WordPress guidelines, but we are following OOP to accomplish them.

##### OOP Approach

We will keep it short. For a more readable and maintainable code, we follow an OOP approach. That helps us to keep our code clean and follow some best-practices. To mention a nice and elegant example, we have a [fluent-interface-design-pattern](https://en.wikipedia.org/wiki/Fluent_interface) in place for our theme-setup.

![Theme setup][theme-setup]

There are some ideas, how we can improve our code and add some more flexibility to our theme-setup process. We try to let us influence by best practices from the community and other well-known frameworks, especially laravel - we heavily work with laravel for custom application development.

Btw, just to mention it, we have namespaces in place :)

##### VueJS, TWIG & REST-API

Within the WordPress setup, we integrated VueJS, but not totally decoupled yet with the provided REST-API. That was kind of a challenge, but it works pretty well with twig.

What we basically do is providing the needed data for the VueJS components by passing them into the components as data-attributes. That looks something like this:

![Passing data to Vue][towa-boilerplate-passing-data-to-vue]

So the twig engine kinda is the glue between the WordPress backend and the VueJS frontend. Besides that, we do have components that bind the data they need from the available rest-endpoints. In the screenshot, you can see some basic endpoints that can be consumed by the Vue-components.

![Vue and rest][towa-boilerplate-vue-and-rest]

So in conclusion for our theme, we do have two ways of providing data for the vue-components. The REST-API is probably the more common and flexible method. The combination of twig & vue is kind of a type of "server-side data binding", which does have some advantages. Furthermore we have webpack in place which does a lot of work for us and helps us to integrate different standards & toolings.

#### Some sparkles

To round up our whole development process, we try to integrate some practices for defining a standard in how we code and work. That reaches from styling & formatting to some coding rules. To be brief, here are some things we have integrated so far:

- we have `php-cs-fixer` for checking some php-coding rules
- we have linters for our stylesheets
- we have linters for our js-code
- we have linters for our vue-components
- we have linters for our markdown-files (documentation)
- we have `prettier` in use to format our code
- we have `pre-commit` hooks to automate our linters & formatters

Our goal with all that tooling is to avoid work in areas of our code where we don't really bring value to the project itself but keep our development standard. Therefore these things are automated as much as possible. The benefit of our teamwork is that we can keep a defined quality standard and have a defined way of working together.

## The famous future

There is a lot going on in the web-world. Quite a few topics are also affecting us and will have some impact on our way of working and technology standards. To anticipate, we can already tell what topics are in our roadmap and are already half-way through:

- Headless CMS Setup with WordPress & VueJS - WIP
- extending documentation standards - WIP
- dockerizing our setup
- integrating GraphQL in our setup
- integrating php tests
- integrating frontend tests

It's exiciting and necessary at once to pursue those topics. And we are all glad that we have an environment where we can do that. We will post about the new topics in the future and one of the next most exiciting things for us, as developers and also just to be part of it, is that we are going to open-source our boilerplate.

Thank you very much for your attention and we are going to give more insights, and also more in detail with coding-samples, in the near future. Meanwhile, take care :call_me_hand:

[towa-boilerplate]: towa-boilerplate.png "TOWA Boilerplate"
[towa-boilerplate-passing-data-to-vue]: towa-boilerplate-passing-data-to-vue.png "Passing Data"
[towa-boilerplate-vue-and-rest]: towa-boilerplate-vue-and-rest.png "Vue & REST"
[theme-setup]: theme-setup.png "Theme setup"
