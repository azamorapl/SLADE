The `archives` scripting namespace contains functions for managing archives.

## Functions

### `all`

**Returns** <type>[Archive](../Types/Archive.md)\[\]</type>

Returns an array of all currently open archives.

---
### `openFile`

<params>Parameters</params>

* <type>string</type> <arg>path</arg>: The full path + name of the archive file to open

**Returns** <type>[Archive](../Types/Archive.md)</type>

Attempts to open the file at <arg>path</arg> on disk. Returns the archive if it opened successfully, or `nil` if it could not be opened.

If opening fails, the error that occurred should be available via <code>[slade.globalError](SLADE.md#globalerror)()</code>.

---
### `close` <sup>(1)</sup>

<params>Parameters</params>

* <type>[Archive](../Types/Archive.md)</type> <arg>archive</arg>: The archive to close

**Returns** <type>boolean</type>

Closes the given <arg>archive</arg>. Returns `false` if <arg>archive</arg> is invalid or not currently open.

---
### `close` <sup>(2)</sup>

<params>Parameters</params>

* <type>number</type> <arg>index</arg>: The index of the archive to close

**Returns** <type>boolean</type>

Closes the archive at <arg>index</arg> in the list of currently open archives (see <code>[all](#all)</code>). Returns `false` if the given <arg>index</arg> is invalid.

---
### `closeAll`

Closes all currently open archives.

---
### `fileExtensionsString`

**Returns** <type>string</type>

Returns a string with the extension filter for all supported archive file types.

See <code>[slade.browseFile](SLADE.md#browsefile)</code> and the [Open Archive](../Examples/OpenArchive.md) example for more information.

---
### `baseResource`

**Returns** <type>[Archive](../Types/Archive.md)</type>

Returns the currently loaded base resource archive.

---
### `baseResourcePaths`

**Returns** <type>string[]</type>

Returns an array of configured base resource archive file paths.

!!! note "TODO"
    Needs a better description

---
### `openBaseResource`

<params>Parameters</params>

* <type>number</type> <arg>index</arg>: The base resource path index to open

**Returns** <type>boolean</type>

Opens the base resource archive from the path at <arg>index</arg> in the list of base resource archive file paths (see <code>[baseResourcePaths](#baseresourcepaths)</code>).

!!! note "TODO"
    Needs a better description

---
### `programResource`

**Returns** <type>[Archive](../Types/Archive.md)</type>

Returns the program resource archive (either `slade.pk3` or the `res` folder if you are running a dev build).

---
### `recentFiles`

**Returns** <type>string[]</type>

Returns an array of file paths to recently opened archives.

---
### `bookmarks`

**Returns** <type>[ArchiveEntry](../Types/ArchiveEntry.md)`[`]</type>

Returns an array of all currently bookmarked entries.

---
### `addBookmark`

<params>Parameters</params>

* <type>[ArchiveEntry](../Types/ArchiveEntry.md)</type> <arg>entry</arg>: The entry to bookmark

Adds <arg>entry</arg> as a bookmark.

---
### `removeBookmark`

<params>Parameters</params>

* <type>[ArchiveEntry](../Types/ArchiveEntry.md)</type> <arg>entry</arg>: The entry to un-bookmark

**Returns** <type>boolean</type>

Removes <arg>entry</arg> from the bookmarked entries list. Returns `false` if the given <arg>entry</arg> was not currently bookmarked.