# check_pure
Nagios (and compatibles) plugin to check the health of Elsevier Pure CRIS.

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

## Copyright and license

Copyright (c) 2015 Kasper LÃ¸vschall and Aalborg University Library

This software is free software; you can redistribute it and/or modify it under the same terms as Perl itself. See [Perl Licensing](http://dev.perl.org/licenses/).
