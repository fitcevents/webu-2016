**Distributing UI Libraries in a Post-Web-Component World**
-----------------------------------------------------------
*With Rachel Moore*

So you’ve decided to build your product by reusing code. This has practice challenges. The first problem of shared code is dependencies, ideally there should be an automatic way to get all dependencies at once. In the past we've either copied-pasted or manually downloaded files from jQuery and Bootstrap. The second problem is theme styles located in different places in the code base unnecessarily coupling the different dependencies. This leads to having to include more and more code bases in order to achieve the needed functionality, causing code bloat. In addition, A GUI component should have a single custom element interface so the user doesn’t have to copy and paste markup into their files. A component should leverage a package manager to handle component dependencies. 

Keep in mind that package managers can have bugs, version conflicts and other complications however. The packages should follow semantic versioning ([semver](http://semver.org/)), allowing you easily know if installing the updated component will break your build. For semver version X.Y.Z, X is a major breaking change, Y is a minor non-breaking (backward compatible) change, and Z are patches. A major change signals that you will need to update your own app code. Ideally the package manager will also manage version conflicts, downloading supported dependency versions only. NPM and Bower diverge on how this is handled. With NPM we download multiple versions of a package when requested and simply nest them in the package folder, while Bower requires you to manually manage conflicts. This is by design, since Bower was a more front-end focus and the front end has a single global namespace making multiple versions problematic.

**Create your own package**

If you have a public github repo with the required manifest files you can include then as NPM packages. You can also setup private packages. The best way to do that is to set up a private registry, which is how your package will be located. 

