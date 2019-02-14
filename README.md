# Description

There's now easy way to prevent the fields of type `changed` to be updated when
the host entity is updating. A Drupal [core issue](
https://www.drupal.org/project/drupal/issues/2329253) is dealing with this
issue but os not yet committed. This module covers this lack of API and will be
drop as soon the core issue is fixed.

# How to use it?

When saving an existing entity that has a `changed` field type, mark the field
to be preserved during save:

```php
$node = Node::load(123);
// Change the title.
$node->title->value = 'New title';
// Mark the 'changed' field to be preserved.
$node->changed->preserve = TRUE;
$node->save();
```
