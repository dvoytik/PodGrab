FAQ
===

How to download whole RSS podcast?
---------------------------------

```bash
python3 ./PodGrab.py -d http://cool-podcast.com/rss.xml
````


PODGRAB
=======

A Python command line audio/video podcast downloader for RSS XML feeds.
Supported RSS item file types: MP3, M4V, OGG, FLV, MP4, MPG/MPEG, WMA, WMV, WEBM

Author: Jonathan Baker jon@the-node.org (http://the-node.org)

For a full description and discussion, please see http://joshua14.homelinux.org/blog/?p=492

Do with this code what you will, it's "open source". As a courtesy,
I would appreciate credit if you base your code on mine. If you find
a bug or think the code sucks balls, please let me know :-) 

Outstanding issues:-
 - Video podcasts which which are not direct URLs and are modified by PodGrab
   in order to be grabbed won't display their size as the filenames haven't 
   been stripped of their garbage URL info yet. It'll say 0 bytes, but don't 
   worry, they've downloaded. 

==== CHANGES MADE AFTER FORK ====

Author: Werner Avenant werner.avenant@gmail.com (http://www.collectiveminds.co.za)

Changes after fork:

    - Added support for M3U files listing all files downloaded that day    
    - Last Episode Detection wasn't always right. It wasn't noticable
      because if the file existed it wouldn't download the episode. Rewrote
      last_ep logic
    - Changed write_podcast to return if a file existed. This in turn
      updates the "last_ep" in the database
    - Refactored/cleaned up iterate_channel
    - Function update_subscription will check to see if the last_ep is older
      than the existing last_ep
    - Moved NUM_MAX_DOWNLOAD to the front of the file for easy configuration
