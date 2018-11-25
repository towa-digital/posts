# WordPress Development with Laravel Valet

There are tons of options for setting up a local development environment for WordPress. In this post we want to show you, how you can use [Laravel Valet](https://laravel.com/docs/5.7/valet) for local WordPress development.

## Laravel Valet

Laravel Valet was primarily designed for local [Laravel](https://laravel.com/) development - sound obvious right? :).

Valet uses the built-in PHP server from Mac (yes Valet is limited to Mac-Users, but there are forks for [Linux](https://github.com/cpriego/valet-linux) and [Windows](https://github.com/cretueusebiu/valet-windows) - but we did not test those yet) and utilizes [DnsMasq](http://www.thekelleys.org.uk/dnsmasq/doc.html) to proxy all requests to the `.test` TLD to sites on your local machine. Valet also requires PHP and a database server installed locally on your machine.

It's a very simple and fast setup.

## WordPress & Valet

We are using a slightly modified [Bedrock](https://roots.io/bedrock/) setup for our WordPress projects, but you can also use the default one. The local setup is pretty easy and can be done as follows.

### 1. Install valet with composer

`composer global require laravel/valet`

![Valet options and commands][valet]

### 2. Configure Valet

Run `valet install` for installing and configuring valet and dnsmasq. After the installation try pinging any `*.test` domain and you should see that `127.0.0.1` will respond.

#### Auto mapping projects

Valet has a super comfortable function, which maps local sites automatically to the configured TLD domain. For enabling switch to the folder which should be mapped and run `valet park`.

```bash
▲ cd ~/projects/valet
▲ valet park
```

All folders inside the used path will be mapped automatically. The folder name is also the site name.

![Valet mapping][valet-mapping]

### 3. Setup WordPress project

As usual :)

And that's actually it.

## Sharing sites

You can also share local sites to others with the `valet share` command. It enables sharing with a tool called **ngrok**.

```bash
▲ cd ~/projects/valet/towa-boilerplate
▲ valet share
```

 After running the command inside the project folder following screen appears:

![Valet sharing][valet-sharing]

## Further useful commands

+ `valet link`: add projects outside the parked folder
+ `valet secure`: secure a local site with ssl
+ `valet list`: list all commands

## Valet vs VMs

You should be aware that Valet is not a replacement for a virtual machine. If you need more advanced and extended setup you probably have to use one. You could use for example [homestead](https://laravel.com/docs/5.7/homestead) - which we'll cover in a seperate blogpost.

## Conclusion

Valet is a super simple and fast setup for a local development environment. It's suitable for WordPress and also a couple of other frameworks who have the same requirement stack.

## Resources

+ [Official Laravel Website](https://laravel.com/)
+ [Official Laravel Valet Website](https://laravel.com/docs/5.7/valet)
+ [WordPress Bedrock](https://roots.io/bedrock/)

[valet]: https://github.com/towa-digital/posts/raw/master/11-25-2018-laravel-valet/valet.png "Valet options & commands"
[valet-mapping]: https://github.com/towa-digital/posts/raw/master/11-25-2018-laravel-valet/valet-mapping.png "Valet mapping"
[valet-sharing]: https://github.com/towa-digital/posts/raw/master/11-25-2018-laravel-valet/valet-sharing.png "Valet sharing"