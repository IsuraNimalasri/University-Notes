University-Notes
================

Notes from various courses at the University of Waterloo. Written by Anthony Zhang.

# [VIEW NOTES](http://anthony-zhang.me/University-Notes/)

About
-----

I write these during lectures, and then add to them occasionally when mistakes or omissions are discovered.

They're written in Markdown with LaTeX for math. There's a build script that uses [Pandoc](http://johnmacfarlane.net/pandoc/) to generate HTML with [KaTeX](https://khan.github.io/KaTeX/) for math rendering.

Deployment
----------

To compile, run `make` in the top-level directory.

I then push the resulting files to GitHub, where they're hosted using GitHub Pages.

To compile KaTeX, I use [Docker](https://www.docker.com/):

    git clone --depth 1 https://github.com/Khan/KaTeX.git
    sudo docker run --volume "$(pwd)/KaTeX:/files" --interactive --tty pritunl/archlinux:latest /bin/bash

    # run inside Docker image
    pacman -S make nodejs zip
    cd /files
    make
    exit

    # the output folder with all the files is now in KaTeX/build/katex

License
-------

Copyright 2013-2017 Anthony Zhang

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/deed.en_US"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by-nc-sa/3.0/88x31.png" /></a><br />The works in this project are licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/deed.en_US">Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported License</a>.

In other words, you are free to modify the work - provided you also release those modifications under the same license - and use it as you like, as long as it isn't commercial.
