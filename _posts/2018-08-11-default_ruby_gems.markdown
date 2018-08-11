---
layout: post
title:      "Default Ruby Gems"
date:       2018-08-11 13:04:21 -0400
permalink:  default_ruby_gems
---


Ruby comes with a set of 23 gems bundled with it (as of version 2.5.1). I decided that it would be a good idea to learn what they all do since they are all available by default in any Ruby project. In this post, I will describe what they all do, as well as provide links to each of their [RubyGems.org](https://rubygems.org/) pages.
 

### [bigdecimal](https://rubygems.org/gems/bigdecimal)
The big decimal gem provides "arbitrary-precision floating point decimal arithmetic". Ruby itself provides support for arbitrary precision integer arithmetic. BigDecimal provides a similar level of support for very accurate or very large floating point numbers. This arithmetic is useful because it provides the answer people expect, as opposed to normal binary floating point arithmetic, which can have errors.
### [cmath](https://rubygems.org/gems/cmath)
CMath provides "trigonometric and transcendental functions for complex numbers". It accepts integers, floating-point numbers, and complex numbers.
### [CSV](https://rubygems.org/gems/csv)
CSV provides an interface with CSV(comma-separated-values) files and data.
### [date](https://rubygems.org/gems/date)
Date provides a subclass Object that helps handle dates. Date objects are immutable and have various methods, such as year, mon which returns the month, and mday which provides the day of the month.
### [dbm](https://rubygems.org/gems/dbm)
dbm wraps the Database Manager Library. DBM databases are key-value data stores, similar to a Ruby hash. Keys and values must be strings.
### [etc](https://rubygems.org/gems/etc)
etc provides access to information stored in the `/etc` directory of a UNIX system. It allows you to access information in the `/etc/passwd` and `/etc/group` files as well as the `/tmp` directory.
### [fcntl](https://rubygems.org/gems/fcntl)
Fcntl loads constants defined in the systems fcntl.h C header file.
### [fiddle](https://rubygems.org/gems/fiddle)
Fiddle is a libffi wrapper for Ruby. libffi stands for Foreign Function Interface library. A foreign function is a name for an interface that allows code written in one language to call code written in a different language. libffi is described as a way to "build a bridge between interpreted and natively compiled code".
### [fileutils](https://rubygems.org/gems/fileutils)
FileUtils provides file utility methods, which provide functionalities such as copying, moving, and removing.
### [gdbm](https://rubygems.org/gems/gdbm)
GDBM is a Ruby extension for the GNU database manager. The GNU database manager is a library for simple databases consisting of key-value pairs. The database can be accessed by both reader and writer methods
### [io-console](https://rubygems.org/gems/io-console)
IO-Console "adds console capabilities to IO instances."
### [ipaddr](https://rubygems.org/gems/ipaddr)
IPAddr gives you methods to manipulate an IP address in both IPv4 and IPv6 versions. It provides methods such as IN6FORMAT, which formats a string as an IPv6 address, and regex methods to parse IPv4 and IPv6 addresses.
### [json](https://rubygems.org/gems/json)
json provides a JSON implementation written in C. It allows you to parse and generate JSON.
### [openssl](https://rubygems.org/gems/openssl)
openssl wraps the OpenSSL library and provides methods to create, export, and load OpenSSL keys.
### [psych](https://rubygems.org/gems/psych)
Psych is a "YAML parser and emitter". YAML is a data serialization language that is often used as a way to store configuration files. Psych wraps libyaml, which is a YAML parser and emitter library.
### [rdoc](https://rubygems.org/gems/rdoc)
RDoc "produces HTML and command-line documentation for Ruby project".  It provides various formatting and parsing methods.
### [rubygems-update](https://rubygems.org/gems/rubygems-update)
rubygems-update seems to be a way to update your other Ruby gems. Little information is available related to it.
### [scanf](https://rubygems.org/gems/scanf)
scanf is an implementation of the C function scanf, which has been modified to work with Ruby. Scanf scans an input according to a format and returns an array of matches. The format can also contain conversion specifiers which tell the function what type each particular matched substring should be converted to.
### [sdbm](https://rubygems.org/gems/sdbm)
SDBM provides a key-value store. The keys and values must be strings. It provides methods for bulk updates and value retrievals.
### [stringio](https://stdgems.org/stringio/)
StringIO makes a string look like an IO object. The object has read/write methods.
### [strscan](https://stdgems.org/strscan/)
strscan allows for "lexical string scanning". Lexical analysis is defined by Wikipedia as "the process of converting a sequence of characters into a sequence of tokens (strings with an assigned and thus identified meaning)".
### [webrick](https://rubygems.org/gems/webrick)
WEBrick is a toolkit or HTTP and HTTPS servers, and can also be configured as a proxy server or virtual-host server.
### [zlib](https://rubygems.org/gems/zlib)
zlib provides support for the zlib compression and decompression library. zlib, the first version of which was first released in 1995, uses an abstraction of the DEFLATE lossless compression algorithm.
