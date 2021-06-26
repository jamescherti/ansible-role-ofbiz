# ansible-role-ofbiz
[Ansible-role-ofbiz](https://github.com/jamescherti/ansible-role-ofbiz) is an **Ansible role** that **installs Apache OFBiz** on Linux operating systems (Debian, Ubuntu, and Arch Linux).

## Author
- [James Cherti](https://github.com/jamescherti/)

## How to use the Ansible role

```yaml
- {role: ofbiz,
   ofbiz_version: "17.12.07"}
```

## Run Apache OFBiz for the first time

After Apache OFBiz is installed by this Ansible role:

Switch to the user 'ofbiz':
```shell
$ su -l ofbiz
```

Change the directory to 'current':
```shell
$ cd ~/current
```

Prepare Apache OFBiz (may take time):
```shell
$ ./gradlew cleanAll
```

Load Apache OFBiz data and create the admin user (first time only):
```shell
$ ./gradlew "ofbiz --load-data readers=seed,seed-initial" loadAdminUserLogin -PuserLoginId=admin
```

The command above will load the data:
- seed: Apache OFBiz and External Seed Data, generic config, permission, help screens
- seed-initial: Apache OFBiz and external seed data
- ext: External general data

Run Apache OFBiz:
```shell
./gradlew ofbiz
```

Visit Apache OFBiz through your browser:
- https://localhost:8443/ordermgr
- https://localhost:8443/accounting
- https://localhost:8443/webtools

By default, you can log in with the user 'admin' and password 'ofbiz'.

## Links
- [Ansible role to install Apache OFBiz (GitHub repository)](https://github.com/jamescherti/ansible-role-ofbiz)
- [Install Apache OFBiz without demo data](https://cwiki.apache.org/confluence/display/OFBIZ/How+to+Install+OFBiz+without+the+Demo+Data)
- [Apache OFBiz Tutorial - A Beginners Development Guide](https://cwiki.apache.org/confluence/display/OFBIZ/OFBiz+Tutorial+-+A+Beginners+Development+Guide)
- [Apache OFBiz videos on YouTube](https://www.youtube.com/user/ofbiz) and [Apache OFBiz videos on Vimeo](https://vimeo.com/user2598348/videos/)
- [Apache OFBiz mailing lists](https://ofbiz.apache.org/mailing-lists.html)
