# BootstrapValidator

A jQuery plugin to validate form fields. Use with Bootstrap 3

## Features

* Built from scratch
* Many built-in [validators](#validators)

## Required

* [jQuery](http://jquery.com/)
* [Bootstrap 3](http://getbootstrap.com/)

## Demo

You can see the live demo here:

* [Sample demo](https://rawgithub.com/nghuuphuoc/bootstrapvalidate/master/demo/index.html)
* [Validator examples](https://rawgithub.com/nghuuphuoc/bootstrapvalidate/master/demo/validators.html)

## Usage

Since the bootstrapValidator plugin requires jQuery and Bootstrap 3, you have to include the required CSS and JS files to your page:

```html
<link rel="stylesheet" href="/path/to/bootstrap/css/bootstrap.css"/>
<link rel="stylesheet" href="/path/to/bootstrapValidator.min.css"/>

<script type="text/javascript" src="/path/to/jquery/jquery-1.10.2.min.js"></script>
<script type="text/javascript" src="/path/to/bootstrap/js/bootstrap.min.js"></script>
<script type="text/javascript" src="/path/to/bootstrapValidator.min.js"></script>
```

Call the plugin to validate the form as following:

```javascript
$(document).ready(function() {
    $(<form Selector>).bootstrapValidator({
        // The default error message for all fields
        // You can specify the error message for any fields
        message: ...,

        // The submit buttons selector
        // These buttons will be disabled when the form input are invalid
        submitButtons: ...,

        // The fields which need to be validated
        fields: {
            ...
            // The field name
            <fieldName>: {
                // The default error message for this field
                message: ...,

                // Array of validators
                validators: {
                    ...
                    <validatorName>: <validatorOptions>
                    ...
                }
            }
            ...
        }
    });
});
```

The ```<validatorName>``` can be the name of the built-in validator which are described in the [Validators](#validators) section

## Validators

Below is the list of built-in validators sorted in alphabetical order:

Validator name                          | Description
----------------------------------------|------------
[between](#between-validator)           | Check if the input value is between (strictly or not) two given numbers
digits                                  | Return true if the value contains only digits
emailAddress                            | Validate an email address
[greaterThan](#greaterthan-validator)   | Return true if the value is greater than or equals to given number
hexColor                                | Validate a hex color
[identical](#identical-validator)       | Check if the value is the same as one of particular field
[lessThan](#lessthan-validator)         | Return true if the value is less than or equals to given number
notEmpty                                | Check if the value is empty
[regexp](#regexp-validator)             | Check if the value matches given Javascript regular expression
[remote](#remote-validator)             | Perform remote checking via Ajax request
[stringLength](#stringlength-validator) | Validate the length of a string
uri                                     | Validate an URL address
usZipCode                               | Validate a US zip code

The validator options are described in the following section:

### Between Validator

Option name | Default | Description
------------|---------|------------
message     | n/a     | The error message
min         | n/a     | The lower value in the range. This option is required
max         | n/a     | The upper value in the range. This option is required
inclusive   | true    | Can be true or false. If true, the input value must be in the range strictly

### GreaterThan Validator

| Option name | Default | Description
|-------------|---------|------------
| message     | n/a     | The error message
| value       | n/a     | The number to make a comparison to. This option is required
| inclusive   | n/a     | Can be true or false
|             |         | If true, the input value must be greater than the comparison one
|             |         | If false, the input value must be greater than or equal to the comparison one

### Identical Validator

Option name | Default | Description
------------|---------|------------
message     | n/a     | The error message
field       | n/a     | The name of field that will be used to compare with current one. This option is required

### LessThan Validator

| Option name | Default | Description
| ------------|---------|------------
| message     | n/a     | The error message
| value       | n/a     | The number to make a comparison to. This option is required
| inclusive   | n/a     | Can be true or false
|             |         | If true, the input value must be less than the comparison one
|             |         | If false, the input value must be less than or equal to the comparison one

### Regexp Validator

Option name | Default | Description
------------|---------|------------
message     | n/a     | The error message
regexp      | n/a     | The Javascript regular expression. This option is required

### Remote Validator

| Option name | Default | Description
| ------------|---------|------------
| message     | n/a     | The error message
| url         | n/a     | The remote URL.
|             |         | The remote URL must response an encoded JSON of array containing the 'valid' key
|             |         | This option is required

### StringLength Validator

Option name | Default | Description
------------|---------|------------
message     | n/a     | The error message
min         | n/a     | The minimum length
max         | n/a     | The maximum length. One of 'min', 'max' options is required

## Build

BootstrapValidator uses [grunt](http://gruntjs.com) to simplify building process.

From the BootstrapValidator root directory, execute the following commands to install the dependent packages (the administrator permission might be required):

```bash
$ npm install grunt --save-dev
$ npm install grunt-contrib-concat --save-dev
$ npm install grunt-contrib-copy --save-dev
$ npm install grunt-contrib-cssmin --save-dev
$ npm install grunt-contrib-uglify --save-dev
$ npm install grunt-contrib-watch --save-dev
```

Then, uses grunt to build:

```bash
$ grunt
```

If you want grunt to generate scripts whenever the original scripts (located in ```src```) change, use the following command:

```bash
$ grunt watch
```

The generated scripts (including source and compressed versions) are placed inside the ```dist``` directory.

## Release History

Look at the [Change Log](CHANGELOG.md)

## Author

Nguyen Huu Phuoc ([Email](mailto: phuoc@huuphuoc.me) / [Twitter](http://twitter.com/nghuuphuoc) / [Github](http://github.com/nghuuphuoc))

Big thanks to the contributors:

* Vu Minh Khang ([Email](mailto: khangvm530@gmail.com) / [Github](https://github.com/khangvm53))

## License

Copyright (c) 2013 Nguyen Huu Phuoc

BootstrapValidator is licensed under the MIT license.