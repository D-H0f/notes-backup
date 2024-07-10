Name: jaydebeapi
Description:
Dependencies:
	datetime, [[glob]], os, time, re, sys, warnings
Functions:
	`connect(jclassname, url, driver_args=None, jars=None, libs=None)`
		Description:
			Open a connection to a database using a JDBC driver and return a Connection
			class instance.
		Arguments:
			jsclassname:
				Full qualified Java class name of the JDBC driver.
			url:
				Database url as required by the JDBC driver.
			driver_args:
				Dictionary or sequence of arguments to be passed to the Java
				DriverManager .getConnection method. Usually sequence of username
				and password for the db. Alternatively a dictionary of connection
				arguments (where 'user' and 'password' would probably be included)
				See [link](http://docs.oracle.com/javase/7/docs/api/java/sql/DriverManager.html) for more details.
			jars:
				Jar filename or sequence of filenames for the JDBC driver.
			libs:
				Dll/so filenames or sequence of dlls/sos used as shared library by the
				JDBC driver
Classes:
	`Connection(jconn, converters)`
		Arguments:
			jconn
				`jconn = _jdbc_connect(jclassname, url, driver_args, jars, libs)`
			converters
		Methods:
			`.close(self)`
			`.commit(self)`
			`.cursor(self)`
			`.rollback(self)`
	`Cursor(connection, converters)
		Methods:
			`.close(self)`
			`.execute(self, operation, parameters=None)`
			`.executemany(self, operation, seq_of_parameters)`
			`.fetchall(self)`
			`.fetchmany(self, size=None)`
			`.fetchone(self)`
			`.setinputsizes(self, sizes)`
			`.setoutputsize(self, size, column=None)`