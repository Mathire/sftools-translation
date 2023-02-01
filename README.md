# How to translate SFTools

**NOTE: As of February 2023, SFTools translation has been completely moved to [CrowdIn](https://crowdin.com/project/sftools). If you want to contribute, there's a page on the Wiki with a short [tutorial](https://github.com/HafisCZ/sf-tools/wiki/Translation-Guide).**

___

This short tutorial will demonstrate how to effectively contribute to the translation for [SFTools](sftools.mar21.eu).

## Requirements

I recommend to install on your PC:
- [Notepad++](https://notepad-plus-plus.org/). Needed to actually translate;
- [Node.js](https://nodejs.org/en/). Needed to run a local server;
- [Git](https://git-scm.com/). I use this to keep my local github repo up to date;

Note: you can also just use notepad++, but without a local server you won't be able to test your contribution. Missing a comma or a bracket may "break" the tool.


## First steps

### Creation and cloning of your fork

To create a fork, go to [SFTools GitHub page](https://github.com/HafisCZ/sf-tools) and click on "create a new fork".

Choose a name for your fork and click on "create". 

Now it's time to clone it locally. To do that, go to a directory of your choice (eg. create a github folder inside the documents folder) and, from there, right-click -> 'git bash here', the git shell will open. 

Now type: 

```
git clone https://github.com/your_username/your_fork.git
```

A new folder containing your fork should be created.

### Adding origin and upstream links

To ease the process of updating and pushing commits, I prefer to do it via command line. To do that, the following commands must be ran in the git shell:

```
git remote add origin https://github.com/your_username/your_fork.git
git remote add upstream https://github.com/HafisCZ/sf-tools.git
```

And, to check if everything is working, type: 

```
git remote -v
```

Here's what it should look like:

![git remote-v](/res/git_remote-v.png)


## Translating

Open Notepad++ and install the plugin "Compare plus" in the "plugin" section. 

Note: after the installation is completed, I recommend to go to "plugin->compare plus" and check-off "auto re-compare on change".

Now you can start translating. Go to your sf-tools directory, and open:

- en.json;
- your_language.json.

Select your_language.json in Notepad++ and under "plugin->compare plus", click on "set as first to compare". 
Now select en.json and under "plugin->compare plus" click on "compare".

It will look like this:

![compare](/res/example_diffs.png)

Now you can start translating by copying the parts that are missing and changing the translation:

![compare](/res/example_after-paste.png)

### Testing

Once you finished, it's time to test. Save your files, close Notepad++ and go to sf-tools directory.
Open terminal there and use: 

```
http-server -c-1 -o
``` 

This will start a local server (-c-1 sets cache to 0 and -o open favourite browser).
Sftools site should load, now you can check your translations (ctrl + c in your terminal will stop the local server).

Note: if the site is broken, you probably missed / added some commas in your_language.json .

![http-server](/res/http-server_launch.png)

If everything works, you can commit changes.

## Commit and PR

In your sftools directory, open git bash and type:

```
git add .
git commit -m "commmit message"
git push origin
```

Now on your github page you should have your new commits. Make a PR from there. 
