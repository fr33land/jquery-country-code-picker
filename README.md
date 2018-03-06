# JQuery country dial code picker plugin
jQuery country dial code picker plugin (jQuery +1.7)

Plugin adds dropdown list of countries with dial codes to the choosen html input text element. It is possible to use plain json text file or remote json datasource as countries codes list. The example of JSON data structure is in data.json file. It is possible to initialize several ccPicker instances in same page on different HTML input elements. You can find demo in index.html file. Plugin is very lightweight. It comes without validation and doesn't use any UI library (jQuery UI, bootsrap) so you are free to use any external UI and validation libraries. This approach doesn't tie user to specific frameworks.

## Features
* Local or remote JSON datasource option
* Country name filter (case insensitive)
* Public methods for changing country by iso and phone code
* Registered country select event
* Flag icons

## Usage
Start using plugin in your page by adding js and css files. Also don't forgrt to add jQuery library.

```html
<script src="https://code.jquery.com/jquery-x.x.x.min.js" type="text/javascript"></script>
<script src="js/jquery.ccpicker.js" type="text/javascript"></script>
<link rel="stylesheet" type="text/css" href="css/jquery.ccpicker.css">
```

Add html input to your page and initialise plugin (with or without options).

```html
<script>
   $( document ).ready(function() {
      $("#phoneField").CcPicker();
   });
</script>

<input type="text" id="phoneField" name="phoneField" class="phone-field"/>
```

### Options

**countryCode** - 
Sets default plugin's country code.
* Type: **String**
* Default: **LT**

**dialCodeFieldName** - 
HTML input field name for using in jQuery selector.
* Type: **String**
* Default: **phoneCode**

**dataUrl** - 
JSON datasource url
* Type: **String**
* Default: **data.json**

**countryFilter** - 
Enable or disable country filter. 
* Type: **Boolean**
* Default: **true**

**searchPlaceHolder** - 
Change filter search field placeholder caption. 
* Type: **String**
* Default: **Search**

***Usage example***

```js
$("#phoneField").CcPicker({ countryCode: "fr", dataUrl: "http://server/countries.json", searchPlaceHolder: "Find..." });
```

### Public functions

**setCountryByPhoneCode** - 
Set country based on phone code.
* Param: **String**

***Usage example***

```js
$("#phoneField").CcPicker("setCountryByPhoneCode","370");
```

**setCountryByCode** - 
Set country based on country code.
* Param: **String**

***Usage example***

```js
$("#phoneField").CcPicker("countryCode","es");
```

**disable** - 
Disable ccPicker component

***Usage example***

```js
$("#phoneField").CcPicker("disable");
```

**enable** - 
Enable ccPicker component

***Usage example***

```js
$("#phoneField").CcPicker("enable");
```

### Plugin events

**countrySelect** - 
Event is triggered after dropdown country is selected

***Usage example***

```js
$("#phoneField").on("countrySelect", function(e, i){});
```

## Browser support

| Chrome |  FF  | Safari |  IE  | Edge | Opera |
| :----: | :--: | :----: | :--: | :--: | :---: |
|    X   |   ✓  |    ✓   |  8+  |   ✓ |   X   |
