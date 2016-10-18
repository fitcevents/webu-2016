**Creating beautiful, accessible and user friendly forms**
----------------------------------------------------------
*With Clarissa Peterson*

Forms are one of the key ways users interact with websites. Making sure your forms work well will have a big impact on your UX. Simplest forms are the best not just because they’re easier to make, but because they are easier for your users to complete. You want to make completing the form as easy as possible, and the outcome of sending the form as clear as possible. (For a good example, see Freshbooks forms.) Extra questions on a form mean more data you need to clean up and deal with. If you ask extra questions (that you don’t necessarily need to complete the task, e.g. gender) you need to first build trust with your users so that they feel comfortable providing that information. For example, Facebook tells you why they’re asking for your birthday on their sign-up form (even though it’s a lie, it’s just for marketing). You want to build up your forms slowly, e.g. Twitter asks you for your name and email first, and only in the next step once you’re already somewhat invested asks you to pick a username, which is a more difficult decision.

Before HTML5 there was only the text input type but now we have many more:

* **date:** Some desktop browsers will provide a calendar by default and you can supply a min and max possible date.

* **time:** Similarly to date, you can set a min and max possible time

* **email:** On mobile you’ll get a different keyboard with an ‘@' sign and a ‘.’ to make it easier for data entry on mobile. There is also some built in validation and you can specify a max length.

* **url:** This also gives you a different keyboard on mobile.

* **tel**: Tel brings up a number pad on mobile.

* **number:** This gives you a custom keyboard on mobile as well. The thing to remember about numbers is that not everything that looks like a number is a number, e.g. you should use a text field for credit card numbers.

**Dropdown and radio buttons**

You’ll want to avoid drop downs in general, but especially when there are only two options. For two options use radio buttons, note that you’ll want to style radio buttons in order to give users a larger area to click. You can do this by setting the radio button opacity to 0, styling the labels, and leveraging the :checked pseudo selector to style the label that has been checked. Sometimes you’ll need a dropdown, e.g. a country selector. In these cases you'll want to place the most likely options at them top, not strictly in alphabetical order. You’ll also want to use loose partial matching to guess at the best possible option depending on what the user’s typed in. You can also section a long list into categories with an <optgroup>.

**Labels and placeholder text**

Label elements are very important for screen readers since screen readers cannot read placeholder text, so make sure you match up your labels to input fields. Placeholders are meant only to give an additional hint as to what to write in the field. Once you begin filling out the form you can no longer see the placeholder to know if you filled in the appropriate information. In the cases where you need to hide the label, use the aria-label attribute on the input element and placeholders, keeping in mind the previous caveat. Also note that placeholder text is not dark enough to meet minimum contrast requirements by default, but on the other hand you don’t want to make it darker as it would suggest that the form is already complete. You can style the placeholder text, but beware of vendor prefixes. Only use placeholder text instead of labels only if it’s more important for your site to look pretty than be usable.

**Required fields**

Use the required and aria-required attributes to signal to the user that the input field must be filled out. For forms where most, but not all fields are required it’s easier to indicate which are *not* the required fields with an asterix (the convention) than indicating all the field that are required. Keep in mind that not everyone knows what an asterix means, so provide a key at the *top* of the page with the meaning. Also, you don’t want to just use colour to indicate field requiredness as colour-blind people may not see them.

**Passwords**

Creating passwords is a commonly problematic part of the website, since requirements for passwords can vary and need to be communicated ahead of time, not just when submitting the form. What you can do is hide the instructions until the user is focussed on the field. It’s better to explicit about requirements than just saying, "you’re password is weak" which can lead to frustration. Tell your users the rules. Provide the user the ability to toggle to see their password so they can see where they made a mistake, but show the password as only asterixes by default or users think your site is not secure.

**Validation**

The only time instant validation is useful is when entering a user name. In other cases is just frustrating, e.g. entering an email address. Give then a chance to fill in the full email address before yelling at them that it’s invalid because it doesn’t include and @ sign. Validate emails only after moving off the field than on each keystroke. You can use aria polite for screen reads to wait, and aria assertive to tell users of errors immediately. Fields can be styled by whether they contain valid or invalid information, but try not to use color only to distinguish them.

**Misc.**

Do not use autocorrect on username fields, but do apply autocapitalization. When asking gender, first make sure you really need that information. Facebook lets you choose Male, Female or custom which gives you chance to specify which pronoun the user would prefer. On most sites you can simply avoid using the pronoun, but on medical sites it is actually an important thing to know.

**Design**

Do small screen first then expand to full size. Sometimes the small size form works so well that you'll also want to use it for the desktop and just give it more background.

