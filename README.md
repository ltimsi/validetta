# hsnValidate

hsnValidate is a tiny jQuery plugin which you can do client-side validation of your forms. It aims to decrease your burden with easy usage and flexible structure.

[View Demos](http://lab.hasanaydogdu.com/hsnValidate/#examples)

## What can be done?

* You can check fields whether it is empty or not or it is chosen or not.
* You can do e-mail check.
* You can do number check.
* You can check if the two fields are equal to each other.
* You can check credit card number validation.
* You can limit number of characters written to fields.
* You can limit number of choice of multiple select box or check box.
* By creating your own regular expression, you can check fields according to this regular expression.

##Browser support

The project is tested in Chrome and Firefox. It should work in the current stable releases of Chrome, Firefox, Safari as well as IE8 and up.

## How does it work?

It is sufficient to copy downloaded hsnValidate folder to root folder and attach essential folders to your web page. You don’t need to copy hsnValidate folder to root folder but those are applied in the following expression as if hsnValidate is copied to root folder.

include the dependent libraries and css files

```html
<link href="hsnValidate/hsnValidate.css" rel="stylesheet" type="text/css" media="screen" >

<script type="text/javascript" src="http://code.jquery.com/jquery-latest.min.js"></script>
<script type="text/javascript" src="hsnValidate/hsnValidate.js"></script>   
```

You can include language file if you want.

```html
<script type="text/javascript" src="hsnValidate/languages/hsnValidateLang-tr.js"></script>
```

Then, you will only need to call the plugin inside `$(document).ready function`:

```javascript
$(document).ready(function() {
    $("#form").hsnValidate();
});
```

and add `data-hsnvalidate` attribute to element which you want to validate.

```html
<input type="text" name="example" data-hsnvalidate="required,minLength[2],maxLength[3]" />
```

## Checking methods [ ]
- `required` : It checks fields if it is empty or not.
- `number` : It checks fields if it is consist of number or not.
- `email` : It checks E-mail if it is valid or not.
- `creditCard` : It checks credit card number written to fields if it is valid or not.
- `equal[input_name]` : It checks if the two fields are equal to each other according to input name.
- `minLength[x]` : It checks fields if it is consist of minimal X character.
- `maxLength[x]` : It checks maximal X character entry to the area.
- `minChecked[x]` : It checks minimal X option if it is marked or not.
- `maxChecked[x]` : It checks maximal X option if it is marked or not.
- `minSelected[x]` : It checks minimal X option if it is chosen or not.
- `maxSelected[x]` : It checks maximal X option if it is chosen or not.
- `customReg[regexp_name]` : It checks if field is suits to identified ordered expression or not.

## Options { }

### errorClass 

If you want special style, you can add a class to error message with this option.

```javascript
{
    errorClass      : 'formHata'
}
```

### errorCloseClass 

You can add a class to error message closure button.

```javascript
{
    errorCloseClass : 'formHataKapa'
}
```

### ajax

It provides ajax request after validate process is completed. 

```javascript
{
    ajax : {
        call        : true,         /* If you want make an ajax request set it true */
        type        : 'GET',        /* Ajax type. Default value is "GET" */
        url         : null,         /* Ajax url. You don’t need to write again here, if you wrote address which your form will be posted.  Plugin gets url information from action attribute. */
        dataType    : 'html',       /* Ajax dataType. Default value is "html" */
        beforeSend  : function(){}, /* Ajax beforeSend function */
        success     : function(){}, /* Ajax success function */
        fail        : function(){}, /* Ajax error function */
        complete    : function(){}  /* Ajax complete function */
    }
}
```

### realTime

To enable real-time form control, set this option true. Default value is "false"

```javascript
{
    realTime     : true
}
```

### onCompleteFunc

This is the function to be run after the completion of form control.

```javascript
{
    onCompleteFunc  : function(){}
}
```

## License
All code is open source and dual licensed under [GPL](http://www.gnu.org/licenses/gpl.txt) and [MIT](http://www.opensource.org/licenses/mit-license.php). Check the individual licenses for more information.