# Troubleshooting
Having trouble starting your server? It wont you connect? Whoops, Dont panic, We are here to help you!

**Issue: When I start the server it just freezes and/or restarts by itself all the time.**  
Solution: This behavior indicates that the framework license key is not valid or already in use, Make sure that you got `wosa.key` set in the **server.cfg** or try to wait for about 1-5 minutes. A non-valid key will crash/freeze your server.

**Issue: The MySQL gives a ton of errors on startup.**  
Solution: If you are receiving heavy MySQL errors on startup you have most likley failed to setup your database or the mysql-async properly. To make sure you have not missed anything consider following this [guide](https://brouznouf.github.io/fivem-mysql-async/) regarding the setup of mysql-async.

**Issue: When I launch the server it says that the key is not valid.**  
Solution: This error indicates that you have not entered or entered the wrong "wosa.key" in the "server.cfg", Make sure that you did follow the installation guide.

**Issue: When I start my server it says that my key is already in use.**  
Solution: This means that the `wosa.key` you entered in your **server.cfg** is already marked as "in use" by our auth server. Only one server at time can use a specific key, If you require more for your community please contact support. If you did just close your server please wait up to 5 minutes for the auth service to re-sync. To avoid having to wait ~5 minutes you can use the command "quit" when closing the server or manually shut down the core with "stop wosa_core" before closing the terminal.

**Issue: The console says that MariaDB field xxx does not have a default value.**  
Solution: This *is* hopefully fixed in newer versions of wosa and should not occur but if it do occur please read [this](https://www.farbeyondcode.com/Solution-for-MariaDB-Field--xxx--doesn-t-have-a-default-value-5-2720.html) post.

**Issue: Cars in the server wont spawn and will just spam the F8 console / When I try to spawn a car from the garage I just get a black screen.**  
Solution: You need to use a up to date server and use `onesync legacy` in your **server.cfg** to enable server awareness as wosa is built on OneSync technology.

**If you did not find a solution on this page do not hesitate to contact support on our forums or in our discord.**