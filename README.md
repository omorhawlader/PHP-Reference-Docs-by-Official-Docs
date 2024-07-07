# PHP Reference Documentation

Welcome to the PHP Reference Documentation project! This repository contains a collection of references and documentation derived from the official PHP docs. The goal is to provide a structured and easy-to-navigate resource for PHP developers.

## Table of Contents

1. [Introduction](./PHP_Introduction.md)

2. [Basic Syntax](./basic_syntax.md)

3. [Escaping From Html](./escaping_from_html.md)


## Introduction

## what is php?

> PHP (recursive acronym for PHP: Hypertext Preprocessor) is a widely-used open source general-purpose scripting language that is especially suited for web development and can be embedded into HTML. `Although PHP's development is focused on server-side scripting,but you can do much more with it`

Nice, but what does that mean by it can be embedded into HTML? An example:

```php
    <!DOCTYPE html>
<html>
    <head>
        <title>Example</title>
    </head>
    <body>

        <?php
            echo "Hi, I'm a PHP script!";
        ?>

    </body>
</html>

```

# PHP Creator.

> It was originally created by Danish-Canadian programmer `Rasmus Lerdorf` in 1993 and released in 1995


# What is the full form of PHP?

>The full form of PHP is `Hypertext Preprocessor`. It was abbreviated previously as `Personal Home Page`.

# What can PHP do?

### Anything. PHP is mainly focused on server-side scripting, so you can do anything any other CGI program can do, such as collect form data, generate dynamic page content, or send and receive cookies. But PHP can do much more.

## There are three main areas where PHP scripts are used.

- Server-side scripting.
- Command line scripting.
- Writing desktop applications.
- [`checkout for more details.`](https://www.php.net/manual/en/intro-whatcando.php)

[Installing & Environment Setup](./installing&environment.md)

## Bsic Syntax

# php Basic syntax

## PHP tags

> When PHP parses a file, it looks for opening and closing tags, which are <?php and ?> which tell PHP to start and stop interpreting the code between them. Parsing in this manner allows PHP to be embedded in all sorts of different documents, as everything outside of a pair of opening and closing tags is ignored by the PHP parser.

PHP includes a short echo tag <?= which is a short-hand to the more verbose <?php echo.

# Example #1 PHP Opening and Closing Tags

```php

1.  <?php echo 'if you want to serve PHP code in XHTML or XML documents,
                use these tags'; ?>

2.  You can use the short echo tag to <?= 'print this string' ?>.
    It's equivalent to <?php echo 'print this string' ?>.

3.  <? echo 'this code is within short tags, but will only work '.
            'if short_open_tag is enabled'; ?>
            
```

> Short tags (example three) are available by default but can be disabled either via the short_open_tag php.ini configuration file directive, or are disabled by default if PHP is built with the --disable-short-tags configuration

# Note:

`As short tags can be disabled it is recommended to only use the normal tags (<?php ?> and <?= ?>) to maximise compatibility.`

> If a file contains only PHP code, it is preferable to omit the PHP closing tag at the end of the file. This prevents accidental whitespace or new lines being added after the PHP closing tag, which may cause unwanted effects because PHP will start output buffering when there is no intention from the programmer to send any output at that point in the script.

```php

<?php
echo "Hello world";

// ... more code

echo "Last statement";

// the script ends here with no PHP closing tag

```

## Escaping From Html

# Escaping from HTML

> Everything outside of a pair of opening and closing tags is ignored by the PHP parser which allows PHP files to have mixed content. This allows PHP to be embedded in HTML documents, for example to create templates.

```php 
<p>This is going to be ignored by PHP and displayed by the browser.</p>
<?php echo 'While this is going to be parsed.'; ?>
<p>This will also be ignored by PHP and displayed by the browser.</p> 

```
> This works as expected, because when the PHP interpreter hits the ?> closing tags, it simply starts outputting whatever it finds (except for the immediately following newline - see instruction separation) until it hits another opening tag unless in the middle of a conditional statement in which case the interpreter will determine the outcome of the conditional before making a decision of what to skip over. See the next example.
Using structures with conditions

# Example #1 Advanced escaping using conditions

```php

<?php if ($expression == true): ?>
  This will show if the expression is true.
<?php else: ?>
  Otherwise this will show.
<?php endif; ?>

```

> In this example PHP will skip the blocks where the condition is not met, even though they are outside of the PHP open/close tags; PHP skips them according to the condition since the PHP interpreter will jump over blocks contained within a condition that is not met.
For outputting large blocks of text, dropping out of PHP parsing mode is generally more efficient than sending all of the text through echo or print.

# Note:

> If PHP is embeded within XML or XHTML the normal PHP <?php ?> must be used to remain compliant with the standards. [org-doc](https://www.php.net/manual/en/language.basic-syntax.phpmode.php)



## License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for more details.

---

Created by [Omor Hawlader (Omar)](https://github.com/omorhawlader).