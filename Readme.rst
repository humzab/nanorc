***************************************
Improved Nano Syntax Highlighting Files
***************************************

This repository holds ``{lang}.nanorc`` files that have improved
definitions of syntax highlighting for various languages.


1. Copy files
~~~~~~

These should be placed inside of the ``~/.nano/`` directory. 
Or for system-wide installation ``/usr/share/nano-syntax-highlighting/``.
In other words::

    git clone git@github.com:humzab/nanorc.git ~/.nano

*Note - if you have any issues (ssh was not properly configured), alternatively use::

    git clone https://github.com/humzab/nanorc.git ~/.nano
    
*System wide will look like so*::

    sudo git clone https://github.com/humzab/nanorc.git /usr/share/nano-syntax-highlighting/


2. Configure ``nano``
~~~~~~~~~

Once there you should add the languages you want to your
nano configuration file ``~/.nanorc``.  For example::

    ## C/C++
    include "~/.nano/c.nanorc"

You can also append the contents of ``~/.nano/nanorc`` into your
``~/.nanorc`` to include all languages::

    cat ~/.nano/nanorc >> ~/.nanorc
    
Or to be less verbose, append content of the folder in one line with wildcard::

    ## For all users
    $ echo "include $install_path/*.nanorc" >> /etc/nanorc 
    ## For current user
    $ echo "include $install_path/*.nanorc" >> ~/.nanorc
    
where ``$install_path`` is ``/usr/share/nano-syntax-highlighting`` or ``~/.nano/`` or ...

1a.  Automatic installer
~~~~~~~~~~~~~~~~~~~~~~
Finally, you can run an automatic installer using the following code::

    $ curl https://raw.githubusercontent.com/humzab/nanorc/master/install.sh | sh

or alternatively::

    $ wget https://raw.githubusercontent.com/humzab/nanorc/master/install.sh -O- | sh

*Note -
    some syntax definitions which exist in Nano upstream may be preferable to the ones provided by this package.
    The install.sh script may be run with ``-l`` or ``--lite`` to insert the included syntax definitions from this package
    with lower precedence than the ones provided by the standard package.
    
    
1b. Distributive specific installation via package managers
~~~~~~~~~~
On **Arch Linux** and other *pacman/aur* based systems it is possible to::

    $ yaourt nano-syntax-highlight

Then you need to mannually add ``.nanorc``-s to user's ``~/.nanorc`` or system ``/etc/nanorc``. See **$2**
