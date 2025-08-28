# Finally

As projects get bigger and more complex, so too does the complexity of the underlying modules and packages. In the examples covered here, I created a single package with multiple module files, all of which were trivial.&#x20;

In a large project I might have a package called networking. Under that I might have a separate package for dealing with all things TCP. I might have another separate package for dealing with all things UDP. And just for good measure, multicast we'll also have its own package. Very quickly we end up with a nested directory tree of packages, all of which can be called relative to the root directory the application is in.&#x20;

In your spare time, play with this concept, but you do need to implement it in any projects for this module.
