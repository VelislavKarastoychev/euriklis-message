# Euriklis - message package.

## About the package:

The ***@euriklis/message*** or ***euriklis-message*** package is a javascript tool that provide an utility library for colored console printing of messages with some additional properties like warning symbol, information symbol, check symbol or not check symbol. 

# Installation

To install the euriklis-message package just run in the terminal the following command.

`npm install @euriklis/message --save --save-exact`

This command will add the package to your node_modules folder.

# Usage:

To use the message library you have to get it from the package:

```js
const message = require ('@euriklis/message')
// print an information message:
new message().bold().italic().underline().set_color_yellow()
    .append('Euriklis information message:\n')
    .reset().set_color_green().append_check_mark()
    .set_color_cyan().append_white_space()
    .append('The message library of the euriklis package was successfully installed.')
    .reset().log()
// print an error message:
new message().bold().italic().underline().set_color_yellow()
    .blink().append('Euriklis error message:\n')
    .reset().set_color_red().append_warning_sign().set_color_yellow().append('The message library of the euriklis package prints error message for you.')
    .reset().log()
```

# Methods:

## message methods

All the methods of the message class returns message object but makes changes on the text parameter of the instance.
1. bold() - makes the text that will be printed in the terminal bold style.
2. italic() - makes the text that will be printed in the terminal with italic style.
3. underline() or underscore() ?!!? - this method makes the style of the text that will be printed on the terminal to be underlined.
4. blink() - the text that will be printed on the terminal will blink periodically.
5. setColor(color) - sets the color of the text that will be printed on the terminal. The possible values of the color are 'black', 'red', 'green', 'blue', 'grey', 'violet', 'cyan' and finally 'yellow'.
6. setBgColor(color) - sets the background color of the text message that will be printed on the terminal. The possible color values of the method are the same with the setColor() method. Note that for the methods setColor() and setBgColor() exists short specified methods like set_color_red() that sets the color of the text automatically to the cyan without inserting of some argument.
7. reset() - reset, restart the color/background color and style properties of the text to the default.
8. append(text_message) - appends a text to the current text property of the message instance.
9. append_check_mark() - appends check mark symbol to the text.
10. append_not_check_mark()
11. append_warning_sign() - appends a warning sign to the text.
12. append_white_space() - appends a white space to the text property.
13. log() - prints the message on the terminal. 
14. warn() - execute console.warn method to the text.
15. error() - execute console.error() method to the text property.
16. info() - execute console.info() method to the text property.


Note that the color, background color and style method are valid only in the node terminal environment.

# More useful examples:

Let say that we want to print a mathematical expression in formal logic. We can use the append_math_... and append_logic_... methods of the library.
```js
new message().bold().set_color_yellow().setBgColor('red')
    .append_logical_forAll_symbol().append(' a, b : ')
    .append('a ').append_logical_element_of_symbol()
    .append_white_space().append_math_natural_numbers_symbol()
    .append_white_space().append_logical_conjunction_symbol()
    .append_white_space().append('b')
    .append_white_space().append_logical_element_of_symbol()
    .append_white_space().append_math_natural_numbers_symbol()
    .append_white_space().append_logical_follows_symbol()
    .append_white_space().append_logical_exists_symbol()
    .append_white_space().append('c :')
    .append_white_space().append('c ')
    .append_logical_element_of_symbol()
    .append_white_space().append_math_natural_numbers_symbol()
    .append_white_space().append_logical_conjunction_symbol()
    .append(' c').append_white_space()
    .append_logical_identical().append_white_space()
    .append('a + b ').reset().log()
```
and we have to take the following result in the terminal:

<div style = "color:yellow"> 
∀ a, b : a ∈ ℕ ⋀ b ∈ ℕ ⇒ ∃ c : c ∈ ℕ ⋀ c ≡ a + b
</div>

# Bugs and tips

If you want to inform me for something useful for this project or for some possible mistake or error, you can send me an email to exel_mmm@abv.bg or to euriklis@hotmail.com

# License

This project has MIT license. Everyone that use it has to know that the author of the project is not responsible for any third party software or hardware harms that follows from the using of this library. The package is free to use supposing that the it will be not part of some commercial software or hardware product.
