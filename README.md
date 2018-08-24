# bibtex files

Group BibTeX databases of references.

#### Usage:

Use the environment variable `BIBINPUTS` to set the path to your local machine where you cloned this repo. This way, the `\bibliography` command works for all group members (as no hard path is provided to the database files).

Sometimes, processing an article with LaTeX generates an additional `.bib` file in your working directory for footnotes that are added to the list of references (this happens with the RevTeX format). You then have to remember to copy that file over to your `BIBINPUTS` location (with the other BibTeX files), or your `\bibliography` won't find it, and you will get an error:

`I couldn't open database file <article name>.bib ... I'm skipping whatever remains of this command`
`I found no database files`

followed by a failure to create the bibliography. SIGH. This can stump you and make you waste a couple of hours before you realize it.

**Always copy any footnote file generated by LaTeX `article name.bib` into your BIBINPUTS location.**

#### Environment variables on Mac

Up to Lion (10.7), you can use the file `MacOSX/environment.plist`
To change its contents, open it with: 

`open ~/.MacOSX/environment.plist`

See the blog ["How to set an environment variable in Mac OS X"](http://www.dowdandassociates.com/blog/content/howto-set-an-environment-variable-in-mac-os-x-home-slash-dot-macosx-slash-environment-dot-plist/)

This does not work from 10.8 onwards, though. After Mountain Lion, you have to use `launched`
More details in [blog posts](http://www.dowdandassociates.com/blog/content/howto-set-an-environment-variable-in-mac-os-x-launchd-plist/) and [StackOverflow](http://stackoverflow.com/questions/135688/setting-environment-variables-in-os-x/3756686#3756686).

##### On Yosemite:
The answer is found on a [StackOverflow thread](http://stackoverflow.com/questions/25385934/setting-environment-variables-via-launchd-conf-no-longer-works-in-os-x-yosemite), like everything.

Launch `AppleScript Editor`, then enter a command like this:

`do shell script "launchctl setenv variablename value"`

(Use multiple lines if you want to set multiple variables)

Now save (⌘+s) as *File format: Application*. Click the Run button to get your variable set right now. (Restart any apps that you want to take this variable, like TeXShop.)

Finally, open System Settings → Users & Groups → Login Items and add your new application.
