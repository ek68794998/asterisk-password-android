# Android: Asterisk Password Field

:warning: **This project was build for very outdated versions of Android and is no longer updated.**

Based on [a question I answered on StackOverflow](http://stackoverflow.com/questions/11597648/in-android-how-to-show-asterisk-in-place-of-dots-in-edittext-having-inputtyp), I thought it would be a good idea to put this out in public for everyone to see.

This is an example of `PasswordTransformationMethod` that, in a password field, would display a paradigmic asterisk *, instead of the generic dot •.

# Usage

If `text` were a `TextView` variable, preferably an `EditText`, you would call the method using this:

	text.setTransformationMethod(new AsteriskPasswordTransformationMethod());
