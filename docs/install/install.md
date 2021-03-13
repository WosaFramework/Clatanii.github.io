# Installation
Did you just get access to the framework? That's cool, Now let us help you install it to your awesome server!


### Server Setup
You might need to tweak a few things to get the best results from the framework, Old artifact versions and such may cause the framework to perform bad in certain areas. Make sure that you have checked all of these before moving on with the guide.

1. Make sure that your server is running on a updated version for either [linux](https://runtime.fivem.net/artifacts/fivem/build_proot_linux/master/) or [windows](https://runtime.fivem.net/artifacts/fivem/build_server_windows/master/).
2. Make sure that you are using `onesync legacy` in the **server.cfg**. As we are using OneSync Legacy technology, The framework is heavily dependant on this.

### Required Resources
To run our framework you will need a few things to make sure it will run as expected. Without these required dependencies certain functions may perform bad or not work at all.

- [mysql-async](https://github.com/brouznouf/fivem-mysql-async) (the *most* important resource by far, Communicates with your database)
- [eup-stream](https://forum.cfx.re/t/emergency-uniform-pack-client-server-sided-easy-install-update-5-0-announcement/97599) (The clothing for certain jobs such as police require this. **Recommended version is "V.3 (Update 3.6)"**.)

*These resources should be started before any framework resources as they should be loaded prior to the framework.*

### Server Configuration
Lets configure the **server.cfg** file, Add the following lines to the config. It is **important** that you set the `wosa.key` with your license key in order for the framework to properly boot up.

```
# Convars
set wosa.key "mykey" # required
set wosa.server "my server!" # not required
set wosa.discord "my discord" # not required
set wosa.website "my website" # not required
set wosa.discord_server_log "my webhook" # not required
set wosa.discord_report_log "my webhook" # not required

# required
ensure mysql-async
ensure eup-stream
ensure wosa_core
ensure wosa_jobs

# recommended but not required
ensure wosa_hud
ensure wosa_chat
```

### Download
Time to download all the required files to run the framework! Super easy, Just follow these steps!

1. You can either download the [latest](https://github.com/WosaFramework/releases) version or the [experimental](https://github.com/WosaFramework) version from our GitHub. *The experimental version might be unstable, broken or not working at all as it is the "test" version still under going heavy development.*
2. Import the `import.sql` file from the download and **import** it to your database, There are loads of tutorials on the internet if you are unsure how to do it.
3. Add all of the **wosa_** files to `/resources`, We strongly **recommend** you to create a sub folder within the `/resources` folder like this `/resources/[wosa]` to support our *ServerFFX* tool for example.

### Final
You server is ready for some roleplay, Thank you for supporting this project! **If you have are experiencing any issues we advise you to take a look at [troubleshooting](troubleshooting.md).**