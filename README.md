pgx
===

Experimental PostgreSQL client library for Go

Usage
=====

TODO

Development
===========

ERB Templating
--------------

Sometimes Go code can be repetitive especially with dealing with functions that only differ in the type (e.g. ReadInt16, ReadInt32, ReadInt64). Some of this repetition can be eliminated by using a template preprocessor. pgx uses Ruby erb templates. Files that end in .go.erb are used to produce the corresponding .go files. These files can be automatically processed with guard -- a Ruby file and directory watcher.

Prerequisites:

* Ruby
* guard
* guard-tilt

To automatically process .go.erb files open a shell in the pgx directory and run:

    jack@hk-47~/dev/pgx$ guard

Testing
-------

To setup the test environment run the test_setup.sql script as a user that can
create users and databases. To successfully run the connection tests for various
means of authentication you must include the following in your pg_hba.conf.

    local  pgx_test  pgx_none  trust
    local  pgx_test  pgx_pw    password
    local  pgx_test  pgx_md5   md5


