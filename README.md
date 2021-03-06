gitfiti _noun_ : Carefully crafted graffiti in a github commit history calendar.  

An example of gitfiti in the wild:  
![alt text](https://raw.github.com/gelstudios/gitfiti/master/gitfiti-screenshot.png "screenshot")

`gitfiti.py` is a tool I wrote to decorate your github account's commit history calendar by (blatantly) abusing git's ability to accept commits _in the past_.

How?  `gitfiti.py` generates a bash script: `gitfiti.sh` that makes commits with the GIT_AUTHOR_DATE and GIT_COMMITTER_DATE environment variables set for each targeted pixel.

Since this is likely to clobber repo's history, I highly recommend that you create a _new_ github repo when using gitfiti. Also, the generated bash script assumes you are using public-key authentication with git.
  
  
###Pixel Art:
![alt text](https://raw.github.com/gelstudios/gitfiti/master/pixels-large.png "pixel art")  
Included "art" from left to right: kitty, oneup, oneup2, hackerschool, octocat, octocat2

###Usage:
1. Create a new github repo to store your handiwork.
2. Run `gitfiti.py` and follow the prompts for username, art selection, offset, and repo name.
3. Run the generated `gitfiti.sh` from your home directory (or any non-git tracked dir) and watch it go to work.
4. Wait... Seriously, you'll probably need to wait a day or two for the gitfiti to show in your commit graph.

### User Templates
The file format for personal templates is the following:

1. Each template starts off with a ":" and then a name (eg. ":foo")
2. Each line after that is part of a json-recognizable array.
3. The array contain values 0-4, 0 being blank and 4 being dark green.
4. To add multiple templates, just add another name tag as described in 1.

For example:

```
:center-blank
[[1,1,1,1,1,1,1],
[1,1,1,1,1,1,1],
[1,1,1,1,1,1,1],
[1,1,1,0,1,1,1],
[1,1,1,1,1,1,1],
[1,1,1,1,1,1,1],
[1,1,1,1,1,1,1]]
```

This would output a 7 x 7 light green square with a single blank center square.

Once you have a file with templates, enter its name when prompted and the templates will be added to the list of options.

###Removal:
Fortunately if you regret your gitfiti in the morning, removing it is fairly easy: delete the repo you created for your gitfiti (and wait).

---
####Todo:
- ~~Remove 'requests' dependency~~ [_thanks empathetic-alligator_](https://github.com/empathetic-alligator)
- Web interface
- ~~Load "art" from a file~~ [_thanks empathetic-alligator_](https://github.com/empathetic-alligator)
- Load commit content from a file
- ...
- Profit?
  
  
![alt text](http://f.cl.ly/items/0J463J0K1N020S1Q3E3l/er-small.png "tiny logo")
