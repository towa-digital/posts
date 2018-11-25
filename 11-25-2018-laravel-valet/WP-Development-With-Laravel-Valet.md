# WordPress Development with Laravel Valet

There are tons of options for setting up a local development environment for WordPress. We tried a couple of different ones with different tooling and setup configurations. In this post we want to show you, how you can use [Laravel Valet](https://laravel.com/docs/5.7/valet) for local WordPress development.

## Laravel Valet

Laravel Valet was primarily designed for local [Laravel](https://laravel.com/) development - sound obvious right? :).

Valet uses the built-in PHP server from Mac (yes Valet is limited to Mac-Users, but there are forks for [Linux](https://github.com/cpriego/valet-linux) and [Windows](https://github.com/cretueusebiu/valet-windows) - but we did not test those yet) and utilizes [DnsMasq](http://www.thekelleys.org.uk/dnsmasq/doc.html) to proxy all requests to the `.test` TLD to sites on your local machine. Valet also requires PHP and a database server installed locally on your machine.

It's a very simple and fast setup.

## WordPress & Valet

We are using a slightly modified [Bedrock](https://roots.io/bedrock/) setup for our WordPress projects, but you can also use the default one. The local setup is actually so easy, that we can just describe it as follows:

1. Install valet
2. Configure valet
3. Setup WordPress project

And that's actually it.

## Valet vs VMs

You should be aware that Valet is not a replacement for a virtual machine. If you need more advanced and extendes setup you probably have to use one. You could use for example [homestead](https://laravel.com/docs/5.7/homestead) - which we'll cover in a seperate blogpost.

## Resources

+ [Official Laravel Website](https://laravel.com/)
+ [Official Laravel Valet Website](https://laravel.com/docs/5.7/valet)
+ [WordPress Bedrock](https://roots.io/bedrock/)