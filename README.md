# SnipGenius README

This is the README for your extension "SnipGenius". SnipGenius provides a collection of PHP snippets to simplify common coding tasks. This documentation covers the features, settings, and other relevant details for using this extension.

## Features

SnipGenius includes the following PHP snippets:

- **`Database Connection`**  
  Prefix: `dbconn`  
  Description: Generates a procedural `database connection`.

- **`SELECT Query`**  
  Prefix: `dbread`  
  Description: Generates a procedural `SELECT query`.

- **`Insert Query`**  
  Prefix: `dbwrite`  
  Description: Generates a procedural `INSERT` statement.

- **`Update Query`**  
  Prefix: `dbupdate`  
  Description: Generates a procedural `UPDATE` statement.

- **`Delete Query`**  
  Prefix: `dbdelete`  
  Description: Generates a procedural `DELETE` statement.

- **`Form Handling`**  
  Prefix: `fiq`  
  Description: Handles `form data submission` and insertion into the database.

- **`Query Error Check`**  
  Prefix: `qch`  
  Description: Checks for `errors` after running a MySQL query.

- **`Class Definition`**  
  Prefix: `clsdef`  
  Description: Generates a basic PHP class definition with `properties, methods, default values`, and usage examples.

- **`Database Connection With custom class`**  
  Prefix: `cdbconn`  
  Description: Generates a PHP class for `database connection` using OOP with default values and usage examples.

- **`Class Based Insert Query Method`**  
  Prefix: `fdbwrite`  
  Description: Generates an insert query method for the Database class. Use with `insert($table, $columns, $values)`.

- **`Class Based Update Query Method`**  
  Prefix: `fdbupdate`  
  Description: Generates an update query method for the Database class. Use with `update($table, $set, $conditions)`.

- **`Class Based Select Query Method`**  
  Prefix: `fdbread`  
  Description: Generates a select query method for the Database class. Use with `select($table, $columns, $conditions)`.

- **`Class Based Delete Query Method`**  
  Prefix: `fdbdelete`  
  Description: Generates a delete query method for the Database class. Use with `delete($table, $conditions)`.

- **`OOP Database Connection`**  
  Prefix: `odbconn`  
  Description: Generates a `database connection`.

- **`OOP SELECT Query`**  
  Prefix: `odbread`  
  Description: Generates a `OOP SELECT query`.

- **`OOP Insert Data`**  
  Prefix: `odbwrite`  
  Description: Generates an `INSERT` statement.

- **`OOP Update Data`**  
  Prefix: `odbupdate`  
  Description: Generates an `OOP UPDATE` statement.

- **`OOP Delete Data`**  
  Prefix: `odbdelete`  
  Description: Generates an `OOP DELETE` statement.

- **`OOP Prepared Statement`**  
  Prefix: `prepstmt`  
  Description: Generates an `OOP prepared` statement.

- **`PDO Connection`**  
  Prefix: `pdoconnect`  
  Description: Generates a PDO `database connection`.

- **`PDO Insert Data`**  
  Prefix: `pdoinsert`  
  Description: PDO Inserts data into a table.

- **`PDO Read Data`**  
  Prefix: `pdoread`  
  Description: Read data from a table..

- **`PDO Update Data`**  
  Prefix: `pdoupdate`  
  Description: Updates data in a table.

- **`PDO Delete Data`**  
  Prefix: `pdodelete`  
  Description: Deletes data from a table.

- **`PDO Insert Multiple Rows`**  
  Prefix: `pdominsert`  
  Description: Inserts multiple rows into a table..

- **`PDO Check Table Exists`**  
  Prefix: `ptex`  
  Description: Checks if a table exists in the database..

- **`PDO Execute Raw SQL`**  
  Prefix: `pexecsql`  
  Description: Executes raw SQL query and fetches results`.

- **`If-Else`**  
  Prefix: `ifelse`  
  Description: Creates a basic `if-else` statement.

- **`If-elseif-else`**  
  Prefix: `ifelseif`  
  Description: Creates a basic `If-elseif-else` statement..

- **`Foreach Loop`**  
  Prefix: `foreach`  
  Description: Creates a `foreach` loop.

- **`Try-Catch Block`**  
  Prefix: `trycatch`  
  Description: Creates a `try-catch` block.

- **`Include File`**  
  Prefix: `inc`  
  Description: Includes a PHP file.

- **`Require File`**  
  Prefix: `rqr`  
  Description: Requires a PHP file.

- **`include_once`**  
  Prefix: `inco`  
  Description: Generates an `include_once` statement.  
  ![include_once screenshot](images/inco.png)

- **`require_once`**  
  Prefix: `reqo`  
  Description: Generates a `require_once` statement.  
  ![require_once screenshot](images/reqo.png)

- **`Database Connection`**  
  Prefix: `dbconn`  
  Description: Generates a procedural database connection snippet.  
  ![Database Connection screenshot](images/dbconn.png)

- **`SELECT Query`**  
  Prefix: `dbread`  
  Description: Generates a `SELECT` query snippet.  
  ![SELECT Query screenshot](images/dbread.png)

- **`INSERT Query`**  
  Prefix: `dbwrite`  
  Description: Generates an `INSERT` statement snippet.  
  ![INSERT Query screenshot](images/dbwrite.png)

- **`UPDATE Query`**  
  Prefix: `dbupdate`  
  Description: Generates an `UPDATE` statement snippet.  
  ![UPDATE Query screenshot](images/dbupdate.png)

- **`DELETE Query`**  
  Prefix: `dbdelete`  
  Description: Generates a `DELETE` statement snippet.  
  ![DELETE Query screenshot](images/dbdelete.png)

- **`Form Handling`**  
  Prefix: `fiq`  
  Description: Handles form data submission and insertion into the database.  
  ![Form Handling screenshot](images/fiq.png)

- **`Query Error Check`**  
  Prefix: `qch`  
  Description: Checks for errors after running a MySQL query.  
  ![Query Error Check screenshot](images/qch.png)

- **`Class Definition`**  
  Prefix: `clsdef`  
  Description: Generates a basic PHP class definition with properties, methods, default values, and usage examples.  
  ![Class Definition screenshot](images/clsdef.png)

- **`Class Database Connection`**  
  Prefix: `cdbconn`  
  Description: Generates a PHP class for database connection using OOP with default values and usage examples.  
  ![Class Database Connection screenshot](images/cdbconn.png)

- **`Insert Query Method`**  
  Prefix: `fdbwrite`  
  Description: Generates an insert query method for the Database class.  
  ![Insert Query Method screenshot](images/fdbwrite.png)

- **`Update Query Method`**  
  Prefix: `fdbupdate`  
  Description: Generates an update query method for the Database class.  
  ![Update Query Method screenshot](images/fdbupdate.png)

- **`Select Query Method`**  
  Prefix: `fdbread`  
  Description: Generates a select query method for the Database class.  
  ![Select Query Method screenshot](images/fdbread.png)

- **`Delete Query Method`**  
  Prefix: `fdbdelete`  
  Description: Generates a delete query method for the Database class.  
  ![Delete Query Method screenshot](images/fdbdelete.png)

- **`OOP Database Connection`**  
  Prefix: `odbconn`  
  Description: Generates a database connection snippet.  
  ![OOP Database Connection screenshot](images/odbconn.png)

- **`PDO Connection`**  
  Prefix: `pdoconnect`  
  Description: Generates a PDO database connection snippet.  
  ![PDO Connection screenshot](images/pdoconnect.png)

- **`OOP SELECT Query`**  
  Prefix: `odbread`  
  Description: Generates an OOP SELECT query snippet.  
  ![OOP SELECT Query screenshot](images/odbread.png)

- **`OOP Insert Data`**  
  Prefix: `odbwrite`  
  Description: Generates an INSERT statement snippet.  
  ![OOP Insert Data screenshot](images/odbwrite.png)

- **`OOP Update Data`**  
  Prefix: `odbupdate`  
  Description: Generates an OOP UPDATE statement snippet.  
  ![OOP Update Data screenshot](images/odbupdate.png)

- **`OOP Delete Data`**  
  Prefix: `odbdelete`  
  Description: Generates an OOP DELETE statement snippet.  
  ![OOP Delete Data screenshot](images/odbdelete.png)

- **`OOP Prepared Statement`**  
  Prefix: `prepstmt`  
  Description: Generates an OOP prepared statement snippet.  
  ![OOP Prepared Statement screenshot](images/prepstmt.png)

- **`If-Else`**  
  Prefix: `ifelse`  
  Description: Creates a basic if-else statement.  
  ![If-Else screenshot](images/ifelse.png)

- **`If-Else if-else`**  
  Prefix: `ifelseif`  
  Description: Creates a basic if-else if-else statement.  
  ![If-Else if-else screenshot](images/ifelseif.png)

- **`Foreach Loop`**  
  Prefix: `foreach`  
  Description: Creates a foreach loop.  
  ![Foreach Loop screenshot](images/foreach.png)

- **`Try-Catch Block`**  
  Prefix: `trycatch`  
  Description: Creates a try-catch block.  
  ![Try-Catch Block screenshot](images/trycatch.png)

- **`Include File`**  
  Prefix: `inc`  
  Description: Includes a PHP file.  
  ![Include File screenshot](images/inc.png)

- **`Require File`**  
  Prefix: `rqr`  
  Description: Requires a PHP file.  
  ![Require File screenshot](images/rqr.png)

- **`Include Once`**  
  Prefix: `inco`  
  Description: Generates an 'include_once' statement.  
  ![Include Once screenshot](images/inco.png)

- **`Require Once`**  
  Prefix: `rqro`  
  Description: Generates a 'require_once' statement.  
  ![Require Once screenshot](images/rqro.png)

- **`Session Start`**  
  Prefix: `sessionstart`  
  Description: Starts a PHP session.  
  ![Session Start screenshot](images/sessionstart.png)

- **`HTTP Header`**  
  Prefix: `hdr`  
  Description: Sends a raw HTTP header.  
  ![HTTP Header screenshot](images/hdr.png)

- **`Set Cookie`**  
  Prefix: `setcookie`  
  Description: Sets a cookie.  
  ![Set Cookie screenshot](images/setcookie.png)

- **`Get Request`**  
  Prefix: `get`  
  Description: Retrieves data from a GET request.  
  ![Get Request screenshot](images/get.png)

- **`Post Request`**  
  Prefix: `post`  
  Description: Retrieves data from a POST request.  
  ![Post Request screenshot](images/post.png)

- **`Date and Time`**  
  Prefix: `date`  
  Description: Gets the current date and time.  
  ![Date and Time screenshot](images/date.png)

- **`DateTime Format 1`**  
  Prefix: `datetime1`  
  Description: Outputs the current date and time in the format dd/mm/yy HH:mm:ss.  
  ![DateTime Format 1 screenshot](images/datetime1.png)

- **`Date Format 1`**  
  Prefix: `dMy`  
  Description: Outputs the current date in the format dd M yyyy.  
  ![Date Format 1 screenshot](images/dMy.png)

- **`Time Format 1`**  
  Prefix: `timeA`  
  Description: Outputs the current time in the format h:i AM/PM.  
  ![Time Format 1 screenshot](images/timeA.png)

- **`Day and Month Format`**  
  Prefix: `daymonth`  
  Description: Outputs the current day and month in the format l F Y.  
  ![Day and Month Format screenshot](images/daymonth.png)

- **`Print Array`**  
  Prefix: `pra`  
  Description: Prints an array in a readable format.  
  ![Print Array screenshot](images/pra.png)

- **`Check Variable Set`**  
  Prefix: `issetcheck`  
  Description: Checks if a variable is set.  
  ![Check Variable Set screenshot](images/issetcheck.png)

- **`File Upload`**  
  Prefix: `fileupload`  
  Description: Handles file upload.  
  ![File Upload screenshot](images/fileupload.png)

- **`Generate Random String`**  
  Prefix: `randstring`  
  Description: Generates a random string of a given length.  
  ![Generate Random String screenshot](images/randstring.png)

- **`Send Email`**  
  Prefix: `sendemail`  
  Description: Sends an email.  
  ![Send Email screenshot](images/sendemail.png)

- **`Check File Exists`**  
  Prefix: `fileexists`  
  Description: Checks if a file exists.  
  ![Check File Exists screenshot](images/fileexists.png)

- **`Read File`**  
  Prefix: `readfile`  
  Description: Reads the content of a file.  
  ![Read File screenshot](images/readfile.png)

- **`Write to File`**  
  Prefix: `writefile`  
  Description: Writes content to a file.  
  ![Write to File screenshot](images/writefile.png)

- **`Sanitize Input`**  
  Prefix: `sanitize`  
  Description: Sanitizes input data.  
  ![Sanitize Input screenshot](images/sanitize.png)

- **`Validate Email`**  
  Prefix: `validateemail`  
  Description: Validates an email address.  
  ![Validate Email screenshot](images/validateemail.png)

- **`Generate UUID`**  
  Prefix: `uuid`  
  Description: Generates a UUID.  
  ![Generate UUID screenshot](images/uuid.png)

- **`Check Array`**  
  Prefix: `isarray`  
  Description: Checks if a variable is an array.  
  ![Check Array screenshot](images/isarray.png)

- **`Array to JSON`**  
  Prefix: `arraytojson`  
  Description: Converts an array to JSON format.  
  ![Array to JSON screenshot](images/arraytojson.png)

- **`JSON to Array`**  
  Prefix: `jsontoarray`  
  Description: Decodes JSON string to an array.  
  ![JSON to Array screenshot](images/jsontoparray.png)

- **`String Contains`**  
  Prefix: `strcontains`  
  Description: Checks if a string contains a substring.  
  ![String Contains screenshot](images/strcontains.png)

- **`Current Timestamp`**  
  Prefix: `timestamp`  
  Description: Gets the current Unix timestamp.  
  ![Current Timestamp screenshot](images/timestamp.png)

- **`Date Difference`**  
  Prefix: `datediff`  
  Description: Calculates the difference between two dates.  
  ![Date Difference screenshot](images/datediff.png)

- **`Check Empty`**  
  Prefix: `isempty`  
  Description: Checks if a variable is empty.  
  ![Check Empty screenshot](images/isempty.png)

- **`Validate URL`**  
  Prefix: `vurl`  
  Description: Validates a URL.  
  ![Validate URL screenshot](images/validateurl.png)

- **`Format Date`**  
  Prefix: `formatdate`  
  Description: Formats a date.  
  ![Format Date screenshot](images/formatdate.png)

- **`Trim Whitespace`**  
  Prefix: `trimspace`  
  Description: Trims whitespace from a string.  
  ![Trim Whitespace screenshot](images/trimspace.png)

- **`To Uppercase`**  
  Prefix: `toupper`  
  Description: Converts a string to uppercase.  
  ![To Uppercase screenshot](images/toupper.png)

- **`To Lowercase`**  
  Prefix: `tolower`  
  Description: Converts a string to lowercase. Replace `$1` with the string.  
  ![To Lowercase screenshot](images/tolower.png)

- **`Check Writable`**  
  Prefix: `iswritable`  
  Description: Checks if a file is writable. Replace `$1` with the file path.  
  ![Check Writable screenshot](images/iswritable.png)

- **`File Size`**  
  Prefix: `filesize`  
  Description: Calculates the size of a file in bytes. Replace `$1` with the file path.  
  ![File Size screenshot](images/filesize.png)

- **`File Extension`**  
  Prefix: `fileext`  
  Description: Gets the extension of a file. Replace `$1` with the file path.  
  ![File Extension screenshot](images/fileext.png)

- **`Count Words`**  
  Prefix: `countwords`  
  Description: Counts the number of words in a string. Replace `$1` with the string.  
  ![Count Words screenshot](images/countwords.png)

- **`Replace Text`**  
  Prefix: `replacetext`  
  Description: Replaces text in a string. Replace `$1` with the search text, `$2` with the replacement text, and `$3` with the original string.  
  ![Replace Text screenshot](images/replacetext.png)

- **`Find Text`**  
  Prefix: `findtext`  
  Description: Finds text in a string. Replace `$1` with the string and `$2` with the search text.  
  ![Find Text screenshot](images/findtext.png)

- **`Extract Substring`**  
  Prefix: `substring`  
  Description: Extracts a substring from a string. Replace `$1` with the string, `$2` with the start position, and `$3` with the length.  
  ![Extract Substring screenshot](images/substring.png)

- **`Random Integer`**  
  Prefix: `rint`  
  Description: Generates a random integer between min and max values. Replace `$1` with min and `$2` with max.  
  ![Random Integer screenshot](images/randint.png)

- **`String Length`**  
  Prefix: `strlen`  
  Description: Calculates the length of a string. Replace `$1` with the string.  
  ![String Length screenshot](images/strlen.png)

- **`File Modification Time`**  
  Prefix: `filemtime`  
  Description: Gets the last modification time of a file. Replace `$1` with the file path.  
  ![File Modification Time screenshot](images/filemtime.png)

- **`Validate Integer`**  
  Prefix: `vint`  
  Description: Validates if a value is an integer. Replace `$1` with the value.  
  ![Validate Integer screenshot](images/validateint.png)

- **`For loop`**  
  Prefix: `for`  
  Description: Creates a for loop. Replace `condition` with your loop condition.  
  ![For loop screenshot](images/forloop.png)

- **`Constructor method`**  
  Prefix: `_c`  
  Description: Creates a constructor method. Replace `parameters` with your constructor parameters.  
  ![Constructor method screenshot](images/_c.png)

- **`Error Logging`**  
  Prefix: `errorlog`  
  Description: Logs errors to the PHP error log file.  
  ![Error Logging screenshot](images/errorlog.png)

- **`Custom Error Handler`**  
  Prefix: `errorCustom`  
  Description: Sets a custom error handler function.  
  ![Custom Error Handler screenshot](images/errorCustom.png)

- **`Shorthand If Statement`**  
  Prefix: `?if`  
  Description: Shorthand if statement (ternary operator) for concise conditional assignments.  
  ![Shorthand If Statement screenshot](images/?if.png)

- **`Nested If Statements`**  
  Prefix: `iif`  
  Description: Creates nested if statements for more complex conditional logic.  
  ![Nested If Statements screenshot](images/iif.png)

- **`Switch Statement`**  
  Prefix: `switch`  
  Description: Creates a switch statement with multiple cases.  
  ![Switch Statement screenshot](images/switch.png)

- **`Do-While Loop`**  
  Prefix: `dowhile`  
  Description: Creates a do-while loop in PHP.  
  ![Do-While Loop screenshot](images/dowhile.png)

- **`While Loop`**  
  Prefix: `while`  
  Description: Creates a while loop in PHP.  
  ![While Loop screenshot](images/while.png)

- **`Array Splice`**  
  Prefix: `array_splice`  
  Description: Modifies an array by removing or replacing elements.  
  ![Array Splice screenshot](images/array_splice.png)

- **`Multidimensional Arrays`**  
  Prefix: `multiarray`  
  Description: Defines and accesses elements in a multidimensional array.  
  ![Multidimensional Arrays screenshot](images/multiarray.png)

- **`Array Functions`**  
  Prefix: `arrayfunc`  
  Description: Common PHP array functions and their usage.  
  ![Array Functions screenshot](images/arrayfunc.png)

- **`Multiple Insert PDO`**  
  Prefix: `pdoim`  
  Description: Performs multiple inserts into a database using PDO.  
  ![Multiple Insert PDO screenshot](images/pdoim.png)

## Requirements

This extension does not have any specific dependencies. Ensure you have [Visual Studio Code](https://code.visualstudio.com/) installed to use this extension.

## Extension Settings

This extension does not add any custom VS Code settings through the `contributes.configuration` extension point.

## Known Issues

There are no known issues at the moment. If you encounter any problems, please open an issue in the [GitHub repository](https://github.com/your-repo).

## Contributing

Contributions are welcome! Please submit a pull request or open an issue in the [GitHub repository](https://github.com/your-repo).

## License

This extension is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Enjoy using SnipGenius for your PHP development needs!
