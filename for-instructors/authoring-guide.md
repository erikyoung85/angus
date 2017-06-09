# Authoring guide

## Technical info re adding content to the Web site

All the ANGUS 2017 tutorials are stored on GitHub: [https://github.com/ngs-docs/angus](https://github.com/ngs-docs/angus).

We will use [GitHub Flow](https://guides.github.com/introduction/flow/) for updates: from the command line,

* fork a new branch off of `2017` within the `ngs-docs/angus repository`;
* edit, change, add, etc;
* submit a PR against 2017;
* when ready to review & merge say 'ready for review & merge @angus2017'.

It's important that all updates go through code review by
someone. Anyone with push access to the repo can review and merge!

From the Web site, you should be able to edit the files and then set up a
PR directly.

### Updating the "official" Web site.

The Web site, http://angus.readthedocs.io/, will update automatically
from GitHub.  However, it may take 5-15 minutes to do so.

### Building a local copy of the Web site.

Briefly,

* Clone the repo:

  `git clone https://github.com/ngs-docs/angus.git`

* set up a virtualenv with python2 or python3;

  `python -m virtualenv buildenv -p python3.5; . ~/buildenv/bin/activate`
  
* install the prerequisites:

  `pip install -r requirements.txt`
  
* build site: `make`

* open / click on `html/index.html`

## Formatting, guidelines, etc.

Everything can/should be in
[Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)!
If you're not super familiar with Markdown, you can use
[hackmd](https://hackmd.io/) to write your tutorials (use `+ New guest
note`) - it will show you a live preview of your Markdown code.

If you create a file named `mytut.md` it will automatically be compiled into
`mytut.html`.

(Note that you can go visit the github repo and it will helpfully render
`.md` files for you if you click on them! They just won't have the full
site template.)

Files and images that don't need to be "compiled" and should just be
served up by through the web site can be put in the `_static`
directory; their URL will then be

    `https://angus.readthedocs.io/en/2017/_static/filename`

## Medium-size data file storage

We can put files up to a total of 5 GB on our [Open Science Foundation project](https://osf.io/pyvfg/).  (For bigger data sets, talk to Titus about
where to put them. :)  You can use a Web interface to upload them.

These files should then be downloaded in the tutorials using a `curl` command
like so: `curl -L -o filename.out https://osf.io/bya2u/?action=download`.

To get the file ID (the `bya2u` in the command above), go there and
upload them using the nice Web interface, and then click on the file; the
file ID is in your URL bar.