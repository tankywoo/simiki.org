---
title: "Collection/Tag"
date: 2016-04-27 00:00
---

## Three-Tier Structure ##

*(new in version 1.6.0)*

Simiki manage personal documents(`content` directory) by three-tier structure:

1. category: The first level, stored by directory, be used to simply classficition.
2. collection: The second level, defined in the `meta` filed of page (keyword: `collection`). A page can only belonged to one collection
3. tag: The third level, defined in the `meta` of page (keyword: `tag`). A page can have multiple tags.

This way can satisfy the needs of most personal wiki users, and is easy to manage.

> new theme `simple2` will not support multiple level structure of content directory:

> * Personal wiki rarely need multiple level structure to store documents
> * Reduce complexity of generator.
> * Reduce complexity of theme development.
>
> Maybe we would support multiple level structure of content directory in the future, but for the moment it's not. If you want the theme to support multiple level structure, you can refer the old default theme [simple](https://github.com/tankywoo/simiki/tree/master/simiki/themes/simple).

---

Details about collection and tag:

### collection ###

For example, the content directory:

```text
tree content
content
├── linux
│   └── other2.md
└── tool
    ├── git.md
    ├── other1.md
    └── svn.md
```

If **without** collection, the `pages` variable looks like (Irrelevant fields has been removed):

```text
[
  {
    "name": "linux",        # Category Nmae
    "pages": [
      ...
    ]
  },
  {
    "name": "tool",        # Category Name
    "pages": [             # The whole pages and collections under category
      {
        "date": "2016-01-01 00:00",
        "fname": "git.md",        # Page without collection
        ...
      },
      {
        "date": "2016-01-03 00:00",
        "fname": "other1.md",
        ...
      },
      {
        "date": "2016-01-02 00:00",
        "fname": "svn.md",
        ...
      }
    ]
  }
]
```

Now we define the same collection for git.md and svn.md:

```text hl_lines="5 11"
$ cat content/tool/{git,svn}.md
---
title: "Git"
date: 2016-01-01 00:00
collection: Version Control
---

---
title: "SVN"
date: 2016-01-02 00:00
collection: Version Control
---
```

**With** collection, the `pages` variable looks like (Irrelevant fields has been removed):

```text hl_lines="17 18"
[
  {
    "name": "linux",        # Category Name
    "pages": [
      ...
    ]
  },
  {
    "name": "tool",        # Category Name
    "pages": [             # The whole pages and collections under category
      {
        "date": "2016-01-03 00:00",
        "fname": "other1.md",        # Page without collection
        ...
      },
      {
        "name": "Version Control",        # Collection Name
        "pages": [                        # The while pages under collection
          {
            "collection": "Version Control",
            "fname": "git.md",
            "date": "2016-01-01 00:00"
            ...
          },
          {
            "collection": "Version Control",
            "fname": "svn.md",
            "date": "2016-01-02 00:00"
            ...
          }
        ]
      }
    ]
  }
]
```

Under the same category, if we defined the same collection:

* Within the same category, collection-undefined pages are the same level with collection.
* Within the same category, collection-defined pages are under collection, in the sub-level.

### Tag ###

Tag make the wikis with relationship.

For example, two wikis relate to Vim:

```text hl_lines="5 12 13"
==> content/book/practical-vim.md <==
---
title: "Practical Vim"
date: 2014-11-13 22:11
tag: vim  # Define tag with comma-separated string
---

==> content/tool/vim.md <==
---
title: "Vim"
date: 2013-08-17 07:32
tag:  # Define tag with list
  - vim
---
```

`page.relation` is a list-typed variable, store the meta info of other pages, which have the same tag with current page.

```text hl_lines="3 4 5 6 7 8 9 10 11"
{
	'filename': u'vim.html',
	'relation': [
		{
			'category': u'book',
			'date': '2014-11-13 22:11',
			'filename': u'practical-vim.html',
			'tag': ['vim'],
			'title': 'Practical Vim'
		}
	],
	'tag': ['vim'],
	'title': 'Vim',
	...
}
```
