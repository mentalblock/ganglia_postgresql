## PostgreSQL

**This software does not work properly. This is a work in progress.**

This is the Ganglia python module for PostgreSQL. It executes queries against
the database to gather metrics for display in Ganglia.

Various other Ganglia python modules were used as a reference for this work.

More information on Ganglia python modules can be found [here](http://sourceforge.net/apps/trac/ganglia/wiki/ganglia_gmond_python_modules).

## Requirements
* The [psycopg2](http://www.initd.org/psycopg/) library. This is a PostgreSQL
  adapter for Python. Your OS distribution may have a package available which
  provides this adapter.

## Installation
* Copy `postgresql.pyconf` to `/etc/ganglia/conf.d/`. 
* Copy `postgresql.py` to `/usr/lib64/ganglia/python_modules`
* Configure the module.
* Restart the gmond service.

## Configuration

As with other Ganglia python modules, configuration is managed through the
pyconf `postgresql.pyconf`.

## Adding custom metrics

In order to add metrics in addition to those already included, it is required
that the *metrics_defs* dictionary be modified in the module script
`postgresql.py`. This dictionary is where all the queries are defined and one
can use the included queries as a guideline for creating additional metrics. 

## Bugs

* It is not yet clear which included metrics need to be GAUGE or COUNTER. This
  will be improved upon as they are discovered.
* This module was not thoroughly tested. More testing is in progress.

[Found a bug?](http://github.com/bwong114/ganglia_postgresql/issues).

## Debugging

As with most Ganglia python modules, you can execute `postgresql.py` from the
command-line. Execute `postgresql.py -h` for help. The command-line invocation
is very close to how gmond will utilize the module.

## Contact

* Mail

  bwong114 [at] gmail.com
