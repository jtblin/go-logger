# go-logger

The only goal of this library is to provide a standard interface that can be used by library owners
to allow passing a logger to their library.

# Rationale

Quote from [Why log.Logger is not an interface](http://nodir.io/post/132312948446/logger)

> In traditional programming languages, such as Java, the stdlib defines canonical interfaces that others can 
implement. Go stdlib does that too (...)

This is where I stop agreeing with the author of this post. Unfortunately Go creators didn't deem necessary to do 
this for logger, so it is impossible for library owners to allow passing a logger as a parameter to a 
library `struct` or function.

For example you could use [logrus](https://github.com/Sirupsen/logrus) in your project, set it up to
output JSON or to use one of the supported hooks but when using a library that needs to log some output
you would suddenly be at the mercy of the library creator logger choice.

See [I wish Logger was an interface](http://comments.gmane.org/gmane.comp.lang.go.general/121533) and this
[reddit thread](https://www.reddit.com/r/golang/comments/3r919w/why_loglogger_is_not_an_interface/) for 
reasons why the standard lib should provide a `Logger` interface.

# Usage

Simply accept `logger.Interface` in your function or struct, and use one of the standard logger functions
e.g. `Println`, `Fatalf`, `Panic`, etc.

# Support

The interface is compatible with the standard logging libraries:

* stdlib `log`
* [logrus](https://github.com/Sirupsen/logrus)
* tbc

# Author

Jerome Touffe-Blin, [@jtblin](https://twitter.com/jtblin), [About me](http://about.me/jtblin)

# License

go-logger is copyright 2015 Jerome Touffe-Blin and contributors. 
It is licensed under the BSD license. See the include LICENSE file for details.
