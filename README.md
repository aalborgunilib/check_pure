# check_pure
Nagios (and compatibles) plugin to check the health of Elsevier Pure CRIS (https://www.elsevier.com/solutions/pure).

## About
This plugin will check the internal surveillance URL of Pure that will report the status of the system.

## Installation
Copy the check_pure file to your Nagios plugins directory, e.g.:

    git clone https://github.com/aalborgunilib/check_pure
    cd check_pure
    sudo cp plugins/check_pure /usr/lib64/nagios/plugins/
    sudo chmod 755 /usr/lib64/nagios/plugins/check_pure

Install Perl dependencies for the plugin via e.g. [cpanm](https://metacpan.org/pod/App::cpanminus). (Please stay within the check_pure directory):

    cpanm --sudo --installdeps .

*Compilation of the Perl dependencies might require the installation of software development tools on the server (gcc).*

## Usage

    Usage: check_pure
        [ -H|--hostname=<Hostname of the Pure administrative interface> ]
        [ -s|--ssl ]
        [ -t|--timeout=<timeout> ]


`-H|--hostname` is the hostname of the Pure administrative interface (probably the one you append /admin to).

`-s|--ssl` is needed if you use https to connect to the administrative interface.

`-t|--timeout` is the plugin timeout. If timeout is reached, the check will bail out and issue an UNKNOWN state.

In case of warnings and critical issues the plugin will try to get the issue description from the surveillance status.

According to the Pure wiki, the check currently includes:

  * Basic read access to the database
  * Search via the free-text search index
  * Free disk space in the serverDataDir

## Copyright and license

Copyright (c) 2016 Kasper Løvschall and Aalborg University Library

This software is free software; you can redistribute it and/or modify it under the same terms as Perl itself. See [Perl Licensing](http://dev.perl.org/licenses/).
