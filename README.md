# Save As You Type

This is a fork of Save As You Type which works with Cookies.

This jQuery plugin autosaves to the browser local storage (using jStorage) as you type, and autorecovers, form data. Auto saving will save as data is entered or changed.

You have the ability to disable autosaving and auto recovering, and instead use manual calls for each. You can also manually call an erase cookie feature, and manually call to see if a form actually has saved data.

Currently, the plugin works for the following form elements:

* Text boxes
* Text areas
* Select (Single AND multiple)
* Radio buttons
* Check boxes

Tested as working in:

* IE7
* IE8
* IE9
* Chrome
* Firefox
* Safari
* Opera

## Examples

Default's:

* autosave: true
* savenow: false
* days: 3
* erase: false
* recover: false
* autorecover: true
* checksaveexists: false - (Returns true or false)

```js
$(function()
{

	/**
	 * When building your forms, you MUST make sure your form has an ID, and that it's unique
	 * on the application.
	 *
	 * Ie, don't call all forms 'id="form"', even if they are on seperate pages.
	 */
	
	/*
	 * Attach to a form with default settings
	 */
	$('#form_id').sayt();
	
	
	/*
	 * Attach to a form with custom settings
	 *
	 * Autosave disabled (Must use manual save to save anything)
	 * Autorecover disabled (Must use a manual recover to recover anything)
	 * Days 7 (Keeps the data for 7 days)
	 */
	$('#form_id').sayt({'autosave': false, 'autorecover': false, 'days': 7});
	
	
	/*
	 * Check to see if a form has a save
	 */
	if($('#form_id').sayt({'checksaveexists': true}) == true)
	{
		console.log('Form has existing data.');
	}
	
	
	/*
	 * Perform a manual save
	 */
	$('#forms_save_button').click(function()
	{
		$('#form_id').sayt({'savenow': true});
		
		console.log('Form data has been saved.');
		return false;
	});
	
	
	/*
	 * Perform a manual recover
	 */
	$('#forms_recover_button').click(function()
	{
		$('#form_id').sayt({'recover': true});
		
		console.log('Form data has been recovered.');
		return false;
	});
	
	
	/*
	 * To erase form data
	 */
	$('#forms_delete_save_button').click(function()
	{
		$('#form_id').sayt({'erase': true});
		
		console.log('Form datac was deleted.');
		return false;
	});
	
});
```

## Dependencies

This plugin depends on the on jStorage: https://github.com/andris9/jStorage


## Author

[Ben Griffiths]
Adapted for jStorage by Lorenz Ulrich

## License

Copyright (c) 2012 Ben Griffiths, 2014 Lorenz Ulrich. Licensed under the MIT License. Redistributions of files must retain the above copyright notice.
