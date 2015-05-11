The rjson package implements a backwardly compatible version of JSON with
the aim of making it easier for humans to read and write. There is also an rjson
command (in cmd/rjson) that reads and writes this format.

The data model is exactly that of JSON's and this package implements all
the marshalling and unmarshalling operations supported by the standard
library's json package.

The three principal differences are:

- Quotes may be omitted for some object key values (see below).

- Commas are automatically inserted when a newline
is encountered after a value (but not an object key).

- Commas are optional at the end of an array or object.

The quotes around an object key may be omitted if the key matches the
following regular expression:

	[a-zA-Z][a-zA-Z0-9\-_]*

This rule may be relaxed in the future to allow unicode characters,
probably following the same rules as Go's identifiers, and probably a
few more non-alphabetical characters.
