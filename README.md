# Numbered Vanila v1.0.0

Plugin for create an input mask of numbers

```javascript
new Numbered(el, options);
```
## Default options
```javascript
{
    mask: '+7 (###) ### - ## - ##', // Mask for input value
    numbered: '#',                  // Masking definition
    empty: '_',                     // Empty masking definition char (or space)
    placeholder: false              // Enable  placeholder to mask
}
```

## Initialize
```javascript
var numberedFromId = new Numbered('#numbered');
```
or
```javascript
var numberedFromClass = new Numbered('.numbered', {
    mask: '#### - #### - #### - ####',
	empty: 'X',
	placeholder: true
});
```
or
```javascript
var numberedFromTag = new Numbered('input');
```
or
```javascript
var numberedFromSelector = new Numbered('form input.numbered');
```
or if jQuery included
```javascript
var $numbered = $('#numbered');
var numberedFromJQuery = new Numbered($numbered);
```

## Validate
Validate method retuns `1` - is valid, `0` - is empty, `-1`, is invalid. The result can be `Integer` or `Array` depending on the number of elements. You can listen to your desired events and to validate out at any time.
```
var $numbered = $('#numbered');
var numbered = new Numbered($numbered);
$numbered.on('change blur input focusin', function () {
    console.log(numbered.validate());
});
```

## Destroy

```javascript
var numbered = new Numbered('#numbered');
numbered.destroy();
```