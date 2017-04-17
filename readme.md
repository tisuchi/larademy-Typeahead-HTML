# How to Use Typeahead (Auto-Complete) with HTML

If you are planning to use Auto-Complete field in your html, I believe, **[Typeahead](https://twitter.github.io/typeahead.js/)** is your first choose. Its very very flexible, where you can just use Typeahead.js library to use that. 

Imagine that, you have a country list that you want to display in text field in html with auto-complete way. Let's do this. 

## What we need 
To complete this task, we need jQuery and Typeahead library. I am grabbing cdn for these. 

```
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
<script src="https://twitter.github.io/typeahead.js/releases/latest/typeahead.bundle.js"></script>
```
Just add this library cdn in header. 


Now call the Typeahead instance (I prefer to put inside <head> tag)

```
<script>
$(document).ready(function(){

	//list of the countries
	var countries = ["Afghanistan", "Albania", "Bahamas", "Bahrain", "Cambodia", "Cameroon", "Denmark", "Djibouti", "East Timor", "Ecuador", "Falkland Islands (Malvinas)", "Faroe Islands", "Gabon", "Gambia", "Haiti", "Heard and Mc Donald Islands", "Iceland", "India", "Jamaica", "Japan", "Kenya", "Kiribati", "Lao People's Democratic Republic", "Latvia", "Macau", "Macedonia", "Namibia", "Nauru", "Oman", "Pakistan", "Palau", "Qatar", "Reunion", "Romania", "Saint Kitts and Nevis", "Saint Lucia", "Taiwan", "Tajikistan", "Uganda", "Ukraine", "Vanuatu", "Vatican City State", "Wallis and Futuna Islands", "Western Sahara", "Yemen", "Yugoslavia", "Zaire", "Zambia"];
	

	//instance of Typeahead
	var countries_list = new Bloodhound({
		datumTokenizer: Bloodhound.tokenizers.whitespace,
		queryTokenizer: Bloodhound.tokenizers.whitespace,
		local: countries
	});
	
	$('.searchfield').typeahead(
		{ minLength: 1 },
		{ source: countries_list }
	);

});  
</script>
```

Now in your body, you can add search textfield. 

```
Search:</label> <input type="text" name="country" class="searchfield" />
```

Now, run your file and it should work. 



Read the Original Tutorial [Typeahead](https://twitter.github.io/typeahead.js/)







