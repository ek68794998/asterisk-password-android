# Android: Asterisk Password Field
Based on [a question I answered on StackOverflow](http://stackoverflow.com/questions/11597648/in-android-how-to-show-asterisk-in-place-of-dots-in-edittext-having-inputtyp), I thought it would be a good idea to put this out in public for everyone to see.

This is an example of `PasswordTransformationMethod` that, in a password field, would display a paradigmic asterisk *, instead of the generic dot •.

# Usage

If `text` were a `TextView` variable, preferably an `EditText`, you would call the method using this:

	text.setTransformationMethod(new AsteriskPasswordTransformationMethod());

# Code

	public class AsteriskPasswordTransformationMethod extends PasswordTransformationMethod {
		@Override
		public CharSequence getTransformation(CharSequence source, View view) {
			return new PasswordCharSequence(source);
		}

		private class PasswordCharSequence implements CharSequence {
			private CharSequence mSource;
			public PasswordCharSequence(CharSequence source) {
				mSource = source; // Store char sequence
			}
			public char charAt(int index) {
				return '*'; // This is the important part
			}
			public int length() {
				return mSource.length(); // Return default
			}
			public CharSequence subSequence(int start, int end) {
				return mSource.subSequence(start, end); // Return default
			}
		}
	};
