Description:
	-The ADD instruction copies new files, directories or remote file URLs from \<src\> and adds them to the filesystem of the image at the path \<dest\>
	-Multiple \<src\> resources may be specified but if they are files ore directories, their paths are interpreted as relative to the source of the context of the build.
	-Each \<src\> may contain wildcards and matching will be done using Go's [filepath.Match](https://golang.org/pkg/path/filepath#Match) rules.
	ADD has two forms. The latter form is required for paths containing whitespace.
		`ADD [FLAGS] <src> ... <dest>`
		`ADD [FLAGS] ["<src>", ... "<dest>"]`
			ADD:
				base command
			FLAGS:
				optional flags to modify behavior of the command
			src:
				one or multiple source directories or files to be copied and added to the image.
			dest:
				the destination to which copied files and directories will be placed. Can be relative to WORKDIR, or an absolute path.
				example:
					ADD test.txt relateiveDir/
						this is relateive to WORKDIR
					ADD test.txt /mnt/
						this is an absolute path to the mnt directory in the root directory
Flags:
	--keep-git-dir
	--checksum
	--chown
	--chmod
	--link
		- Enabling this flag in COPY or ADD commands allows you to copy files with enhanced semantics where your files remain independent on their own layer and don't get invalidated when commands on previous layers are changed.
		- when --link is used, your source files are copied into an empty destination directory. That directory is turned into a layer that is linked on top of your previous state.
		- example:
			```
			FROM alpine
			ADD --link /foo /bar
			```
			is the equivalent of doing two builds:
			```
			FROM alpine
			```
			and
			```
			FROM scratch
			COPY /foo /bar
			```
			and merging all the layers of both images together.
	--exclude
		- The --exclude flag lets you specify a path expression for files to be excluded.
		- The path expression follows the smae format as `<src>`, supporting wildcards and matching. For example, to add all files starting with "hom", excluding files with a .txt extension: `ADD --exclude=*.txt hom* /mydir/`
Additional notes:
	ADD obeys the following rules:
		- The \<src\> path must be inside the build context; you can't use `ADD ../something /something`, because the building can only access files from the context, and `../something` specifies a parent file or directory of the build context root.
		- if \<src\> is a directory, the entire contents of the directory are copied, including filesystem metadata (The directory itelself isn't copied, only its contents.)
		- if multiple \<src\> resources are specified, either directly or due to the use of a wildcard, then \<dest\> must be a directory, and it must end with a slash /.
		- if \<dest\> doesn't exist, it's created, along with all missing directories in its path.