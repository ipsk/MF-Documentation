# Change Log

**v2.0.1**

* Reworked the entire parser to use common mark for the additions like colors, instead of regex, which results in a good performance boost, plus removes the previous limitations.
* Colors and formats will carry through different nodes and even lines.
* Reworked the FormatOptions into MessageOptions and simplified it a bit.
* Added support for legacy formats \(`&l`, etc\).
* Added support for Kyori's Adventure.
* Separated project into modules, Bukkit and Adventure.
* Added `Format.ALL` and `Format.NONE`.
* Removed many unnecessary parts of Commonmark.
* Made possible to have ponctuation and spaces after opening and closing formats, for example: `** BOLD **`making it completely more true to Discord's syntax.
* Moved project to personal repository instead of Maven Central.
* Added WIP experimental `ReplaceableNode` to allow injecting custom text in the middle of a message.

