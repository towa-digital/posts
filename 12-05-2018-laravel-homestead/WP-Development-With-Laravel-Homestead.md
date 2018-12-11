# WordPress Development with Laravel Homestead

In a previous [post](https://www.towa-digital.com/news/local-wordpress-development-with-laravel-valet/) we described how you can use Laravel Valet for your local development environment. This post shows how to setup your local development environment based on [Laravel Homestead](https://laravel.com/docs/5.7/homestead).

## Laravel Homestead

[Laravel Homestead](https://laravel.com/docs/5.7/homestead) is an official package for [vagrant](https://www.vagrantup.com/). It's packed with all the needed software for a Laravel project, but the used stack is also suitable for any other PHP-based application.

The box includes the Nginx web server, PHP 5.6 til 7.3, PostgreSQL, MySQL, Redis, Memcached and few other software. You can find the full list in the [official documentation](https://laravel.com/docs/5.7/homestead#introduction).

It's perfect for an independent setup on your machine without installing any other software than vagrant and a VM-provider like virtualbox.

## WordPress & Homestead

We use the same bedrock-based setup as mentioned in our [post about the Valet](https://www.towa-digital.com/news/local-wordpress-development-with-laravel-valet/) example. The same applies here, you can use the default or any other WordPress Boilerplate.

It takes a little bit more time than setting up Valet, but it's just as easy.

### 1. Requirements

Before installing Laravel Homestead, check if you have vagrant as well as a VM-provider installed. Following VM-providers are supported: VirtualBox, VMWare, Parallels or Hyper-V.

Please also check the further information for the VM-providers other than vagrant [here](https://laravel.com/docs/5.7/homestead#installation-and-setup).

We use the combination of vagrant + VirtualBox.

### 2. Install Homestead

For installing Homestead you can either use vagrant or clone the repository itself. To download the Homestead-box via vagrant, use the following command:

`vagrant box add laravel/homestead`

If you consider cloning the Homestead-repo instead, use the following:

```bash
▲ git clone https://github.com/laravel/homestead.git ~/Homestead
▲ cd ~/Homestead

// Clone the desired release...
▲ git checkout v7.xx.0
```

After the cloning run the initialization script which creates the Homestead configuration file:

`bash init.sh`

There will be a `Homestead.yaml` file afterwards in the `~/Homestead` folder.

![Homestead initialized][homestead-initialized]

### 3. Configure

The created configuration file has everything we need already. We'll just adjust the mapping and domain-name for the demo-project, so it's callable via `towa.boilerplate.local`.

![Homestead configuration][homestead-config]

Nothing complicated or special there. Just map the desired project folder to the VM-folder. Also note the `/web` as the root, which is required for the bedrock setup.

To call the website via `towa.boilerplate.local` adjust your `~/etc/hosts` file:

![Hosts configuration][homestead-hosts-config]

So far so good. The final step before we need is to create a database to use. The database credentials are per default the following:

+ `host`: 127.0.0.1
+ `port`: 33060
+ `username`: homestead
+ `password`: secret

### 4. Start

That's it. Now you can start the vagrant box - will take a few minutes the first time - and then you're good to go.

For starting just run `vagrant up` in the `~/Homestead` folder. If the VM is ready you can open now `towa.boilerplate.local` and also `ssh` into the VM.

![WordPress via Homestead][homestead-wp-demo]

![Hosts ssh connection][homestead-ssh]

## Conclusion

Laravel Homestead is a nice option for your local development environment. It has a decent amount of preconfigured packages included which cover more advanced PHP-based applications. Based on that it's also perfectly suitable for WordPress projects.

If an opportunity comes up, we will also cover some more advanced usages of Homestead. For example you can used it on a per-project basis with composer, extend it or add environment variables and so on.

If you just need a basic PHP-stack with php, mysql and apache maybe Laravel Valet is an also option for you, which we mentioned above. Here is the corresponding post: [WP & Valet](https://www.towa-digital.com/news/local-wordpress-development-with-laravel-valet/).

## Resources

+ [Official Laravel Homestead Website](https://laravel.com/docs/5.7/valet)
+ [Official Vagrant Website](https://www.vagrantup.com/)
+ [Official VirtualBox Website](https://www.virtualbox.org/)

[homestead-initialized]: homestead-initialized.png "Homestead after installation and initialization"
[homestead-config]: homestead-config.png "Homestead configuration"
[homestead-hosts-config]: homestead-hosts-config.png "Hosts configuration"
[homestead-ssh]: homestead-ssh.png "Hosts ssh connection"
[homestead-wp-demo]: homestead-wp-demo.png "WordPress via Homestead"