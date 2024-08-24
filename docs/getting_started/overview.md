# Overview

The Open Pattern Format consists of three closely related specifications each with their own file type:

 * **Pattern** - `.opaf` files store the pattern source and will generally not be distributed by the designer in their raw form. A pattern in `.opaf` format requires packaging before it can be distributed.

 * **Package** - `.opafpkg` files are packaged, self-contained patterns which can be distributed by the designer. These files can be used to generate projects.

 * **Project** - `.opafproj` files are generated from packaged pattern files based on individual user configuration. An `.opafproj` file can be used with any compatible reader and is stand-alone so does not depend on the original pattern file. Project tracking is also integral.