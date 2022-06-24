# Nginx Basic commands

Reference the following list of popular commands if you ever need a quick reminder on how to use a certain command or what it does.&#x20;

**Remember, if you aren’t a root user, you’ll need to `sudo` each command in order for them to properly work.**

#### Start Nginx <a href="#start-nginx" id="start-nginx"></a>

Starting Nginx is very simple. Just use the following command:

```
service nginx start
```

If you’re using a systemd based version such as Ubuntu Linux 16.04 LTS and above, use `systemctl`within the command, like so:

```
systemctl start nginx
```

**Example response:**

```
Starting nginx server...
```

#### Stop Nginx <a href="#stop-nginx" id="stop-nginx"></a>

Stopping Nginx will kill all system processes quickly. This will terminate Nginx even if there are open connections. In order to do so, run one of the following commands:

```
service nginx stop
systemctl stop nginx
```

**Example response:**

```
Stopping nginx Server...
```

This command can still, however, take some time on busy servers. Therefore, if you want Nginx to stop even faster, you can also use:

```
killall -9 nginx
```

#### Quit Nginx <a href="#quit-nginx" id="quit-nginx"></a>

Quitting Nginx is very similar to stopping it however it does so gracefully which means it will finish serving open connections before shutting down. To quit Nginx, use one of the following commands:

```
service nginx quit
systemctl quit nginx
```

#### Restart Nginx <a href="#restart-nginx" id="restart-nginx"></a>

Restarting Nginx basically performs a stop then a start. Use one of the following commands to run a Nginx restart:

```
service nginx restart
systemctl restart nginx
```

**Example response:**

```
Stopping nginx Server... [ OK ]
Starting nginx Server... [ OK ]
```

#### Reload Nginx <a href="#reload-nginx" id="reload-nginx"></a>

Reload is a bit different from restart in that, again, it is more gracefully. According to Nginx, reload is defined as “start the new worker process with a new configuration, gracefully shut down old worker processes.”. You can reload Nginx by using one of the following commands:

```
service nginx reload
systemctl reload nginx
```

**Example response:**

```
Reloading nginx Server... [ OK ]
```

#### View Server Status <a href="#view-server-status" id="view-server-status"></a>

Check what the current status of your Nginx web server is with one of the following commands:

```
service nginx status
systemctl status nginx
```

**Example response:**

```
nginx is running
```

#### Test Nginx Configuration <a href="#test-nginx-configuration" id="test-nginx-configuration"></a>

You can test your Nginx server’s configuration file before restarting or reloading it completely. This helps prevent any unforeseen errors which can cause your website to gown down. To do this there are two separate commands you can use, both return the same information:

```
nginx -t
```

Or use one of the following:

```
service nginx configtest
systemctl config nginx
```

**Example response:**

```
nginx: the configuration file /etc/nginx-sp/nginx.conf syntax is ok
nginx: configuration file /etc/nginx-sp/nginx.conf test is successful
```

#### Check Nginx Version <a href="#check-nginx-version" id="check-nginx-version"></a>

There are also two different ways to check your Nginx version. Both are fairly similar but one shows a little more information than the other. Use one of the following Nginx commands to print the Nginx version:

```
service nginx -v
systemctl -v nginx
```

Use the following command to print the Nginx version, compiler version and configure parameters.

```
service nginx -V
systemctl -V nginx
```

#### Show Command Help <a href="#show-command-help" id="show-command-help"></a>

If you’d like a quick reference guide of the commands available directly from within the terminal, use one of the following help commands:

```
service nginx -h
systemctl -h nginx
```

Or:

```
service nginx -?
systemctl -? nginx
```

### &#x20; <a href="#summary" id="summary"></a>
