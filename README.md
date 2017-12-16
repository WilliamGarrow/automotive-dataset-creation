# Automotive make/model dataset creation from Polk API

The original project needed to build an interface with various makes and automotive models. The provided API endpoints only allowed for data from a web browser. This solution allows for the collection of the necessary data via the index.php.

## Usage
From either localhost or a webserver load index.php which will load the getCarInfo.js script and build a list from relevant variables.
```php
var years=['1989','1990','1991','1992','1993','1994',
...

var makes = ['acura','alfa romeo','am general','amc', 
...
```

At the completion of the script, it will post the serialized data via save-ajax.php
```php
$put_array = array();
$saved = file_get_contents('cardata.ser');
...
$put_array[$_POST['year']][$_POST['make']] = $detail;
file_put_contents('cardata.ser',serialize($put_array));
```
