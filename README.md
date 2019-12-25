# Trimmer

[![Travis CI Build Status](https://travis-ci.org/jonlabelle/Trimmer.svg?branch=master)](https://travis-ci.org/jonlabelle/Trimmer)
[![AppVeyor Build status](https://ci.appveyor.com/api/projects/status/fdcdvfsip9d9efg3?svg=true)](https://ci.appveyor.com/project/jonlabelle/trimmer)
[![SonarQube Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=org.jonlabelle-github%3ATrimmer%3Amaster&metric=alert_status)](https://sonarcloud.io/dashboard/index/org.jonlabelle-github:Trimmer:master)
[![Package Control Installs](https://img.shields.io/packagecontrol/dt/Trimmer.svg?label=installs)](https://packagecontrol.io/packages/Trimmer)
[![Latest Release](https://img.shields.io/github/tag/jonlabelle/Trimmer.svg?label=version)](https://github.com/jonlabelle/Trimmer/releases)

> [Trimmer](https://github.com/jonlabelle/Trimmer) is a [Sublime Text](http://www.sublimetext.com) plug-in for cleaning up whitespace.

## Features

- Trim whitespace at the end of each line.
- Trim whitespace at the start of each line.
- Trim whitespace at the start and end of each line.
- Trim whitespace from selection(s).
- Delete empty, whitespace only lines.
- Collapse multiple consecutive empty lines into one empty line.
- Collapse multiple consecutive spaces into one space.
- Trim empty, whitespace only lines at the beginning and end of file.
- Remove blank space characters.
- Normalize spaces (consecutive spaces reduced, empty lines removed and lines trimmed).
- Tokenize a string by collapsing consecutive spaces, and trimming leading and trailing spaces.
- Delete empty, whitespace only HTML and XML tags.
- Remove code comments and collapse lines.

## Additional Features

A **Replace Smart Characters** command that performs the following actions:

- **Smart single quotes:** `’` *to* `'`
- **Smart double quotes:** `“` *to* `"`
- **Prime:** `′` *to* `'`
- **Double Prime:** `″` *to* `"`
- **German quotes:** `„` *to* `"` and `‚` *to* `'`
- **Ellipsis:** `…` *to* `...`
- **Em dash:** `—` *to* `---`
- **En dash:** `–` *to* `--`
- **Bullet:** `•` *to* `*`
- **Middle dot:** `·` *to* `-`
- **Em space** *to* three spaces
- **En space** *to* two spaces
- **Non-breaking space** *to* one space
- **Thin space** *to* one space
- **Hair space** *to* one space
- **Left angle quote:** `«` *to* `<<`
- **Right angle quote:** `»` *to* `>>`
- **Copyright symbol:** `©` *to* `(C)`
- **Trademark symbol:** `™` *to* `(T)`
- **Registered trademark symbol:** `®` *to* `(R)`

![ScreenShot](https://raw.githubusercontent.com/jonlabelle/Trimmer/master/screenshots/command_palette.png)

Watch a [**Quick Demo**](https://raw.githubusercontent.com/jonlabelle/Trimmer/master/screenshots/demo.gif)


## Installation

### By Package Control

1. Download & Install **`Sublime Text 3`** (https://www.sublimetext.com/3)
1. Go to the menu **`Tools -> Install Package Control`**, then,
   wait few seconds until the installation finishes up
1. Now,
   Go to the menu **`Preferences -> Package Control`**
1. Type **`Add Channel`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
   input the following address and press <kbd>Enter</kbd>
   ```
   https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json
   ```
1. Go to the menu **`Tools -> Command Palette...
   (Ctrl+Shift+P)`**
1. Type **`Preferences:
   Package Control Settings – User`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
   find the following setting on your **`Package Control.sublime-settings`** file:
   ```js
       "channels":
       [
           "https://packagecontrol.io/channel_v3.json",
           "https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json",
       ],
   ```
1. And,
   change it to the following, i.e.,
   put the **`https://raw.githubusercontent...`** line as first:
   ```js
       "channels":
       [
           "https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json",
           "https://packagecontrol.io/channel_v3.json",
       ],
   ```
   * The **`https://raw.githubusercontent...`** line must to be added before the **`https://packagecontrol.io...`** one, otherwise,
     you will not install this forked version of the package,
     but the original available on the Package Control default channel **`https://packagecontrol.io...`**
1. Now,
   go to the menu **`Preferences -> Package Control`**
1. Type **`Install Package`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
search for **`Trimmer`** and press <kbd>Enter</kbd>

See also:

1. [ITE - Integrated Toolset Environment](https://github.com/evandrocoan/ITE)
1. [Package control docs](https://packagecontrol.io/docs/usage) for details.


## Usage

All commands are accessible from the **Command Palette** using prefix
***Trimmer***, and in the **Main Menu** under `Edit` -> `Line` -> *Trimmer* command.

- [Command Palette screenshot](https://raw.githubusercontent.com/jonlabelle/Trimmer/master/screenshots/command_palette.png)
- [Main Menu screenshot](https://raw.githubusercontent.com/jonlabelle/Trimmer/master/screenshots/main_menu.png)

### Key Bindings

The *default* key binding will trim trailing whitespace at the end of each of
line (entire file).

- **OS X**: `Ctrl + S`
- **Linux**: `Ctrl + Alt + S`
- **Windows**: `Ctrl + Alt + S`

### Trimmer Command API

|              Command               |                                              Description                                               |          Context          |
|------------------------------------|--------------------------------------------------------------------------------------------------------|---------------------------|
| `trimmer`                          | trim whitespace at the end of each line                                                                | entire file               |
| `trim_leading_whitespace`          | trim whitespace at the start of each line                                                              | selection, or entire file |
| `trim_leading_trailing_whitespace` | trim whitespace at the start and end of each line                                                      | selection, or entire file |
| `trim_selections`                  | trim whitespace from selection(s)                                                                      | selection                 |
| `delete_empty_lines`               | delete empty, whitespace only lines                                                                    | selection, or entire file |
| `collapse_lines`                   | collapse multiple consecutive empty lines into one empty line                                          | selection, or entire file |
| `collapse_spaces`                  | collapse multiple consecutive spaces into one space                                                    | selection, or entire file |
| `trim_edges`                       | trim empty, whitespace only lines at the beginning and end of the file                                 | entire file               |
| `remove_blank_spaces`              | remove all blank space characters (tab, cr, ff, vt, space)                                             | selection, or entire file |
| `normalize_spaces`                 | consecutive spaces reduced, empty lines removed and lines trimmed                                      | selection, or entire file |
| `replace_smart_characters`         | replace smart characters (smart quotes, em/en dash, ellipsis, nbsp)                                    | selection, or entire file |
| `tokenize_string`                  | convert a string to a token by collapsing consecutive spaces, and trimming leading and trailing spaces | selection, or entire file |
| `delete_empty_tags`                | delete empty, whitespace only html and xml tags                                                        | selection, or entire file |
| `remove_comments`                  | remove code comments and collapse lines                                                                | selection, or entire file |

## Author

[Jon LaBelle](https://jonlabelle.com)

## License

Trimmer is licensed under the [MIT license](http://opensource.org/licenses/MIT).
