### Custom Nginx configuration & embedding Qordoba

Tweaking the Nginx configuration is an essential part of setting up your Qordoba  
instances since it allows you to optimize its performance for your  
infrastructure, or embed Qordoba in an already running OpenResty instance.

#### Custom Nginx configuration

Qordoba can be started, reloaded and restarted with an `--nginx-conf` argument,  
which must specify an Nginx configuration template. Such a template uses the  
[Penlight][Penlight] [templating engine][pl.template], which is compiled using  
the given Qordoba configuration, before being dumped in your Qordoba prefix  
directory, moments before starting Nginx.

The default template can be found at:  
https://github.com/Mashape/qordoba/tree/master/qordoba/templates. It is split in two  
Nginx configuration files: `nginx.lua` and `nginx_qordoba.lua`. The former is  
minimalistic and includes the latter, which contains everything Qordoba requires  
to run. When `qordoba start` runs, right before starting Nginx, it copies these  
two files into the prefix directory, which looks like so


##Option 2: Connecting over command line

Without a configuration file, you must enter option-value pairs for authentication on the command line.

1. Under your settings in your Qordoba projects click the CLI Config tab. 
2. On your host computer command line, `cd` to your project directory and enter command options plus authentication pairs.

## Next Steps

Now that you've added your API to Qordoba, let's learn how to enable plugins.

Go to [Enabling Plugins &rsaquo;][cli-configuration]/docs/{{page.qordoba_version}}/qordoba-cli/cli-configuration


# Authenticating - Config.yml

Connecting to a Qordoba project from your localhost needs authentication.   
**Organization ID**, **Project ID**, and **Account Token** (Required)

##Option 1: Connecting via config.yml - *recommended*

The configuration file saves you from re-entering your option-value pairs on the command line.

**Step 1: download** your configuration file located in your project settings. The file contains your --organization-id, project-id and --access-token. 

**Step 2: move** your downloaded configuration file and optionally set an environment variable.
