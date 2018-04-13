# Memsource Polyglot Demo

## About the multiple-languages plugin

Unfortunately, this plugin does not fit the requirements:

- First and foremost, due to the way it requires the files to be organized, the content cannot be edited through forestry. The translatable content must reside inside a folder called `_i18n` in the root folder. This folder however, is not visible from the forestry gui.
- Front matter fields cannot be translated from the gui. They should be edited through `yaml` files which, again, cannot be edited through forestry.

## Polyglot

So the next best choice, was the [Polyglot plugin](https://github.com/untra/polyglot).

This plugin requires the pages to have a `lang` field and a `permalink` field. The variant of the same page must have **the same value for their permalink fields**.

The markdown files can reside in folders, like `/en` or `/jp`.

## Data files

Data files can reside in their language folders as well. For instance, we have the `_data/en/speakers.yml` and the corresponding `_data/ja/speakers.yml` files. Polyglot is able to identify the current language and use the correct data file. **Forestry however, does not show the folders in the Data Files sections and just shows a flat list of the data files.**

## Page Titles

I have noticed that if a page title is consisted of Japanese characters only, Forestry creates a file without a name, therefore this page cannot be rendered.

So it is recommended, on page creation, to fill the title field with Latin characters as well. This title is set to not be shown in the pages. 

Instead, there is a separate Page Title field, which is actually used  through the page rendering. This field can also consist of just non-latin characters.

## Adding pages

In order to create a page with language variations, add pages to the language folders.

Upon creation, the title must not contain non-latin characters only.

Also, a Front Matter Template must be chosen. There is a generic one, called `Page`. The meetup page, which uses a unique layout, uses the `Meetup` template.

On the page editing gui, the front matter fields can be filled, along with the page's body in Markdown. The meetup page has its own unique fields.

Remember that the `permalink` field must have **the same value** in all the variants of the page!

## jp and ja

Since the segment `ja` must be present in the URLs, Polyglot must use the `ja` identifier. However, wherever possible, the `jp` identifier is used as well, without disrupting the desired functionality.