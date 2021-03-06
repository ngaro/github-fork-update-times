This displays a sorted list of a repository's forks' updated times.

It caches the pages to reduce github API hits.

## Features
* Caches the pages (initial repository page and the json forks)

## Setup
* You'll likely need to set up an auth token -- see the top of the script for info and a URL.
* For now, I hardcode the URL of the repository of desirability into the script -- see the few variables in the script for that. Sorry.

### Reliability
* I didn't use the API for the initial page hit (for the forked projects info). (I didn't know about it).
* Instead I just parse the raw HTML.
* Using the API and the JSON data to get the forks would be preferable and more future-compatible -- also less error-prone since I'm relying on potentially-changing HTML.

### Other
* Aside from the stuff in Setup, deleting cache must be done by hand.
  * Like when your hit/API limit is exceeded and the last file gets messed up content, you'll have to remove it by hand. It should output the full path so it's easy to remove, but still.
* This is in perl
* I'm not using perl's HTTP modules -- I'm calling curl directly. Sorry.
* I'm not using perl's JSON parsing modules -- just regex's. :)
* This uses forward slashes for local file paths
* Also, it uses /tmp/
* Probably not necessary to mention, but in some places I separate the github username from the repo with double underscore (__). This leaves the very-unlikely possibility of a name collision, but I'm mentioning it to be complete.


