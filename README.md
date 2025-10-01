# Dyskinesia

My sway window manager config, tuned for my Parkinson's, heavily "why" commented, unusual features.

2025-10-01 Sorry about the 6 month of inactivity on github. Life. I need to get everything shipshape again. I will once again just dump everything current on here over a few days with no explanation of the history. I get the impression no-one uses it as-is anywwy, but uses it as a resource for ideas and code to go into their stuff. I prefer it that way given the impact of the PD on my abilities.

2025-04-13 Over the last week I have been populating github slowly starting with the config file itself. It needed some scripts and some assets bringing over. There is now enough for someone familiar with sway to replicate my configuration, In the next week I expect to git clone this repo, check everything is in place, fix some details, and then baseline and release.

2025-04-15 This is my first use of git on Fedora so I've had to configure it properly.

My .gitignore arrangement puts Emacs rules in ~/.config/git/ignore for all git repos, you should probably do similarly for your text editor, because the file is not part of this repo.

The file Dyskinesia/.git/info/exclude is not distributed, it effectively a list of things YOU need that I don't supply directly; instead you get instructions to recreate them in this README. These are the files:

assets.d/swaybg1.jpg
assets.d/swaybg2.jpg
assets.d/swaybg3.jpg
scripts.d/autotiling

1) cd into assets.d and make 3 copies of le09600.jpg and rename them swaybg{1,2,3}

Use ImageMagick suite's app "mogrify" to crop each copy in-place, effectively cutting the 5760x1080 image le09600 into three parts, left,centre,right

     mogrify --geometry 1920x1080+0+0    swaybg1.jpg

     mogrify --geometry 1920x1080+1920+0 swaybg2.jpg

     mogrify --geometry 1920x1080+3840+0 swaybg3.jpg

2) scripts.d/autotiling is the executable from https://github.com/nwg-piotr/autotiling installed on my fedora (it may be packaged for your distro, there's a list of packages on the autotiling repo, else use these instructions from said repo reproduced below:

Installing manually:

    Install the python-i3ipc>=2.0.1 package (or whatever it's called in your Linux distribution);
    
    save the main.py file anywhere, rename to autotiling, make executable, move to your bin folder;
    
    add exec_always autotiling to the ~/.config/sway/config or exec_always --no-startup-id autotiling to the ~/.config/i3/config file.

