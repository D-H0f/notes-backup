Name: pathlib - Object-oriented filesystem paths.
Description:
	This module provides classes to represent abstact paths and concrete paths with
	operations that have semantic appropriate for different operating systems.
Classes:
	Path(\*args, \*\*kwargs)
		Description:
			PurePath subclass that can make system calls
			Path represents a filesystem path, but unlike PurePath, also offers methods
			to do system calls on path objects. Depending on your system, instantiating a Path
			will return either a PosixPath or a WindowsPath object. You can also instantiate a
			PosixPath or a WindowsPath directly.
		Methods:
			`.resolve(self, strict=False)`
				Make the path absolute, resolving all symlinks on the way and also 
				normalizing it.
		Readonly properties inherited from PurePath
			`.parent`
				The logical parent of the path.
Examples:
	The following example shows how to find the directory a program is currently running
	in:
```python
curdir = pathlib.Path(__file__).parent.resolve()
print(curdir)
```