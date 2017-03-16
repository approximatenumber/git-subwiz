## `git-subwiz`

Tool for easily adding/updating/removing subtrees in your project.

### Installing

Copy script to directory for your local binaries specified in `$PATH` (for example, `/usr/local/bin` for linux-users and `c:/cygwin/usr/local/bin` for cygwin).

Check that the script is executable: `chmod +x /usr/local/bin/git-subwiz`

### Preparing

Create or copy `dependencies.txt` in your repository. Add content with subtrees you want to add. It must be looked like:

    <repository name> ; <repository url> ; <prefix>

For example, `dependencies.txt` with *Sun* and *Moon* configuration:

    sun ;  ssh://git@github:7999/examples/sun.git  ; .externals
    moon ;  ssh://git@github:7999/examples/moon.git ; .externals

When you run `git subwiz import` you can find imported subtrees `.externals/sun` and `.externals/moon`.

**Be careful to separate configuration items only with semicolon (`;`)!**

Lines started with `#` are ignored (example: `# this is comment line and it will be ignored`).

### Usage

#### Importing

`$ git subwiz import`

Imports all subtrees listed in `dependencies.txt`.

#### Updating

`$ git subwiz update`

Updates all subtrees listed in `dependencies.txt`.

#### Listing

`$ git subwiz list`

Lists all subtrees and its changed time listed in `dependencies.txt`.

#### Removing

`$ git subwiz remove`

Removes all subtrees from repository listed in `dependencies.txt`.
