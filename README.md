# CI Markdown

CI Markdown is a modified rendition of Michel Fortin's [PHP Markdown][1]
and [PHP Markdown Extra][2] for [CodeIgniter][3].

## Install

### Requirements

- [PHP][4] version 8.1 or newer
- [CodeIgniter][3] version 4.5.x

### Download

Download and extract the [ZIP][5] release to your CodeIgniter
`app` directory.

**The extracted paths should resemble:**

- `app/Libraries/Markdown.php`
- `app/Config/Markdown.php`

## Usage

### Configuration

Custom [PHP Markdown settings](https://michelf.ca/projects/php-markdown/configuration/)
are defined in the [Config/Markdown.php](Config/Markdown.php) config file.

### Initializing the Markdown Class

Like most other classes in CodeIgniter, initialize it from your controller
using the `Factories::libraries();` method:

```php
Factories::libraries('Markdown');
```

To programmatically configure the Markdown instance, overriding any matched
settings defined in the [config file](Config/Markdown.php):

```php
$config = array(
    'tab_width' => 2,
    'no_markup' => true
    'empty_element_suffix' => '/>'
);

$markdown = Factories::libraries('Markdown', [], $config);
```

#### Markdown to HTML

- `$markdown->transform()`

Accepts a single `string` parameter of Markdown *text* and returns the
transformed HTML.

```php
$markdown = Factories::libraries('Markdown');

$markdownText = "# Heading "."\n"."## Sub-heading";
echo $markdown->transform($markdownText);
// <h1>Heading</h1>
// <h2>Sub-heading</h2>
```

#### Markdown file to HTML

- `$markdown->transform_file()`

Accepts a single `string` parameter for a Markdown *file path* and returns the
transformed HTML.

```php
$markdown = Factories::libraries('Markdown');

echo $markdown->transform_file('/path/to/markdown/file.md');
// <h1>Heading</h1>
// <h2>Sub-heading</h2>
```

### Syntax Guides and Markdown Converter

- [John Gruber's PHP Markdown Syntax Guide](https://daringfireball.net/projects/markdown/syntax)
- [John Gruber's PHP Markdown Converter](https://daringfireball.net/projects/markdown/dingus)
- [Michel Fortin's PHP Markdown Extra Syntax Guide](https://daringfireball.net/projects/markdown/syntax)

## Issues

For all issues including feature requests, please [open a new issue][6].

## Changes

See the [Changelog][7] page.

## Credits

- [John Gruber](http://daringfireball.net/)
- [Michel Fortin](https://michelf.ca/home/)

[1]: https://michelf.ca/projects/php-markdown/
[2]: https://michelf.ca/projects/php-markdown/extra/
[3]: https://www.codeigniter.com
[4]: https://php.net
[5]: https://github.com/jonlabelle/ci-markdown/archive/master.zip
[6]: https://github.com/jonlabelle/ci-markdown/issues/new
[7]: https://github.com/jonlabelle/ci-markdown/blob/master/CHANGELOG.md
