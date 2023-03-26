Dataview
title: <%+ tp.file.title %>
date_created: <% tp.file.creation_date("YYYY-MM-DD") %>
date_modified: <%+ tp.file.last_modified_date("YYYY-MM-DD") %>
tags: <%+ tp.file.tags %>

Status: #incomplete #documentation #reference 
Tags: [[Obsidian]] 

Documentation: https://blacksmithgu.github.io/obsidian-dataview/

Dataview Query Language: https://blacksmithgu.github.io/obsidian-dataview/queries/structure/

## Dataview consists of two big building blocks: **Data Indexing** and **Data Querying**.

### Data Indexing

Dataview operates on metadata in your Markdown files. It cannot read everything in your vault, but only specific data. Some of your content, like tags and bullet points (including tasks), are [available automatically](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/#implicit-fields) in Dataview. You can add other data through **fields**, either on top of your file [per YAML Frontmatter](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/#frontmatter) or in the middle of your content with [Inline Fields](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/#inline-fields) via the `[key:: value]` syntax. Dataview _indexes_ these data to make it available for you to query.

### Data Querying

You can access **indexed data** with the help of **Queries**.

There are **three different ways** you can write a Query: With help of the [Dataview Query Language](https://blacksmithgu.github.io/obsidian-dataview/queries/dql-js-inline/#dataview-query-language-dql), as an [inline statement](https://blacksmithgu.github.io/obsidian-dataview/queries/dql-js-inline#inline-dql) or in the most flexible but most complex way: as a [Javascript Query](https://blacksmithgu.github.io/obsidian-dataview/queries/dql-js-inline#dataview-js).

The **Dataview Query Language** (**DQL**) gives you a broad and powerful toolbelt to query, display and operate on your data. An [**inline query**](https://blacksmithgu.github.io/obsidian-dataview/queries/dql-js-inline#inline-dql) gives you the possibility to display exactly one indexed value anywhere in your note. You can also do calculations this way. With **DQL** at your hands, you'll be probably fine without any Javascript throurough your data journey.

A DQL Query consists of several parts:

-   Exactly one [**Query Type**](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/) that determines what your Query Output looks like
-   None or one [**FROM statement**](https://blacksmithgu.github.io/obsidian-dataview/queries/data-commands#from) to pick a specific tag or folder (or another [source](https://blacksmithgu.github.io/obsidian-dataview/reference/sources/)) to look at
-   None to multiple [**other Data Commands**](https://blacksmithgu.github.io/obsidian-dataview/queries/data-commands/) that help you filter, group and sort your wanted output

## Adding Metadata to your Pages

### How do I add fields?

You can add fields to a **note** in three different ways. How a field look like depends on the way you add it.

On **tasks or list items**, you will have YAML Frontmatter information available, but won't be able to add them to a specific list item. If you want to add metadata to one list item or task only, use [Inline Fields](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/#inline-fields).

#### Frontmatter

Frontmatter is a common Markdown extension which allows for YAML metadata to be added to the top of a page. It is natively supported by Obsidian and explained in its [official documentation](https://help.obsidian.md/Advanced+topics/YAML+front+matter). All YAML Frontmatter fields will be automatically available as Dataview fields.

    `---     alias: "document"     last-reviewed: 2021-08-17     thoughts:       rating: 8       reviewable: false     ---`

With this your note has metadata fields named `alias`, `last-reviewed`, and `thoughts`. Each of these have different **data types**:

-   `alias` is a [text](https://blacksmithgu.github.io/obsidian-dataview/annotation/types-of-metadata/#text), because its wrapped in ""
-   `last-reviewed` is a [date](https://blacksmithgu.github.io/obsidian-dataview/annotation/types-of-metadata/#date), because it follows the ISO date format
-   `thoughts` is a [object](https://blacksmithgu.github.io/obsidian-dataview/annotation/types-of-metadata/#object) field, because it uses the YAML Frontmatter object syntax

You could i.e. query for this note with the following query, because `thoughts` is a object with the value `rating`:

` ```dataview LIST WHERE thoughts.rating = 8 ``` `

#### Inline Fields

For those wanting a more natural-looking annotation, Dataview supports "inline" fields via a `Key:: Value` syntax that you can use everywhere in your file. This allows you to write your queryable data right where you need it - for example in the middle of a sentence.

If your inline field has an own line, without any content beforehand, you can write it like this:

`# Markdown Page  Basic Field:: Some random Value **Bold Field**:: Nice!`

All content after the `::` is the value of the field until the next line break.

If you want to embed metadata inside sentences, or multiple fields on the same line, you can use the bracket syntax and wrap your field in square brackets:

`I would rate this a [rating:: 9]! It was [mood:: acceptable].`

There is also the alternative parenthesis syntax, which hides the key when rendered in Reader mode:

`This will not show the (longKeyIDontNeedWhenReading:: key).`

will render to:

`This will not show the key.`

You can use YAML Frontmatter and Inline fields with all syntax variants together in one file. You do not need to decide for one and can mix them to fit your workflow.

## Implicit fields

Even if you do not add any metadata explicitly to your note, dataview provides you with a big amount of indexed data out of the box. Some examples for implicit fields are:

-   day the file was created (`file.cday`)
-   links in the file (`file.outlinks`)
-   tags in the file (`file.etags`)
-   all list items in the file (`file.lists` and `file.tasks`)

and many more. Available implicit fields differ depending if you look at a page or a list item. Find the full list of available implicit fields on [Metadata on pages](https://blacksmithgu.github.io/obsidian-dataview/annotation/metadata-pages/) and [Metadata on Tasks and Lists](https://blacksmithgu.github.io/obsidian-dataview/annotation/metadata-tasks/).

## Available Field Types

Dataview knows several field types to cover common use cases.

### Text

The default catch-all. If a field doesn't match a more specific type, it is plain text.

`Example:: This is some normal text.`

### Number

Numbers like '6' and '3.6'.
```
Example:: 6 
Example:: 2.4 
Example:: -80
```

In YAML Frontmatter, you write a number without surrounding quotes:
```
--- 
rating: 8 
description: "A nice little horror movie" 
---
```


### Boolean

Boolean only knows two values: true or false, as the programming concept.

```
Example:: true 
Example:: false
```
### Date

Text that matches the ISO8601 notation will be automatically transformed into a date object. [ISO8601](https://en.wikipedia.org/wiki/ISO_8601) follows the format `YYYY-MM[-DDTHH:mm:ss.nnn+ZZ]`. Everything after the month is optional.

```
Example:: 2021-04  
Example:: 2021-04-18 
Example:: 2021-04-18T04:19:35.000 
Example:: 2021-04-18T04:19:35.000+06:30
```

When querying for these dates, you can access properties that give you a certain portion of your date back:

-   field.year
-   field.month
-   field.weekyear
-   field.week
-   field.weekday
-   field.day
-   field.hour
-   field.minute
-   field.second
-   field.millisecond

For example, if you're interested in which month your date lies, you can access it via `datefield.month`:

``` 
birthday:: 2001-06-11  
```dataview 
LIST birthday 
WHERE birthday.month = date(now).month 
# ``` (Without the # sign)
```


gives you back all birthdays happening this month. Curious about `date(now)`? Read more about it under [literals](https://blacksmithgu.github.io/obsidian-dataview/reference/literals/#dates).

### Duration

Durations are text of the form `<time> <unit>`, like `6 hours` or `4 minutes`. Common English abbreviations like `6hrs` or `2m` are accepted. You can specify multiple units in one field, i.e. `6hr 4min`, optionally with comma separator: `6 hours, 4 minutes`

```
Example:: 7 hours 
Example:: 16days 
Example:: 4min 
Example:: 6hr7min 
Example:: 9 years, 8 months, 4 days, 16 hours, 2 minutes 
Example:: 9 yrs 8 min
```

Find the complete list of values that are recognized as a duration on [literals](https://blacksmithgu.github.io/obsidian-dataview/reference/literals/#durations).

>Calculations with dates and durations
>
Date and Duration types are compatible with each other. This means you can, for example, add durations to a date to produce a new date:
>
`` departure:: 2022-10-07T15:15 length of travel:: 1 day, 3 hours  **Arrival**: `= this.departure + this.length-of-travel` ``
>
and you get back a duration when calculating with dates:
>
``release-date:: 2023-02-14T12:00  `= this.release-date - date(now)` until release!!`````


Curious about `date(now)`? Read more about it under [literals](https://blacksmithgu.github.io/obsidian-dataview/reference/literals/#dates).

### Link

Obsidian links like `[[Page]]` or `[[Page|Page Display]]`.

```
Example:: [[A Page]] 
Example:: [[Some Other Page|Render Text]]
```

#### Links in YAML Frontmatter

If you reference a link in frontmatter, you need to quote it, as so: `key: "[[Link]]"`. This is default Obsidian-sup CTported behavior. Unquoted links lead to a invalid YAML frontmatter that cannot be parsed anymore.


```
---
parent: "[[parentPage]]" 
---
```

Please be aware that this is only a link for dataview, but not for Obsidian anymore - that means it won't show up in the outgoing links, won't be displayed on graph view and won't be updated on i.e. a rename.

### List

Lists are multi-value fields. In YAML, these are defined as normal YAML lists:

```
--- 
key3: [one, two, three] 
key4:  
  - four  
  - five  
  - six 
---
```
In inline fields, they are comma-separated lists values:

```
Example1:: 1, 2, 3 
Example2:: "yes", "or", "no"`
```

Please be aware that in Inline fields, you need to wrap **text values into quotes**

### Object

Objects are a map of multiple fields under one parent field. These can only be defined in YAML frontmatter, using the YAML object syntax:

```
---
obj: 
  key1: "Val" 
  key2: 3 
  key3: 
    - "List1" 
    - "List2" 
    - "List3"
---
```

In queries, you can then access these child values via `obj.key1` etc:

` ```dataview TABLE obj.key1, obj.key2, obj.key3 WHERE file = this.file ``` `


---
## References

2023-03-2608:16
Status: #idea
Tags:


---
## References

https://youtu.be/buOxN65U0qE