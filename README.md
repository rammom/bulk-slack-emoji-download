# Download all slack emojis from your workspace

I made this project because I'm always joining slack workspaces with loads of emojis, but could never figure out
where they get them all!  I wanted them for my own workspaces so hopefully this will help you as
much as it's helped me.

## Getting Started
There's a little bit of a setup for my scripts to work properly, if anything is ambiguous feel free
to let me know via email *mr.rammo@gmail.com* with a subject **slack emojis**

First step is of course to **clone this repo into a directory of your choice.**

## Prerequisites
For this to work you're going to need python3 installed on your system, you can download it [here](https://www.python.org/downloads/).
After that, we need to install a few dependencies from pip.

Run the command below in a bash shell and you'll be all set!
```
pip3 install requests bs4 simplejson
```


## Cookie Thieving
First thing we need to do is manually log into our slack workspace, modify and visit the following link.

```
https://<Your Workspace>.slack.com/customize/emoji
```

That should take you to a slack login screen.  At this point you want to open up your browser's dev tools and
navigate to the network tab.

Log in.

**NOTE: This will not work it you are already logged in, we're looking for the actual authentication here**

After reaching the **Customize Your Workspace** page you should see multiple rest calls under the network tab,
the one we're interested in has a name similar to 
```
checkcookie?redir=...
```
(If you're using chrome you can filter by 'other', this will make the specific call easier to find).

Click on the call and scroll to the **Request Header** section.

We're going to need the cookie so go ahead and copy that value.  You'll need to keep your browser open for the
remaining of the process, so if you close it you may need to start from the beggining.

## Tweaking the Config
I've already created a config.json file, all you need to do is fill in the blank values.  Start by pasting the
cookie value we copied in the last step into the **cookie** field.

Then go ahead and enter the name of your workspace in the **slack-workspace** field.

No need to worry about the outFile.

## The Easy Part
All we need to do now is open up a bash shell if you haven't already, navigate to wherever you cloned this repo
and run:
```
./exec.sh
```





