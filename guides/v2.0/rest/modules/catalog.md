---
group: rest
title: Catalog module
version: 2.0
github_link: rest/modules/catalog.md
redirect_from: /guides/v2.0/rest/catalog-notes.html
functional_areas:
  - Integration
  - Catalog
---

The `Catalog` module provides functionality for creating and maintaining products and categories.

## Categories

When you create a {% glossarytooltip 50e49338-1e6c-4473-8527-9e401d67ea2b %}category{% endglossarytooltip %} from Admin, you have the option to configure display and {% glossarytooltip ae8f7f2b-ddfb-41ed-bec3-bed191406fdd %}search engine optimization{% endglossarytooltip %} settings. To configure these settings using `POST V1/categories`, you can specify the following parameters as `attribute_code` values:

```
all_children
children
children_count
custom_apply_to_products
custom_design
custom_design_from
custom_design_to
custom_layout_update
custom_use_parent_settings
default_sort_by
description
display_mode
filter_price_range
image
is_anchor
landing_page
meta_description
meta_keywords
meta_title
page_layout
path
path_in_store
url_key
url_path
```

Third-party modules may define other custom attributes.

The following example uses the `POST V1/categories` call to assign four custom attributes to the "My New Category" category.

{% highlight json %}

{
"category": {
    "parent_id": 2,
    "name": "My New Category",
    "is_active": true,
    "level": 2,
    "include_in_menu": true,
    "custom_attributes":[
         {
            "attribute_code":"description",
            "value":"Women category description"
         },
         {
            "attribute_code":"meta_title",
            "value":"Women meta title"
         },
         {
            "attribute_code":"meta_keywords",
            "value":"Women meta keywords"
         },
         {
            "attribute_code":"meta_description",
            "value":"Women meta description"
         },
         {
            "attribute_code":"url_key",
            "value":"women-test-key"
         }
      ]
    }
}
{% endhighlight %}
