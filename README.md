# Sugar Activities

This contains all the data for ASLO activities

# Adding yours

First create a new file for your activity.  It should be named `BUNDLE_ID.json` (for example: `com.example.activity.json`).  Then add the following contents:

    {
        "by": [
                {
                    "name": "YOUR_NAME", 
                    "page": "YOUR_SITE"
                }
            ]
    }

Then send us a pull request. Someone will look at your activity.

**NOTE:** It is a good idea to use [a json checker](http://jsonlint.com/) before you commit.

# Hooking it up

You should then add a github web hook for your activity.
That means the bots will build and do stuff for you.
They build from master, but don't worry about different branches for stable and
testing; the bots automatically see when you change the version number.
The webhook address is:

    https://aslo-bot-master.sugarlabs.org/hook

Use the webhook for `only push events`. That is the default option.

# Manual Release

If using a GitHub webhook does not suit your workflow, you can choose when the bots build your activity.

1.  Push the changes you want the bots to include to your github repo
2.  Send a http request to `https://aslo-bot-master.sugarlabs.org/hook/GITHUB_NAME/GITHUB_REPO` (replacing the name and repo values).  You can do this in your browser, using `http` or `curl`.
3.  Success!

# Getting ready for the bots

* Make sure you have a setup.py
* Put your screenshots in `/screenshots/LANG/`. eg: `/screenshots/en/1.png`
* Add summary and title to activity.info
* Translate activity.info (if you can) using po files
* Add the `categories` to your `activity.info`
  Tags are space seperated and are: `game`, `programming`, `robotics`, `internet`, `science`, `maths`, `langauge`, `geography`, `documents`, `music`, `media`, `art`, `teacher` and `system`.

See an example of adding tags & screenshots to an activity in [the Typing Turtle activity](https://github.com/godiard/typing-turtle-activity/commit/08b381a34ff96e20fb72aa7a52441cc1aae0c757)

# See it live

First do a push, and after one of the bots has compiled your activity, go to https://activities-2.sugarlabs.org/!
