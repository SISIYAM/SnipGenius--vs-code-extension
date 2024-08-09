# SnipGenius README

This is the README for your extension "SnipGenius". SnipGenius provides a collection of PHP snippets to simplify common coding tasks. This documentation covers the features, settings, and other relevant details for using this extension.

## Features

# SnipGenius includes the following PHP snippets:

- **`Database Connection`**  
   Prefix: `dbconn`  
   Description: Generates a procedural `database connection`.

  ```php
  $servername = "";
  $username = "";
  $password = "";
  $dbname = "";
  $conn = mysqli_connect($servername, $username, $password, $dbname);
  if (!$conn) {
  die("Connection failed: " . mysqli_connect_error());
  }
  ```

- **`SELECT Query`**
  Prefix: `dbread`
  Description: Generates a procedural `SELECT query`.

  ```php
  $sql = "SELECT * FROM tableName WHERE column = 'condition'";
  $result = mysqli_query($conn, $sql);
  if (mysqli_num_rows($result) > 0) {
  while ($row = mysqli_fetch_assoc($result)) {

  }
  } else {
    echo '0 results';
  }
  ```

- **`Insert Query`**
  Prefix: `dbwrite`
  Description: Generates a procedural `INSERT` statement.

  ```php
  $sql = "INSERT INTO tbaleName (keys) VALUES ('')";
  $result = mysqli_query($conn, $sql);

  if ($result) {
    echo 'New record created successfully';
  } else {
    echo 'Error: ' . mysqli_error($conn);
  }
  ```

- **`Update Query`**
  Prefix: `dbupdate`
  Description: Generates a procedural `UPDATE` statement.

  ```php
  $sql = "UPDATE tableName SET column = 'value' WHERE column = 'condition'";
  $result = mysqli_query($conn, $sql);

  if ($result) {
    echo 'Record updated successfully';
  } else {
    echo 'Error: ' . mysqli_error($conn);
  }
  ```

- **`Delete Query`**
  Prefix: `dbdelete`
  Description: Generates a procedural `DELETE` statement.

  ```php
  $sql = "DELETE FROM tableName WHERE column = 'condition'";
  $result = mysqli_query($conn, $sql);

  if ($result) {
    echo 'Record deleted successfully';
  } else {
    echo 'Error: ' . mysqli_error($conn);
  }

  ```

- **`Form Handling`**
  Prefix: `fiq`
  Description: Handles `form data submission` and insertion into the database.

  ```php
  if (isset($_POST['submit'])) { // Here submit is the name of the button that submits the form
    $name = mysqli_real_escape_string($conn, $_POST['name']);
    $email = mysqli_real_escape_string($conn, $_POST['email']);
    $sql = "INSERT INTO users (name, email) VALUES ('$name', '$email')";
    if (mysqli_query($conn, $sql)) {
      echo 'New record created successfully';
    } else {
      echo 'Error: ' . mysqli_error($conn);
    }
  }
  ```

- **`Query Error Check`**
  Prefix: `qch`
  Description: Checks for `errors` after running a MySQL query.

  ```php
  $result = mysqli_query($conn, $sql);
  if (!$result) {
    echo 'Query Error: ' . mysqli_error($conn);
  } else {

  }
  ```

- **`Class Definition`**
  Prefix: `clsdef`
  Description: Generates a basic PHP class definition with `properties, methods, default values`, and usage examples.

  ```php
  class className {
    private $property1 = 'default1';
    private $property2 = 'default2';

    public function __construct($property1 = 'default1', $property2 = 'default2') {
      $this->$property1 = $property1;
      $this->$property2 = $property2;
    }

    public function getProperty1() {
      return $this->$property1;
    }

    public function setProperty1($property1) {
      $this->$property1 = $property1;
    }

    public function getProperty2() {
      return $this->$property2;
    }

    public function setProperty2($property2) {
      $this->$property2 = $property2;
    }
  }

  // Usage Example
  // Create an instance of the class with default values
  $obj = new className();

  // Create an instance with custom values
  $obj = new className('value1', 'value2');

  // Access and modify properties
  $obj->setProperty1('new value1');
  $property1 = $obj->getProperty1();
  $obj->setProperty2('new value2');
  $property2 = $obj->getProperty2();

  ```

- **`Database Connection With custom class`**
  Prefix: `cdbconn`
  Description: Generates a PHP class for `database connection` using OOP with default values and usage examples.

  ```php
  class Database {
    private $servername = 'localhost';
    private $username = 'root';
    private $password = '';
    private $dbname = 'test';
    private $conn;

    public function __construct($servername = 'localhost', $username = 'root', $password = '', $dbname = 'test') {
      $this->$servername = $servername;
      $this->$username = $username;
      $this->$password = $password;
      $this->$dbname = $dbname;
      $this->connect();
    }

    private function connect() {
      $this->$conn = new mysqli($this->$servername, $this->$username, $this->$password, $this->$dbname);
      if ($this->$conn->connect_error) {
        die("Connection failed: " . $this->$conn->connect_error);
      }
    }

    public function getConnection() {
      return $this->$conn;
    }
  }

  // Usage Example
  // Create an instance of the Database class
  $db = new Database();

  // Create an instance with custom values
  $db = new Database('localhost', 'user', 'password', 'database');

  // Access the connection object
  $conn = $db->getConnection();


  ```

- **`Class Based Insert Query Method`**
  Prefix: `fdbwrite`
  Description: Generates an insert query method for the Database class. Use with `insert($table, $columns, $values)`.

  ```php
  public function insert($table, $columns, $values) {
    $sql = "INSERT INTO $table ($columns) VALUES ($values);";
    result = mysqli_query($this->$conn, $sql);
    if (!$result) {
      die("Query Error: " . mysqli_error($this->$conn));
    }
    return $result;
  }

  // Usage Example
  // Create an instance of the Database class
  $db = new Database();

  // Insert data into 'users' table
  $db->insert('users', 'name, email', '"Jon snow", "jon@example.com"');
  ```

- **`Class Based Update Query Method`**
  Prefix: `fdbupdate`
  Description: Generates an update query method for the Database class. Use with `update($table, $set, $conditions)`.

  ```php
  public function update($table, $set, $conditions) {
    $sql = "UPDATE $table SET $set WHERE $conditions;";
    $result = mysqli_query($this->$conn, $sql);
    if (!$result) {
      die("Query Error: " . mysqli_error($this->$conn));
    }
    return $result;
  }

  // Usage Example
  // Create an instance of the Database class
  $db = new Database();

  // Update data in 'users' table
  $db->update('users', 'email = "newemail@example.com"', 'name = "John snow"');
  ```

- **`Class Based Select Query Method`**
  Prefix: `fdbread`
  Description: Generates a select query method for the Database class. Use with `select($table, $columns, $conditions)`.

  ```php
  public function select($table, $columns, $conditions = '') {
    $sql = "SELECT $columns FROM $table WHERE $conditions;";
    $result = mysqli_query($this->$conn, $sql);
    if (!$result) {
      die("Query Error: " . mysqli_error($this->$conn));
    }
    return $result;
  }

  // Usage Example
  // Create an instance of the Database class
  $db = new Database();

  // Select data from 'users' table
  $result = $db->select('users', '*', 'name = "John snow"');
  while ($row = mysqli_fetch_assoc($result)) {
    echo $row['name'] . " - " . $row['email'];
  }
  ```

- **`Class Based Delete Query Method`**
  Prefix: `fdbdelete`
  Description: Generates a delete query method for the Database class. Use with `delete($table, $conditions)`.

  ```php
  public function delete($table, $conditions) {
    $sql = "DELETE FROM $table WHERE $conditions;";
    $result = mysqli_query(this->$conn, $sql);
    if (!$result) {
      die("Query Error: " . mysqli_error($this->$conn));
    }
    return $result;
  }

  // Usage Example
  // Create an instance of the Database class
  $db = new Database();

  // Delete data from 'users' table
  $db->delete('users', 'name = "John snow"');
  ```

- **`OOP Database Connection`**
  Prefix: `odbconn`
  Description: Generates a `database connection`.

  ```php
  $servername = "";
  $username = "";
  $password = "";
  $dbname = "";
  $conn = new mysqli($servername, $username, $password, $dbname);

  if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
  }
  ```

- **`OOP SELECT Query`**
  Prefix: `odbread`
  Description: Generates an `OOP SELECT query`.

  ```php
  $sql = 'SELECT * FROM tableName';
  $result = $conn->query($sql);

  if ($result->num_rows > 0) {
    while ($row = $result->fetch_assoc()) {
      // Process row
    }
  } else {
    echo '0 results';
  }

  ```

- **`OOP Insert Data`**
  Prefix: `odbwrite`
  Description: Generates an `INSERT` statement.

  ```php
  $sql = "INSERT INTO  (columns) VALUES ('');";
  $result = $conn->query($sql);

  if ($result === TRUE) {
    echo 'New record created successfully';
  } else {
    echo 'Error: ' . $sql . '<br>' . $conn->error;
  }
  ```

- **`OOP Update Data`**
  Prefix: `odbupdate`
  Description: Generates an `OOP UPDATE` statement.

```php
$sql = "UPDATE tableName SET  column= 'value' WHERE  column= 'condition';";
$result = $conn->query($sql);

if ($result === TRUE) {
  echo 'Record updated successfully';
} else {
  echo 'Error: ' . $sql . '<br>' . $conn->error;
}
```

- **`OOP Delete Data`**
  Prefix: `odbdelete`
  Description: Generates an `OOP DELETE` statement.

  ```php
  $sql = "DELETE FROM tableName WHERE  column= 'condition';";
  $result = $conn->query($sql);

  if ($result === TRUE) {
    echo 'Record deleted successfully';
  } else {
    echo 'Error: ' . $sql . '<br>' . $conn->error;
  }
  ```

- **`OOP Prepared Statement`**
  Prefix: `prepstmt`
  Description: Generates an `OOP prepared` statement.

  ```php
  $stmt = $conn->prepare("");
  $stmt->bind_param("", );
  $stmt->execute();

  $result = $stmt->get_result();
  if ($result->num_rows > 0) {
    while ($row = $result->fetch_assoc()) {

    }
  } else {
    echo '0 results';
  }
  $stmt->close();

  ```

- **`PDO Connection`**
  Prefix: `pdoconnect`
  Description: Generates a PDO `database connection`.

  ```php
  $dsn = 'mysql:host=;dbname=';
  $username = "";
  $password = "";

  try {
    $pdo = new PDO($dsn, $username, $password);
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
    echo 'Connected successfully';
  } catch (PDOException $e) {
    echo 'Connection failed: ' . $e->getMessage();
  }
  ```

- **`PDO Insert Data`**
  Prefix: `pdoinsert`
  Description: PDO Inserts data into a table.

  ```php
  $stmt = $pdo->prepare("INSERT INTO tableName  (column1, column2) VALUES (:value1, :value2)");
  $stmt->bindParam(':value1', );
  $stmt->bindParam(':value2', );
  $stmt->execute();
  ```

- **`PDO Read Data`**
  Prefix: `pdoread`
  Description: Read data from a table.

  ```php
  $stmt = $pdo->prepare("SELECT * FROM tableName WHERE column1 = :value");
  $stmt->bindParam(':value', );
  $stmt->execute();
  $results = $stmt->fetchAll(PDO::FETCH_ASSOC);
  print_r($results);
  ```

- **`PDO Update Data`**
  Prefix: `pdoupdate`
  Description: Updates data in a table.

  ```php
  $stmt = $pdo->prepare("UPDATE tableName SET column1 = :new_value WHERE column2 = :identifier");
  $stmt->bindParam(':new_value', );
  $stmt->bindParam(':identifier', );
  $stmt->execute();
  ```

- **`PDO Delete Data`**
  Prefix: `pdodelete`
  Description: Deletes data from a table.

  ```php
  $stmt = $pdo->prepare("DELETE FROM tableName WHERE column1 = :value");
  $stmt->bindParam(':value', );
  $stmt->execute();
  ```

- **`PDO Insert Multiple Rows`**
  Prefix: `pdominsert`
  Description: Inserts multiple rows into a table.

```php
$pdo->beginTransaction();
try {
  $stmt = $pdo->prepare("INSERT INTO tableName (column1, column2) VALUES (:value1, :value2)");
  foreach ($data as row) {
    $stmt->bindParam(':value1', row['value1']);
    $stmt->bindParam(':value2', row['value2']);
    $stmt->execute();
  }
  $pdo->commit();
} catch (Exception $e) {
  $pdo->rollBack();
  echo 'Failed: ' . $e->getMessage();
}
```

- **`PDO Check Table Exists`**
  Prefix: `ptex`
  Description: Checks if a table exists in the database.

  ```php
  $tableName = 'user'; // Replace with your actual table name

  $stmt = $pdo->prepare("SHOW TABLES LIKE :tableName");
  $stmt->bindParam(':tableName', $tableName, PDO::PARAM_STR);
  $stmt->execute();

  $exists = $stmt->rowCount() > 0;

  if ($exists) {
      echo 'Table exists';
  } else {
      echo 'Table does not exist';
  }
  ```

- **`PDO Execute Raw SQL`**
  Prefix: `pexecsql`
  Description: Executes raw SQL query and fetches results.

  ```php
  $stmt = $pdo->query("");
  $results = $stmt->fetchAll(PDO::FETCH_ASSOC);
  print_r($results);
  ```

- **`If-Else`**
  Prefix: `ifelse`
  Description: Creates a basic `if-else` statement.

  ```php
  if () {

  } else {
    // Alternative code
  }
  ```

- **`If-elseif-else`**
  Prefix: `ifelseif`
  Description: Creates a basic `If-elseif-else` statement.

  ```php
  if () {

  } else if () {

  } else {

  }
  ```

- **`Foreach Loop`**
  Prefix: `foreach`
  Description: Creates a `foreach` loop.

  ```php
  foreach ($array as $key => $value) {

  }
  ```

- **`Try-Catch Block`**
  Prefix: `trycatch`
  Description: Creates a `try-catch` block.

  ```php
  try {

  } catch (Exception $e) {
    echo 'Error: ' . $e->getMessage();
  }
  ```

- **`Include File`**
  Prefix: `inc`
  Description: Includes a PHP file.

  ```php
  include ''; // Your file path
  ```

- **`Require File`**
  Prefix: `rqr`
  Description: Requires a PHP file.

  ```php
  require ''; // Your file path
  ```

- **`include_once`**
  Prefix: `inco`
  Description: Generates an `include_once` statement.

  ```php
  include_once 'file_path';
  ```

- **`require_once`**
  Prefix: `rqro`
  Description: Generates a `require_once` statement.

  ```php
  require_once 'file_path';
  ```

- **`Session Start`**
  Prefix: `sessionstart`
  Description: Starts a PHP session.

  ```php
  session_start();

  $user = $_SESSION['user'];
  ```

- **`HTTP Header`**
  Prefix: `hdr`
  Description: Sends a raw HTTP header.

  ```php
  header('');
  ```

- **`Set Cookie`**
  Prefix: `setcookie`
  Description: Sets a cookie.

  ```php
  setcookie($key, $value, time() + (86400 * 30), '/');

  ```

- **`Get Request`**
  Prefix: `get`
  Description: Retrieves data from a GET request.

  ```php
  $value = $_GET[''];
  ```

- **`Post Request`**
  Prefix: `post`
  Description: Retrieves data from a POST request.

  ```php
  $value = $_POST[''];
  ```

- **`Date and Time`**
  Prefix: `date`
  Description: Gets the current date and time.

  ```php
  echo date('Y-m-d H:i:s');
  ```

- **`DateTime Format 1`**
  Prefix: `datetime1`
  Description: Outputs the current date and time in the format dd/mm/yy HH:mm:ss.

  ```php
  echo date('d/m/y H:i:s'); // Example: 11/12/24 16:30:59
  ```

- **`Date Format 1`**
  Prefix: `dMy`
  Description: Outputs the current date in the format dd M yyyy.

  ```php
  echo date('d M Y'); // Example: 11 Dec 2024
  ```

- **`Time Format 1`**
  Prefix: `timeA`
  Description: Outputs the current time in the format h:i AM/PM.

  ```php
  echo date('g:i A'); // Example: 4:30 PM
  ```

- **`Day and Month Format`**
  Prefix: `daymonth`
  Description: Outputs the current day and month in the format l F Y.

  ```php
  echo date('l F Y'); // Example: Wednesday June 2024
  ```

- **`Print Array`**
  Prefix: `pra`
  Description: Prints an array in a readable format.

  ```php
  echo '<pre>';
  print_r($array);
  echo '</pre>';
  ```

- **`Check Variable Set`**
  Prefix: `issc`
  Description: Checks if a variable is set.

  ```php
  if (isset($variable)) {
    // Variable is set
  } else {
    // Variable is not set
  }
  ```

- **`File Upload`**
  Prefix: `fileupload`
  Description: Handles file upload.

  ```php
  if ($_FILES['']['error'] == UPLOAD_ERR_OK) {
    move_uploaded_file($_FILES['']['tmp_name'], '');
    echo 'File uploaded successfully';
  } else {
    echo 'File upload error: ' . $_FILES['']['error'];
  }
  ```

- **`Generate Random String`**
  Prefix: `randstring`
  Description: Generates a random string of a given length.

  ```php
  $length = ;
  $chars = '0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ';
  $randomString = '';
  for ($i = 0; $i < $length; $i++) {
    $randomString .= $chars[rand(0, strlen($chars) - 1)];
  }
  echo $randomString;
  ```

- **`Send Email`**
  Prefix: `sendemail`
  Description: Sends an email.

  ```php
  $to = '';
  $subject = '';
  $message = '';
  $headers = 'From: no-reply@example.com';
  mail($to, $subject, $message, $headers);
  ```

- **`Check File Exists`**
  Prefix: `fileexists`
  Description: Checks if a file exists.

  ```php
  if (file_exists('')) {
    echo 'File exists';
  } else {
    echo 'File does not exist';
  }
  ```

- **`Read File`**
  Prefix: `readfile`
  Description: Reads the content of a file.

  ```php
  $content = file_get_contents('');
  if ($content !== false) {
    echo $content;
  } else {
    echo 'Failed to read file';
  }
  ```

- **`Write to File`**
  Prefix: `writefile`
  Description: Writes content to a file.

  ```php
  $content = '';
  file_put_contents('', $content);
  echo 'File written successfully';
  ```

- **`Sanitize Input`**
  Prefix: `sanitize`
  Description: Sanitizes input data.

  ```php
  $input = filter_var('', FILTER_SANITIZE_STRING);
  echo $input;
  ```

- **`Validate Email`**
  Prefix: `vemail`
  Description: Validates an email address.

  ```php
  $email = '';
  if (filter_var($email, FILTER_VALIDATE_EMAIL)) {
    echo 'Valid email address';
  } else {
    echo 'Invalid email address';
  }
  ```

- **`Generate UUID`**
  Prefix: `uuid`
  Description: Generates a UUID.

  ```php
  $uuid = bin2hex(random_bytes(16));
  $uuid = vsprintf('%s-%s-%s-%s-%s', str_split($uuid, 4));
  echo $uuid;
  ```

- **`Check Array`**
  Prefix: `isarr`
  Description: Checks if a variable is an array.

  ```php
  if (is_array($variable)) {
    echo 'Variable is an array';
  } else {
    echo 'Variable is not an array';
  }
  ```

- **`Array to JSON`**
  Prefix: `arrtojson`
  Description: Converts an array to JSON format.

  ```php
  $json = json_encode($array);
  echo $json;
  ```

- **`JSON to Array`**
  Prefix: `jsontoarray`
  Description: Decodes JSON string to an array.

  ```php
  $array = json_decode('', true);
  print_r($array);
  ```

- **`String Contains`**
  Prefix: `strcontains`
  Description: Checks if a string contains a substring.

  ```php
  if (strpos('', '') !== false) {
    echo 'Substring found';
  } else {
    echo 'Substring not found';
  }
  ```

- **`Current Timestamp`**
  Prefix: `timestamp`
  Description: Gets the current Unix timestamp.

  ```php
  $timestamp = time();
  echo $timestamp;
  ```

- **`Date Difference`**
  Prefix: `datediff`
  Description: Calculates the difference between two dates.

  ```php
  $date1 = new DateTime('');
  $date2 = new DateTime('');
  $interval = $date1->diff($date2);
  echo $interval->format('%y years, %m months, %d days');
  ```

- **`Check Empty`**
  Prefix: `isempty`
  Description: Checks if a variable is empty.

  ```php
  if (empty($variable)) {
    echo 'Variable is empty';
  } else {
    echo 'Variable is not empty';
  }
  ```

- **`Validate URL`**
  Prefix: `vurl`
  Description: Validates a URL.

  ```php
  $url = '';
  if (filter_var($url, FILTER_VALIDATE_URL)) {
    echo 'Valid URL';
  } else {
    echo 'Invalid URL';
  }
  ```

- **`Format Date`**
  Prefix: `formatdate`
  Description: Formats a date.

  ```php
  $date = new DateTime('');
  echo $date->format('');
  ```

- **`Trim Whitespace`**
  Prefix: `trimspace`
  Description: Trims whitespace from a string.

  ```php
  $trimmed = trim('');
  echo $trimmed;
  ```

- **`To Uppercase`**
  Prefix: `toupper`
  Description: Converts a string to uppercase.

  ```php
  $uppercase = strtoupper('');
  echo $uppercase;
  ```

- **`To Lowercase`**
  Prefix: `tolower`
  Description: Converts a string to lowercase.

  ```php
  $lowercase = strtolower('');
  echo $lowercase;
  ```

- **`Check Writable`**
  Prefix: `iswritable`
  Description: Checks if a file is writable.

  ```php
  if (is_writable('')) {
    echo 'File is writable';
  } else {
    echo 'File is not writable';
  }
  ```

- **`File Size`**
  Prefix: `filesize`
  Description: Calculates the size of a file in bytes.

  ```php
  $size = filesize('');
  echo 'File size: ' . $size . ' bytes';
  ```

- **`File Extension`**
  Prefix: `fileext`
  Description: Gets the extension of a file.

```php
$extension = pathinfo('', PATHINFO_EXTENSION);
echo 'File extension: ' . $extension;
```

- **`Count Words`**
  Prefix: `countwords`
  Description: Counts the number of words in a string.

  ```php
  $wordCount = str_word_count('');
  echo 'Word count: ' . $wordCount;
  ```

- **`Replace Text`**
  Prefix: `replacetext`
  Description: Replaces text in a string.

  ```php
  $newString = str_replace('', '', '');
  echo $newString;
  ```

- **`Find Text`**
  Prefix: `findtext`
  Description: Finds text in a string.

  ```php
  $position = strpos('', '');
  if ($position !== false) {
    echo 'Text found at position: ' . $position;
  } else {
    echo 'Text not found';
  }
  ```

- **`Extract Substring`**
  Prefix: `substr`
  Description: Extracts a substring from a string.

  ```php
  $substring = substr('', , );
  echo $substring;
  ```

- **`Random Integer`**
  Prefix: `rint`
  Description: Generates a random integer between min and max values.

  ```php
  $min = "";
  $max = "";
  $randomInt = rand($min, $max);
  echo $randomInt;
  ```

- **`String Length`**
  Prefix: `strlen`
  Description: Calculates the length of a string.

  ```php
  $length = strlen('');
  echo 'String length: ' . $length;
  ```

- **`File Modification Time`**
  Prefix: `filemtime`
  Description: Gets the last modification time of a file.

  ```php
  $mtime = filemtime('');
  echo 'File last modified: ' . date('Y-m-d H:i:s', $mtime);
  ```

- **`Validate Integer`**
  Prefix: `vint`
  Description: Validates if a value is an integer.

  ```php
  $number = '';
  if (filter_var($number, FILTER_VALIDATE_INT) !== false) {
    echo 'Valid integer';
  } else {
    echo 'Invalid integer';
  }
  ```

- **`For loop`**
  Prefix: `for`
  Description: Creates a for loop.

  ```php
  for($i = 0, $i < condition, $i ++)
  {
  echo $i;
  }
  ```

- **`Constructor method`**
  Prefix: `_c`
  Description: Creates a constructor method.

  ```php
  public function __construct($parameters)
  {

  }
  ```

- **`Error Logging`**
  Prefix: `errorlog`
  Description: Logs errors to the PHP error log file.

  ```php
  if (!$result) {
    error_log('Error: ' . mysqli_error($conn));
  }
  ```

- **`Custom Error Handler`**
  Prefix: `errorCustom`
  Description: Sets a custom error handler function.

  ```php
  function customError($errno, $errstr, $errfile, $errline) {
    echo "Error: [$errno] $errstr - $errfile:$errline\n";
    // You can also log errors or handle them differently here
  }
  set_error_handler('customError');

  // Example usage
  $result = someFunction();
  if (!$result) {
    trigger_error('Something went wrong!', E_USER_ERROR);
  }
  ```

- **`Shorthand If Statement`**
  Prefix: `?if`
  Description: Shorthand if statement (ternary operator) for concise conditional assignments.

  ```php
  $result = $condition ? '$trueValue' : '$falseValue';
  ```

- **`Nested If Statements`**
  Prefix: `iif`
  Description: Creates nested if statements for more complex conditional logic.

  ```php
  if ($condition1) {
    if ($condition2) {
      // Code for condition2
    } else {
      // Code for the else case of condition2
    }
  } else {
    // Code for the else case of condition1
  }
  ```

- **`Switch Statement`**
  Prefix: `switch`
  Description: Creates a switch statement with multiple cases.

  ```php
  switch ($expression) {
    case $label1:
      // Code block for label1
      break;
    case $label2:
      // Code block for label2
      break;
    case $label3:
      // Code block for label3
      break;
    default:
      // Code block for default case
  }
  ```

- **`Do-While Loop`**
  Prefix: `dowhile`
  Description: Creates a do-while loop in PHP.

  ```php
  do {
    // Code block to execute
  } while ($condition);
  ```

- **`While Loop`**
  Prefix: `while`
  Description: Creates a while loop in PHP.

  ```php
  while ($condition) {
    // Code block to execute
  }
  ```

- **`Array Splice`**
  Prefix: `arr_splice`
  Description: Modifies an array by removing or replacing elements.

  ```php
  $array = [/* array elements */];
  array_splice($array, $offset, $length, $replacement);
  // $array now contains the modified array
  ```

- **`Multidimensional Arrays`**
  Prefix: `multiarr`
  Description: Defines and accesses elements in a multidimensional array.

  ```php
  $array = [
    ["key1" => "value1", "key2" => "value2"],
    ["key1" => "value3", "key2" => "value4"],
    ["key1" => "value5", "key2" => "value6"]
  ];

  // Accessing an element
  $element = $array[0]["key1"]; // $element is "value1"

  // Loop through multidimensional array
  foreach ($array as $subArray) {
    foreach ($subArray as $key => $value) {
      echo "$key: $value\n";
    }
  }
  ```

- **`Array Functions`**
  Prefix: `arrfunc`
  Description: Common PHP array functions and their usage.

  ```php
  // array_merge - Merges one or more arrays
  $mergedArray = array_merge($array1, $array2);

  // array_diff - Computes the difference of arrays
  $diffArray = array_diff($array1, $array2);

  // array_filter - Filters elements of an array using a callback function
  $filteredArray = array_filter($array, function($value) {
    return $value > 10;
  });

  // array_map - Applies a callback function to each element of the array
  $mappedArray = array_map(function($value) {
    return $value * 2;
  }, $array);

  // array_reduce - Iteratively reduces the array to a single value using a callback function
  $sum = array_reduce($array, function($carry, $item) {
    return $carry + $item;
  }, 0);

  // in_array - Checks if a value exists in an array
  $exists = in_array($value, $array);

  // array_key_exists - Checks if the given key or index exists in the array
  $exists = array_key_exists('key', $array);

  // array_slice - Extracts a slice of the array
  $slice = array_slice($array, 1, 3); // Extracts 3 elements starting from index 1

  // array_splice - Removes and returns a portion of the array
  $spliced = array_splice($array, 2, 2); // Removes 2 elements starting from index 2

  // sort - Sorts an array
  sort(array); // Sorts the array in ascending order
  ```

- **`Multiple Insert PDO`**
  Prefix: `pdoim`
  Description: Performs multiple inserts into a database using PDO.

  ```php
  $pdo = new PDO('mysql:host=;dbname=', '', '');
  $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

  $sql = 'INSERT INTO tableName (column1, column2, column3) VALUES (?, ?, ?)';
  $stmt = $pdo->prepare($sql);

  $data = [
      [, , ],
      [, , ],
      // Add more rows as needed
  ];

  foreach ($data as $row) {
      $stmt->execute($row);
  }

  echo 'Records inserted successfully';
  ```

# SnipGenius includes the following Javascript snippets:

- **`Alert Message`**  
   Prefix: `alert`

  ```javascript
  alert("");
  ```

- **`Prompt User`**  
   Prefix: `prompt`

  ```javascript
  const input = prompt("");
  console.log(input);
  ```

- **`Declare Variable`**  
   Prefix: `let`

  ```javascript
  let name = ;
  ```

- **`Function Declaration`**  
   Prefix: `func`

  ```javascript
  function functionName(params) {}
  ```

- **`Arrow Function`**  
   Prefix: `arrow`

- **`For Loop`**  
   Prefix: `for`

  ```javascript
  for (let i = 0; i < ; i++) {

  }
  ```

- **`While Loop`**  
   Prefix: `while`

  ```javascript
  let i = 0;
  while (condition) {
    i++;
  }
  ```

- **`Switch Statement`**  
   Prefix: `switch`

  ```javascript
  switch (variable) {
    case :

      break;
  case :

  break
    default:

  }
  ```

- **`Try-Catch`**  
   Prefix: `trycatch`

  ```javascript
  try {
  } catch (error) {
    console.error(error);
  }
  ```

- **`Object Declaration`**  
   Prefix: `object`

  ```javascript
  const name = {
    key1: "",
    key2: "",
  };
  ```

- **`Array Declaration`**  
   Prefix: `array`

  ```javascript
  const name = ["", "", ""];
  ```

- **`Date Object`**  
   Prefix: `date`

  ```javascript
  const date = new Date("");
  console.log(date);
  ```

- **`Fetch API Request`**  
   Prefix: `fetch`

  ```javascript
  fetch("url")
    .then((response) => response.json())
    .then((data) => {
      console.log(data);
    })
    .catch((error) => {
      console.error("Error:", error);
    });
  ```

- **`Local Storage Get Item`**  
   Prefix: `getlocal`

  ```javascript
  const value = localStorage.getItem("key");
  console.log(value);
  ```

- **`Local Storage Set Item`**  
   Prefix: `setlocal`

  ```javascript
  localStorage.setItem("key", "value");
  ```

- **`Session Storage Get Item`**  
   Prefix: `getsession`

  ```javascript
  const value = sessionStorage.getItem("key");
  console.log(value);
  ```

- **`Session Storage Set Item`**  
   Prefix: `setsession`

  ```javascript
  sessionStorage.setItem("key", "value");
  ```

- **`Event Listener`**  
   Prefix: `addevent`

  ```javascript
  element.addEventListener("event", (e) => {});
  ```

- **`Debounce Function`**  
   Prefix: `debounce`

  ```javascript
  function debounce(func, delay) {
    let timer;
    return function (...args) {
      clearTimeout(timer);
      timer = setTimeout(() => func.apply(this, args), delay);
    };
  }
  ```

- **`Generate UUID`**  
   Prefix: `uuid`

  ```javascript
  function generateUUID() {
    return "xxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx".replace(/[xy]/g, function (c) {
      const r = (Math.random() * 16) | 0,
        v = c === "x" ? r : (r & 0x3) | 0x8;
      return v.toString(16);
    });
  }
  ```

- **`Array Contains`**  
   Prefix: `includes`

  ```javascript
  const result = array.includes();
  ```

- **`Fetch Data with Error Handling`**  
   Prefix: `fetchError`

  ```javascript
  async function fetchData(url) {
    try {
      const response = await fetch(url);
      if (!response.ok) throw new Error("Network response was not ok");
      return await response.json();
    } catch (error) {
      console.error("Fetch error:", error);
    }
  }
  ```

- **`Check Array Duplicates`**  
   Prefix: `hasDup`

  ```javascript
  function hasDuplicates(array) {
    return new Set(array).size !== array.length;
  }
  ```

- **`Form Data to Object`**  
   Prefix: `form:Obj`

  ```javascript
  function formDataToObject(formData) {
    const obj = {};
    formData.forEach((value, key) => {
      obj[key] = value;
    });
    return obj;
  }
  ```

- **`Capitalize Words`**  
   Prefix: `captWords`

  ```javascript
  function capitalizeWords(str) {
    return str.toLowerCase().replace(/\b\w/g, (char) => char.toUpperCase());
  }
  ```

- **`Check Palindrome`**  
   Prefix: `isPalindrome`

  ```javascript
  function isPalindrome(str) {
    const cleaned = str.toLowerCase().replace(/[^a-z0-9]/g, "");
    return cleaned === cleaned.split("").reverse().join("");
  }
  ```

- **`Format Currency`**  
   Prefix: `formatCurrency`

  ```javascript
  function formatCurrency(amount, currency = "USD") {
    return new Intl.NumberFormat("en-US", {
      style: "currency",
      currency: currency,
    }).format(amount);
  }
  ```

- **`AJAX Request with XMLHttpRequest`**  
   Prefix: `ajaxXml`

  ```javascript
  function fetchData(url, callback) {
    const xhr = new XMLHttpRequest();
    xhr.open("GET", url, true);
    xhr.onload = function () {
      if (xhr.status >= 200 && xhr.status < 300) {
        callback(null, JSON.parse(xhr.responseText));
      } else {
        callback(new Error("Request failed with status " + xhr.status));
      }
    };
    xhr.onerror = function () {
      callback(new Error("Network error"));
    };
    xhr.send();
  }
  ```

- **`jQuery AJAX GET Request`**  
   Prefix: `jqAjaxGet`

  ```javascript
  $.ajax({
    url: "http://example.com/api",
    type: "GET",
    success: function (data) {
      console.log(data);
    },
    error: function (xhr, status, error) {
      console.error("AJAX Error:", error);
    },
  });
  ```

- **`jQuery AJAX POST Request`**  
   Prefix: `jqAjaxPost`

  ```javascript
  $.ajax({
    url: "http://example.com/api",
    type: "POST",
    data: { key1: "value1", key2: "value2" },
    success: function (data) {
      console.log(data);
    },
    error: function (xhr, status, error) {
      console.error("AJAX Error:", error);
    },
  });
  ```

- **`jQuery AJAX`**  
   Prefix: `jqAjax`

  ```javascript
  $.ajax({
    url: "http://example.com/api",
    type: "GET",
    dataType: "json",
    success: function (data) {
      console.log(data);
    },
    error: function (xhr, status, error) {
      console.error("AJAX Error:", error);
    },
  });
  ```

- **`jQuery AJAX Request with Headers`**  
   Prefix: `jqAjaxHeaders`

  ```javascript
  $.ajax({
    url: "http://example.com/api",
    type: "GET",
    headers: {
      Authorization: "Bearer token",
      "Another-Header": "HeaderValue",
    },
    success: function (data) {
      console.log(data);
    },
    error: function (xhr, status, error) {
      console.error("AJAX Error:", error);
    },
  });
  ```

- **`Select Element by ID`**  
   Prefix: `selectId`

  ```javascript
  const element = document.getElementById("elementId");
  ```

- **`Select Elements by Class Name`**  
   Prefix: `selectClass`

  ```javascript
  const elements = document.getElementsByClassName("className");
  ```

- **`Select Elements by Tag Name`**  
   Prefix: `selectTag`

  ```javascript
  const elements = document.getElementsByTagName("tagName");
  ```

- **`Select Single Element by Query Selector`**  
   Prefix: `selectQuery`

  ```javascript
  const element = document.querySelector("selector");
  ```

- **`Select Multiple Elements by Query Selector`**  
   Prefix: `selectQueryAll`

  ```javascript
  const elements = document.querySelectorAll("selector");
  ```

- **`Create a New Element`**  
   Prefix: `crte`

  ```javascript
  const newElement = document.createElement("tagName");
  ```

- **`Append Element to Parent`**  
   Prefix: `apdc`

  ```javascript
  const parentElement = document.querySelector("parentSelector");
  const childElement = document.createElement("childTag");
  parentElement.appendChild(childElement);
  ```

- **`Remove Element`**  
   Prefix: `rmve`

  ```javascript
  const element = document.querySelector("selector");
  if (element) {
    element.remove();
  }
  ```

- **`Set Element Text Content`**  
   Prefix: `setText`

  ```javascript
  const element = document.querySelector("selector");
  if (element) {
    element.textContent = "text";
  }
  ```

- **`Set Element HTML Content`**  
   Prefix: `setHTML`

  ```javascript
  const element = document.querySelector("selector");
  if (element) {
    element.innerHTML = "html";
  }
  ```

- **`Generate Random Number`**  
   Prefix: `randNum`

  ```javascript
  const randomNum = Math.floor(Math.random() * (max - min + 1)) + min;
  ```

- **`Check for Empty Object`**  
   Prefix: `isEmptyObject`

  ```javascript
  function isEmptyObject(obj) {
    return Object.keys(obj).length === 0 && obj.constructor === Object;
  }
  ```

- **`Merge Objects`**  
   Prefix: `mergeObj`

  ```javascript
  const merged = Object.assign({}, obj1, obj2);
  ```

- **`Clone Array`**  
   Prefix: `cloneArray`

  ```javascript
  const clonedArray = [...originalArray];
  ```

- **`Form Data to JSON`**  
   Prefix: `form:JSON`

  ```javascript
  function formDataToJSON(formData) {
    const obj = {};
    formData.forEach((value, key) => {
      obj[key] = value;
    });
    return obj;
  }

  const form = document.querySelector("formSelector");
  const formData = new FormData(form);
  const jsonData = formDataToJSON(formData);
  ```

- **`Add CSS Class to Element`**  
   Prefix: `addClass`

  ```javascript
  const element = document.querySelector("selector");
  if (element) {
    element.classList.add("className");
  }
  ```

- **`Remove CSS Class from Element`**  
   Prefix: `removeClass`

  ```javascript
  const element = document.querySelector("selector");
  if (element) {
    element.classList.remove("className");
  }
  ```

- **`Toggle CSS Class on Element`**  
   Prefix: `toggleClass`

  ```javascript
  const element = document.querySelector("selector");
  if (element) {
    element.classList.toggle("className");
  }
  ```

- **`Convert NodeList to Array`**  
   Prefix: `nla`

  ```javascript
  const array = Array.from(document.querySelectorAll("selector"));
  ```

- **`Get URL Parameters`**  
   Prefix: `gup`

  ```javascript
  function getURLParams() {
    const params = new URLSearchParams(window.location.search);
    const obj = {};
    params.forEach((value, key) => {
      obj[key] = value;
    });
    return obj;
  }

  const queryParams = getURLParams();
  ```

- **`Arrow Function with Implicit Return`**  
   Prefix: `afi`

  ```javascript
  const functionName = (parameters) => expression;
  ```

- **`Arrow Function for Array map`**  
   Prefix: `map`

  ```javascript
  array.map((elements) => {
    // transform element
  });
  ```

- **`Arrow Function for Array filter`**  
   Prefix: `faf`

  ```javascript
  array.filter((element) => {
    // condition
  });
  ```

- **`Arrow Function for Array reduce`**  
   Prefix: `raf`

  ```javascript
  array.reduce((accumulator, currentValue) => {
    // calculation
  }, initialValue);
  ```

- **`Arrow Function with Object Destructuring`**  
   Prefix: `afd`

  ```javascript
  const functionName = ({ prop1, prop2 }) => {
    // function body
  };
  ```

- **`Arrow Function with Array Destructuring`**  
   Prefix: `afad`

  ```javascript
  const functionName = ([element1, element2]) => {
    // function body
  };
  ```

- **`Arrow Function for Event Listener`**  
   Prefix: `ael`

  ```javascript
  document.querySelector("selector").addEventListener("event", (event) => {
    // handler code
  });
  ```

- **`Import`**  
   Prefix: `imp`

  ```javascript
  import moduleName from "module";
  ```

- **`Import Destructing`**  
   Prefix: `imd`

  ```javascript
  import {} from "module";
  ```

- **`Import Everything`**  
   Prefix: `ime`

  ```javascript
  import * as alias from "module";
  ```

- **`Import As`**  
   Prefix: `ima`

  ```javascript
  import { originalName as alias } from "module";
  ```

- **`Require`**  
   Prefix: `rqr`

  ```javascript
  require("package");
  ```

- **`Require to Const`**  
   Prefix: `req`

  ```javascript
  const packageName = require("packageName");
  ```

- **`Module Exports`**  
   Prefix: `mde`

  ```javascript
  module.exports = {};
  ```

- **`Export Named Variable`**  
   Prefix: `env`

  ```javascript
  export const exportVariable = localVariable;
  ```

- **`Export Named Function`**  
   Prefix: `enf`

  ```javascript
  export const functionName = (params) => {};
  ```

- **`Export Default Function`**  
   Prefix: `edf`

  ```javascript
  export default function test(params) {}
  ```

- **`Export Class`**  
   Prefix: `ecl`

  ```javascript
  export default class className {}
  ```

- **`Export Class Extends`**  
   Prefix: `ece`

  ```javascript
  export default class className extends baseClassName {}
  ```

- **`Constructor`**  
   Prefix: `_c`

  ```javascript
  constructor(params) {

  }
  ```

- **`Method`**  
   Prefix: `met`

  ```javascript
  methodName(params) {

  }
  ```

- **`Property Get`**  
   Prefix: `pge`

  ```javascript
  get propertyName() {
    return this.;
  }
  ```

- **`Property Set`**  
   Prefix: `pse`

  ```javascript
  set propertyName(value) {
    ;
  }
  ```

- **`For In`**  
   Prefix: `forin`

  ```javascript
  for (const item in object) {
  }
  ```

- **`Anonymous Function`**  
   Prefix: `anfn`

  ```javascript
  (params) => {};
  ```

- **`Named Function`**  
   Prefix: `nfn`

  ```javascript
  const name = (params) => {};
  ```

- **`Destructing Object`**  
   Prefix: `dob`

  ```javascript
  const { propertyName } = objectToDestruct;
  ```

- **`Destructing Array`**  
   Prefix: `dar`

  ```javascript
  const [propertyName] = arrayToDestruct;
  ```

- **`Set Interval`**  
   Prefix: `sti`

  ```javascript
  setInterval(() => {}, intervalInMs);
  ```

- **`Set Timeout`**  
   Prefix: `sto`

  ```javascript
  setTimeout(() => {}, delayInMs);
  ```

- **`Promise`**  
   Prefix: `prom`

  ```javascript
  return new Promise((resolve, reject) => {});
  ```

- **`Then Catch`**  
   Prefix: `thenc`

  ```javascript
  .then((result) => {

  }).catch((err) => {

  });
  ```

- **`Console Assert`**  
   Prefix: `cas`

  ```javascript
  console.assert(expression, object);
  ```

- **`Console Clear`**  
   Prefix: `ccl`

  ```javascript
  console.clear();
  ```

- **`Console Count`**  
   Prefix: `cco`

  ```javascript
  console.count(label);
  ```

- **`Console Debug`**  
   Prefix: `cdb`

  ```javascript
  console.debug(object);
  ```

- **`Console Dir`**  
   Prefix: `cdi`

  ```javascript
  console.dir(object);
  ```

- **`Console Error`**  
   Prefix: `cer`

  ```javascript
  console.error(object);
  ```

- **`Console Group`**  
   Prefix: `cgr`

  ```javascript
  console.group("label");
  ```

- **`Console Group End`**  
   Prefix: `cge`

  ```javascript
  console.groupEnd();
  ```

- **`Console Log`**  
   Prefix: `clg`

  ```javascript
  console.log(object);
  ```

- **`Console Log Object`**  
   Prefix: `clgo`

  ```javascript
  console.log("object :>> ", object);
  ```

- **`Console Trace`**  
   Prefix: `ctr`

  ```javascript
  console.trace(object);
  ```

- **`Console Warn`**  
   Prefix: `cwa`

  ```javascript
  console.warn(object);
  ```

- **`Console Table`**  
   Prefix: `clt`

  ```javascript
  console.table(object);
  ```

- **`Console Time`**  
   Prefix: `cti`

  ```javascript
  console.time(label);
  ```

- **`Console Time End`**  
   Prefix: `cte`

  ```javascript
  console.timeEnd(label);
  ```

- **`Object Destructuring`**  
   Prefix: `obd`

  ```javascript
  const { prop1, prop2 } = object;
  ```

- **`Nested Object Destructuring`**  
   Prefix: `nobd`

  ```javascript
  const {
    prop1: { nestedProp1, nestedProp2 },
  } = object;
  ```

- **`Array Destructuring`**  
   Prefix: `ard`

  ```javascript
  const [item1, item2] = array;
  ```

- **`Nested Array Destructuring`**  
   Prefix: `nard`

  ```javascript
  const [item1, [nestedItem1, nestedItem2]] = array;
  ```

# SnipGenius includes the following html, Bootstrap snippets:

- **`Input`**  
   Prefix: `inp`

  ```html
  <input type="" placeholder="" />
  ```

- **`Label`**  
   Prefix: `label`

  ```html
  <label for=""></label>
  ```

- **`HTML Table`**  
   Prefix: `table`

  ```html
  <table class="table">
    <thead>
      <tr>
        <th>Header 1</th>
        <th>Header 2</th>
        <th>Header 3</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Row 1, Cell 1</td>
        <td>Row 1, Cell 2</td>
        <td>Row 1, Cell 3</td>
      </tr>
      <tr>
        <td>Row 2, Cell 1</td>
        <td>Row 2, Cell 2</td>
        <td>Row 2, Cell 3</td>
      </tr>
    </tbody>
  </table>
  ```

- **`HTML Boilerplate`**  
   Prefix: `html`

  ```html
  <!DOCTYPE html>
  <html lang="en">
    <head>
      <meta charset="UTF-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <title></title>
    </head>
    <body></body>
  </html>
  ```

- **`video`**  
   Prefix: `video`

  ```html
  <video controls>
    <source src="" type="video/mp4" />
    Your browser does not support the video tag.
  </video>
  ```

- **`Basic Bootstrap Boilerplate`**  
   Prefix: `bootstrap`

  ```html
  <!DOCTYPE html>
  <html lang="en">
    <head>
      <meta charset="UTF-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <title>Document</title>
      <link
        rel="stylesheet"
        href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css"
      />
    </head>
    <body>
      <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
      <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.1/dist/umd/popper.min.js"></script>
      <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
    </body>
  </html>
  ```

- **`Bootstrap Container`**  
   Prefix: `container`

  ```html
  <div class="container">// content here</div>
  ```

- **`Bootstrap Row and Columns`**  
   Prefix: `row-cols`

  ```html
  <div class="container">
    <div class="row">
      <div class="col-sm|md|lg|xl">Column 1</div>
      <div class="col-sm|md|lg|xl">Column 2</div>
      <div class="col-sm|md|lg|xl">Column 3</div>
    </div>
  </div>
  ```

- **`Bootstrap Navbar`**  
   Prefix: `navbar`

  ```html
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="#">Brand</a>
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarNav"
      aria-controls="navbarNav"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item active">
          <a class="nav-link" href="#"
            >Home <span class="sr-only">(current)</span></a
          >
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Features</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Pricing</a>
        </li>
      </ul>
    </div>
  </nav>
  ```

- **`Bootstrap Card`**  
   Prefix: `card`

  ```html
  <div class="card" style="width: 18rem;">
    <img src="https://via.placeholder.com/150" class="card-img-top" alt="..." />
    <div class="card-body">
      <h5 class="card-title">Card title</h5>
      <p class="card-text">
        Some quick example text to build on the card title and make up the bulk
        of the card's content.
      </p>
      <a href="#" class="btn btn-primary">Go somewhere</a>
    </div>
  </div>
  ```

- **`Bootstrap Modal`**  
   Prefix: `modal`

  ```html
  <div
    class="modal fade"
    id="exampleModal"
    tabindex="-1"
    role="dialog"
    aria-labelledby="exampleModalLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
          <button
            type="button"
            class="close"
            data-dismiss="modal"
            aria-label="Close"
          >
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
        <div class="modal-body">Modal body text goes here.</div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary" data-dismiss="modal">
            Close
          </button>
          <button type="button" class="btn btn-primary">Save changes</button>
        </div>
      </div>
    </div>
  </div>
  ```

- **`Bootstrap Grid System`**  
   Prefix: `grid`

  ```html
  <div class="container">
    <div class="row">
      <div class="col-sm|md|lg|xl">Column 1</div>
      <div class="col-sm|md|lg|xl">Column 2</div>
      <div class="col-sm|md|lg|xl">Column 3</div>
    </div>
  </div>
  ```

- **`Bootstrap Alert`**  
   Prefix: `alert`

  ```html
  <div class="alert alert-success|info|warning|danger" role="alert">
    This is a success|info|warning|danger alert—check it out!
  </div>
  ```

- **`Bootstrap List Group`**  
   Prefix: `listGroup`

  ```html
  <ul class="list-group">
    <li class="list-group-item">First item</li>
    <li class="list-group-item">Second item</li>
    <li class="list-group-item">Third item</li>
  </ul>
  ```

- **`Bootstrap Breadcrumb`**  
   Prefix: `breadcrumb`

  ```html
  <nav aria-label="breadcrumb">
    <ol class="breadcrumb">
      <li class="breadcrumb-item"><a href="#">Home</a></li>
      <li class="breadcrumb-item active" aria-current="page">Library</li>
    </ol>
  </nav>
  ```

- **`Bootstrap Carousel`**  
   Prefix: `carousel`

  ```html
  <div
    id="carouselExampleIndicators"
    class="carousel slide"
    data-ride="carousel"
  >
    <ol class="carousel-indicators">
      <li
        data-target="#carouselExampleIndicators"
        data-slide-to="0"
        class="active"
      ></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="2"></li>
    </ol>
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img
          src="https://via.placeholder.com/800x400"
          class="d-block w-100"
          alt="..."
        />
        <div class="carousel-caption d-none d-md-block">
          <h5>First slide label</h5>
          <p>Some representative placeholder content for the first slide.</p>
        </div>
      </div>
      <div class="carousel-item">
        <img
          src="https://via.placeholder.com/800x400"
          class="d-block w-100"
          alt="..."
        />
        <div class="carousel-caption d-none d-md-block">
          <h5>Second slide label</h5>
          <p>Some representative placeholder content for the second slide.</p>
        </div>
      </div>
      <div class="carousel-item">
        <img
          src="https://via.placeholder.com/800x400"
          class="d-block w-100"
          alt="..."
        />
        <div class="carousel-caption d-none d-md-block">
          <h5>Third slide label</h5>
          <p>Some representative placeholder content for the third slide.</p>
        </div>
      </div>
    </div>
    <a
      class="carousel-control-prev"
      href="#carouselExampleIndicators"
      role="button"
      data-slide="prev"
    >
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="sr-only">Previous</span>
    </a>
    <a
      class="carousel-control-next"
      href="#carouselExampleIndicators"
      role="button"
      data-slide="next"
    >
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="sr-only">Next</span>
    </a>
  </div>
  ```

- **`Bootstrap Jumbotron`**  
   Prefix: `jumbotron`

  ```html
  <div class="jumbotron">
    <h1 class="display-4">Hello, world!</h1>
    <p class="lead">
      This is a simple hero unit, a simple jumbotron-style component for calling
      extra attention to featured content or information.
    </p>
    <hr class="my-4" />
    <p>
      It uses utility classes for typography and spacing to space content out
      within the larger container.
    </p>
    <a class="btn btn-primary btn-lg" href="#" role="button">Learn more</a>
  </div>
  ```

- **`Bootstrap Pagination`**  
   Prefix: `pagination`

  ```html
  <nav aria-label="Page navigation">
    <ul class="pagination">
      <li class="page-item">
        <a class="page-link" href="#" aria-label="Previous">
          <span aria-hidden="true">&laquo;</span>
        </a>
      </li>
      <li class="page-item"><a class="page-link" href="#">1</a></li>
      <li class="page-item"><a class="page-link" href="#">2</a></li>
      <li class="page-item"><a class="page-link" href="#">3</a></li>
      <li class="page-item">
        <a class="page-link" href="#" aria-label="Next">
          <span aria-hidden="true">&raquo;</span>
        </a>
      </li>
    </ul>
  </nav>
  ```

- **`Bootstrap Tooltip`**  
   Prefix: `tooltip`

  ```html
  <button
    type="button"
    class="btn btn-secondary"
    data-toggle="tooltip"
    data-placement="top"
    title="Tooltip text"
  >
    Hover me to see tooltip
  </button>

  <script>
    $(function () {
      $('[data-toggle="tooltip"]').tooltip();
    });
  </script>
  ```

- **`Bootstrap Form Inline`**  
   Prefix: `formInline`

  ```html
  <form class="form-inline">
    <label class="sr-only" for="inputEmail3">Email</label>
    <input
      type="email"
      class="form-control mb-2 mr-sm-2"
      id="inputEmail3"
      placeholder="Email"
    />
    <label class="sr-only" for="inputPassword3">Password</label>
    <input
      type="password"
      class="form-control mb-2 mr-sm-2"
      id="inputPassword3"
      placeholder="Password"
    />
    <div class="form-check mb-2 mr-sm-2">
      <input class="form-check-input" type="checkbox" id="check1" />
      <label class="form-check-label" for="check1">Remember me</label>
    </div>
    <button type="submit" class="btn btn-primary mb-2">Submit</button>
  </form>
  ```

- **`Bootstrap Toast`**  
   Prefix: `toast`

  ```html
  <div aria-live="polite" aria-atomic="true" class="position-relative">
    <div class="toast" role="alert" aria-live="assertive" aria-atomic="true">
      <div class="toast-header">
        <strong class="mr-auto">Bootstrap</strong>
        <small>11 mins ago</small>
        <button
          type="button"
          class="ml-2 mb-1 close"
          data-dismiss="toast"
          aria-label="Close"
        >
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="toast-body">Hello, world! This is a toast message.</div>
    </div>
  </div>

  <script>
    $(function () {
      $(".toast").toast("show");
    });
  </script>
  ```

- **`Bootstrap Offcanvas`**  
   Prefix: `offcanvas`

  ```html
  <div
    class="offcanvas offcanvas-start|end|top|bottom"
    tabindex="-1"
    id="offcanvasExample"
    aria-labelledby="offcanvasLabel"
  >
    <div class="offcanvas-header">
      <h5 class="offcanvas-title" id="offcanvasLabel">Offcanvas title</h5>
      <button
        type="button"
        class="btn-close"
        data-bs-dismiss="offcanvas"
        aria-label="Close"
      ></button>
    </div>
    <div class="offcanvas-body">Your content here.</div>
  </div>

  <button
    class="btn btn-primary"
    type="button"
    data-bs-toggle="offcanvas"
    data-bs-target="#offcanvasExample"
    aria-controls="offcanvasExample"
  >
    Toggle Offcanvas
  </button>
  ```

- **`Bootstrap Toast with Header`**  
   Prefix: `toastHeader`

  ```html
  <div class="toast" role="alert" aria-live="assertive" aria-atomic="true">
    <div class="toast-header">
      <strong class="mr-auto">Notification</strong>
      <small>Just now</small>
      <button
        type="button"
        class="ml-2 mb-1 close"
        data-dismiss="toast"
        aria-label="Close"
      >
        <span aria-hidden="true">&times;</span>
      </button>
    </div>
    <div class="toast-body">
      Here is some text to show in the body of the toast.
    </div>
  </div>

  <script>
    $(function () {
      $(".toast").toast("show");
    });
  </script>
  ```

- **`Bootstrap Accordion`**  
   Prefix: `accordion`

  ```html
  <div id="accordionExample" class="accordion" id="accordionExample">
    <div class="accordion-item">
      <h2 class="accordion-header" id="headingOne">
        <button
          class="accordion-button"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#collapseOne"
          aria-expanded="true"
          aria-controls="collapseOne"
        >
          Accordion Item #1
        </button>
      </h2>
      <div
        id="collapseOne"
        class="accordion-collapse collapse show"
        aria-labelledby="headingOne"
        data-bs-parent="#accordionExample"
      >
        <div class="accordion-body">Content for the first accordion item.</div>
      </div>
    </div>
    <div class="accordion-item">
      <h2 class="accordion-header" id="headingTwo">
        <button
          class="accordion-button collapsed"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#collapseTwo"
          aria-expanded="false"
          aria-controls="collapseTwo"
        >
          Accordion Item #2
        </button>
      </h2>
      <div
        id="collapseTwo"
        class="accordion-collapse collapse"
        aria-labelledby="headingTwo"
        data-bs-parent="#accordionExample"
      >
        <div class="accordion-body">Content for the second accordion item.</div>
      </div>
    </div>
  </div>
  ```

- **`Bootstrap Floating Labels`**  
   Prefix: `floatingLabel`

  ```html
  <div class="form-floating">
    <input
      type="text"
      class="form-control"
      id="inputId"
      placeholder="Placeholder"
    />
    <label for="inputId">Label</label>
  </div>
  ```

- **`Bootstrap Placeholders`**  
   Prefix: `placeholder`

  ```html
  <div class="placeholder-lg|md|sm">Placeholder content goes here.</div>
  ```

- **`Bootstrap Grid System with Nested Columns`**  
   Prefix: `nestedGrid`

  ```html
  <div class="container">
    <div class="row">
      <div class="col-md-6">
        <div class="row">
          <div class="col-6">Nested Column 1</div>
          <div class="col-6">Nested Column 2</div>
        </div>
      </div>
      <div class="col-md-6">Column 2</div>
    </div>
  </div>
  ```

- **`Bootstrap Responsive Embed`**  
   Prefix: `embedResponsive`

  ```html
  <div class="embed-responsive embed-responsive-16by9">
    <iframe
      class="embed-responsive-item"
      src="https://www.youtube.com/embed/tgbNymZ7vqY"
      allowfullscreen
    ></iframe>
  </div>
  ```

- **`Bootstrap Media Object`**  
   Prefix: `media`

  ```html
  <div class="media">
    <img src="https://example.com/64" class="mr-3" alt="image" />
    <div class="media-body">
      <h5 class="mt-0">Media heading</h5>
      Some quick example text to build on the media heading and make up the bulk
      of the media body.
    </div>
  </div>
  ```

- **`Bootstrap Spinner`**  
   Prefix: `spinner`

  ```html
  <div class="spinner-border text-primary" role="status">
    <span class="sr-only">Loading...</span>
  </div>
  ```

- **`Bootstrap Login Form`**  
   Prefix: `formLogin`

  ```html
  <div class="container">
    <div class="row justify-content-center">
      <div class="col-md-6">
        <div class="card">
          <div class="card-header">Login</div>
          <div class="card-body">
            <form>
              <div class="form-group">
                <label for="email">Email address</label>
                <input
                  type="email"
                  class="form-control"
                  id="email"
                  placeholder="Enter email"
                  required
                />
              </div>
              <div class="form-group">
                <label for="password">Password</label>
                <input
                  type="password"
                  class="form-control"
                  id="password"
                  placeholder="Password"
                  required
                />
              </div>
              <button type="submit" class="btn btn-primary">Login</button>
              <div class="form-check mt-2">
                <input
                  type="checkbox"
                  class="form-check-input"
                  id="rememberMe"
                />
                <label class="form-check-label" for="rememberMe"
                  >Remember me</label
                >
              </div>
            </form>
          </div>
          <div class="card-footer text-muted">
            <a href="#">Forgot password?</a>
          </div>
        </div>
      </div>
    </div>
  </div>
  ```

- **`Bootstrap Registration Form`**  
   Prefix: `formRegistration`

  ```html
  <div class="container">
    <div class="row justify-content-center">
      <div class="col-md-8">
        <div class="card">
          <div class="card-header">Register</div>
          <div class="card-body">
            <form>
              <div class="form-group">
                <label for="name">Full Name</label>
                <input
                  type="text"
                  class="form-control"
                  id="name"
                  placeholder="Enter your full name"
                  required
                />
              </div>
              <div class="form-group">
                <label for="email">Email address</label>
                <input
                  type="email"
                  class="form-control"
                  id="email"
                  placeholder="Enter email"
                  required
                />
              </div>
              <div class="form-group">
                <label for="password">Password</label>
                <input
                  type="password"
                  class="form-control"
                  id="password"
                  placeholder="Password"
                  required
                />
              </div>
              <div class="form-group">
                <label for="confirmPassword">Confirm Password</label>
                <input
                  type="password"
                  class="form-control"
                  id="confirmPassword"
                  placeholder="Confirm Password"
                  required
                />
              </div>
              <button type="submit" class="btn btn-primary">Register</button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
  ```

- **`Bootstrap File Upload Form`**  
   Prefix: `formfile`

  ```html
  <div class="container">
    <div class="row justify-content-center">
      <div class="col-md-6">
        <div class="card">
          <div class="card-header">File Upload</div>
          <div class="card-body">
            <form>
              <div class="form-group">
                <label for="fileUpload">Choose file</label>
                <input
                  type="file"
                  class="form-control-file"
                  id="fileUpload"
                  required
                />
              </div>
              <button type="submit" class="btn btn-primary">Upload</button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
  ```

- **`Bootstrap Responsive Image`**  
   Prefix: `imgresponsive`

  ```html
  <img src="#" alt="Description" class="img-fluid" />
  ```

- **`Bootstrap Basic Table`**  
   Prefix: `table-basic`

  ```html
  <table class="table">
    <thead>
      <tr>
        <th>Header 1</th>
        <th>Header 2</th>
        <th>Header 3</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Row 1, Cell 1</td>
        <td>Row 1, Cell 2</td>
        <td>Row 1, Cell 3</td>
      </tr>
      <tr>
        <td>Row 2, Cell 1</td>
        <td>Row 2, Cell 2</td>
        <td>Row 2, Cell 3</td>
      </tr>
    </tbody>
  </table>
  ```

- **`Bootstrap Striped Table`**  
   Prefix: `table-striped`

  ```html
  <table class="table table-striped">
    <thead>
      <tr>
        <th>Header 1</th>
        <th>Header 2</th>
        <th>Header 3</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Row 1, Cell 1</td>
        <td>Row 1, Cell 2</td>
        <td>Row 1, Cell 3</td>
      </tr>
      <tr>
        <td>Row 2, Cell 1</td>
        <td>Row 2, Cell 2</td>
        <td>Row 2, Cell 3</td>
      </tr>
    </tbody>
  </table>
  ```

  - **`Bootstrap Bordered Table`**  
    Prefix: `table-bordered`

  ```html
  <table class="table table-bordered">
    <thead>
      <tr>
        <th>Header 1</th>
        <th>Header 2</th>
        <th>Header 3</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Row 1, Cell 1</td>
        <td>Row 1, Cell 2</td>
        <td>Row 1, Cell 3</td>
      </tr>
      <tr>
        <td>Row 2, Cell 1</td>
        <td>Row 2, Cell 2</td>
        <td>Row 2, Cell 3</td>
      </tr>
    </tbody>
  </table>
  ```

- **`Bootstrap Hoverable Table`**  
   Prefix: `table-hover`

  ```html
  <table class="table table-hover">
    <thead>
      <tr>
        <th>Header 1</th>
        <th>Header 2</th>
        <th>Header 3</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Row 1, Cell 1</td>
        <td>Row 1, Cell 2</td>
        <td>Row 1, Cell 3</td>
      </tr>
      <tr>
        <td>Row 2, Cell 1</td>
        <td>Row 2, Cell 2</td>
        <td>Row 2, Cell 3</td>
      </tr>
    </tbody>
  </table>
  ```

- **`Bootstrap Responsive Table`**  
   Prefix: `tableResponsive`

  ```html
  <div class="table-responsive">
    <table class="table">
      <thead>
        <tr>
          <th>Header 1</th>
          <th>Header 2</th>
          <th>Header 3</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Row 1, Cell 1</td>
          <td>Row 1, Cell 2</td>
          <td>Row 1, Cell 3</td>
        </tr>
        <tr>
          <td>Row 2, Cell 1</td>
          <td>Row 2, Cell 2</td>
          <td>Row 2, Cell 3</td>
        </tr>
      </tbody>
    </table>
  </div>
  ```

## Known Issues

There are no known issues at the moment. If you encounter any problems, please open an issue in the [GitHub repository](https://github.com/SISIYAM/SnipGenius--vs-code-extension.git).

## Contributing

Contributions are welcome! Please submit a pull request or open an issue in the [GitHub repository](https://github.com/SISIYAM/SnipGenius--vs-code-extension.git).

## License

This extension is licensed under the MIT License.

---

Enjoy using SnipGenius for your JavaScript,PHP and html development needs!
