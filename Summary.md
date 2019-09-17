# Summary
1. What is the knowledge point of the test? Where is the official document to the knowledge point?
	* To learn that String are immutable
	* How equality is measured among Strings
	* Common String functions
	* Official documents
		* [Object#equals](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#equals(java.lang.Object))
		* [String immutability and String functions](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)
		* [StringBuilder](https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuilder.html#append-java.lang.CharSequence-)
		* [Unicode](https://docs.oracle.com/javase/tutorial/i18n/text/unicode.html)

2. Why the test failed at first?
	* The correct value wasn't there
3. Why you corrected the test that way?
	* Those involving ```Optional.empty()```
		* Changed it to ```Optional.of(true|false)```
		* To maintain a similar structure to ```Optional.empty()```
	* should_taken_string_apart and should_taken_string_apart_continued
		* I created a variable to take note of the index instead of hardcoding the value to make the intent clearer. Creating an index variable also avoids the usage of magic numbers.
	* should_create_ascii_art
		* Since there are variables for ```width``` and ```height```, I used those to create the ascii art instead of simply hardcoding the result.
	* should_convert_unicode_escape
		* I answered by using ```\u``` followed by the unicode character of the Japanese character in the String. But it seems that the answer is wrong since Java can't correctly parse ```final String expected = "なにこれ";```
	* should_reverse_a_string
		* I used a StringBuilder and looped ```original``` in reverse and added each character to the StringBuilder.
	* should_format_string
		* I replaced the string format characters with the values for ```name``` and ```age```.
4. Do you have further questions on this knowledge point?
	* How do you answer should_convert_unicode_escape?
		* Evaluating ```expected``` shows: ã�ªã�«ã�“ã‚Œ instead of なにこれ
