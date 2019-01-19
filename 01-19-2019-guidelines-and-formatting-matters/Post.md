# Guidelines and Formatting Matters

Probably you already heard and saw a lot of coding guidelines and content about code-formatting and so forth. And it's good that there is a lot of content available, because it matters - quite a bit.

## It matters

If you have an experienced developer in your team or if you know one, you may see different types of configurations for coding rules and formatting. There is a valid reason behind it. We would argue it's the same which airbnb, facebook and others have: sustainability, maintability and efficiency.

You are enabling a common ground for your team, quality-wise, for discussions and for decisions. Sure it may seem a waste of time to invest couple of hours into the right configuration for you eslinter or if you want to use a space or tab based spacing, but consequently it will help to be more effiecient and save time!

![Tabs][tabs]

There are couple of more benefits which you get with a defined set of standard for your code and formatting. Just to name a few:

+ code-reviews and your code in general will be more readable
+ quality of your code will increase
+ bugs can be detected early
+ rule/community-based decisions instead of personal preferences --> objectivity

## Some insights

We introduced couple of topics during the last couple of month and it slowly is paying off - and we are still improving. Our current setup includes following tools and configurations for the following:

+ PHP: `php-cs-fixer`
+ JS (ES6), VueJS: `eslint`, `prettier`
+ SASS: `stylelint`, `prettier`
+ Markdown: `markdownlint`, `prettier`
+ Others: `prettier`

Also to ensure that the rules and configurations are applied on an automated-basis, we are using the `pre-commit`-hook for git to apply those with our `lint-staged`-configuration. Believe us, if you ever have that setup, there is no going back :)

We are planning to open-source our boilerplate for WordPress which includes all the above mentioned setup. Once that happens we will make detailed introduction to it and also explain what we have in place.

![Sneak Preview][sneak-preview-boilerplate-and-configs]

## Conclusion

It's not only about the beauty of your code. It's more than that. It actually helps to write better code and maintain it. It helps you and your team. That's why we are sticking to it and want to improve further.

## Resources

+ [PHP-CS-Fixer](https://github.com/FriendsOfPHP/PHP-CS-Fixer)
+ [Airbnb JS Style Guide](https://github.com/airbnb/javascript)
+ [Prettier](https://prettier.io/)
+ [Husky](https://github.com/typicode/husky)
+ [Lint-Staged](https://github.com/okonet/lint-staged)
+ [Standard](https://standardjs.com/)
+ ...

[sneak-preview-boilerplate-and-configs]: sneak-view-boilerplate-and-configs.png "Boilerplate Preview with Configs"
[tabs]: tabs.webp "Tabs vs Spaces"