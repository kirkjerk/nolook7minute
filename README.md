No-Look 7 Minute Workout Page
=============================

After use of [7MIN] with a group at work to do [The Scientific 7-Minute Workout], I noticed some improvements that could be made to the genre:

  - people were reading the next exercise out loud for their peers
  - when you're on the floor, you can't see the countdown end. Sometimes folks were reading off a "3, 2, 1" at the end for their peers
  - similarly, it's often nice to know the halfway point when gutting out a tough exercise

I decided to roll my own version, using a pre-recorded voice to provide more information rich announcements. It's an easy kind of app to make, so I decided to keep html, css, and script all in a single page.

You can simply use the result at the [No-look 7-minute @ alienbill.com page], or use the files here to build and publish your own.

Implementation Details
----------------------
The page relies on jQuery.

The program sets a large amount of timers when it fires up. Each timer changes some aspect of the page and/or plays a sound.

The page uses the [lowLag] library for playing sounds. A local version is included in this repository.

The voice was generated using OSX's "say" command and the "Veena" voice... e.g. 

    say -v "Veena" "good job" -o goodjob.aiff

those files were then converted via LAME

    lame goodjob.aiff --preset medium goodjob.mp3

The miscellaneous other side effects were from various free sources.

If you run this locally, you probably cannot run it directly from the filesystem and will need to use some kind of web server. If your system has python, the command

    python -m SimpleHTTPServer 8081

will server the current folder at http://localhost:8081/


Future Improvements
-------------------
  - It is likely a bit inefficient to be setting so many timers. A memory structure could be made allowing a single interval timer to do the work, but this seems to work pretty well.
  - My coworkers think there should be a music soundtrack. V2!

Let me know if you find this useful, and remember to push when you do your exercises to get the most out of your 7 minutes!  

[7MIN]:http://www.7-min.com/
[The Scientific 7-Minute Workout]:http://well.blogs.nytimes.com/2013/05/09/the-scientific-7-minute-workout/
[lowLag]:http://lowlag.alienbill.com
[No-look 7-minute @ alienbill.com page]:http://7minute.alienbill.com/
