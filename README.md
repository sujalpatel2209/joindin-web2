# Joind.in

This is the source code for the next generation of the Joind.in website - a resource set up to allow
events to get real-time feedback from those attending. It also gives speakers a 
way to claim and track their presentations over time.

This version is the next generation version, providing a responsive cross-device site for screens of all devices

You can either install joind.in on an existing PHP platform, or use our vagrant setup.

### Welcome

Joind.in welcomes all contributors regardless of your ability or experience. We especially welcome
you if you are new to Open Source development and will provide a helping hand. To ensure that
everyone understands what we expect from our community, our projects have a [Contributor Code of
Conduct](CODE_OF_CONDUCT.md) and by participating in the development of joind.in you agree to abide
by its terms.

## Quick start with Vagrant

To get you going without much hassle we created a vagrant-setup. To use it [fork the joindin-vm](https://github.com/joindin/joindin-vm) repository and follow the instructions in there.

This VM will load all three Joind.in projects (joind.in, joindin-vm and joindin-web2). 

## Other Resources

* The main website http://joind.in
* Issues list: http://joindin.jira.com/ (good bug reports ALWAYS welcome!)
* CI Environment: lots of output and information about tests, deploys etc: http://jenkins.joind.in
* Community: We hang out on IRC, pop in with questions or comments! #joind.in on Freenode

## Global .gitignore

git has the capability to define a global gitignore file , which means you can 
set up rules on your machine to ignore everything you don't want to include in 
your commits. This works not only for this project, but for all your other
projects too.

You can define the gitignore file with a command that looks like this, where the 
last argument is the file that holds the patterns to ignore: 

    $ git config --global core.excludesfile ~/.gitignore_global

Octocat gives [a good starting point](https://gist.github.com/octocat/9257657) for what to include, but you can also ignore the files used by your editor:

    # Eclipse
    .classpath
    .project
    .settings/
    
    # Intellij
    .idea/
    *.iml
    *.iws
        
    # Maven
    log/
    target/

    # Netbeans
    nbproject/private/

For more info on ignoring files, [github has an excellent help page](https://help.github.com/articles/ignoring-files/).

## Using A Proxy

Since web2 then calls the API, it can be tricky to see what is going on.  You can use a proxy tool such as Charles Proxy or mitmproxy to observe the requests that are being made by enabling the `proxy` setting in the config with a line that looks something like this:

    'proxy' => 'tcp://10.0.2.2:8888',

If the proxy tool is running on your host machine, you'll need to understand what IP address the guest thinks your host has, the easiest way to do that is to `vagrant ssh` into the VM and then type `last` to see where it thinks you logged in from.

Alternatively, try [Lorna's blog post about Wiresharking a VM](http://www.lornajane.net/posts/2014/wireshark-capture-on-remote-server).

### CODE STYLE

Please do your best to ensure that any code you contributed adheres to the PSR2 coding style. You can run php codesniffer using phing on an individual file like so:

```
phing phpcs -Dfilename.php
```

This will run codesniffer on any file within the regular source for joindin-web2. Wildcards work as does specifying part of the path in case the filename alone results in sniffing more files than you wanted.

To see a summary of the codesniff errors and warnings across the entire project, run

```
phing phpcs
```

This will show the files that still need some attention.

## License

The joindin-API is developed under a BSD-3 License. You can find the exact wording [in the LICENSE-file](LICENSE)
     
