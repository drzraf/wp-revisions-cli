# Revisions CLI

WP CLI command for managing revisions

## Installation

### as standard plugin

```
wp plugin install https://github.com/trepmal/wp-revisions-cli/archive/master.zip --activate
```

### as wp-cli package (coming soooooooon, hopefully)

```
# wp package install trepmal/wp-revisions-cli
```

## Usage


For a rundown of all commands at any time, run `wp help revisions`


### `wp revisions clean [<keep>]`

For all posts, keep only the last `<keep>` revisions for all posts.

 - `<keep>` *integer*. Defaults to value of `WP_POST_REVISIONS`
 - `--post_type=<post_type>` *string*. Clean revisions for given post type. Default any
 - `--post_id=<post_id>` *integer*. Clean revisions for given post. (Does not yet accept lists)
 - `--hard` use `wp_delete_post_revision()` when deleting, this picks up any potential related data such as meta or comments.

### `wp revisions dump`

Dump all revisions for all posts. Faster than `wp revisions clean -1` since it doesn't query each post.

 - `--hard` Slower. Uses `wp_delete_post_revision()` when deleting, this picks up any potential related data such as meta or comments. Equivalent to `wp revisions clean -1 --hard`
 - `--yes` answer *yes* to confirmation message

### `wp revisions generate [<count>]`

Generate revisions for posts.

 - `<count>` *integer*. Number of revisions to generate per post. Default 15
 - `--post_type=<post_type>` *string*. Generate revisions for given post type. Default any
 - `--post_id=<post_id>` *integer*. Generate revisions for given post. (Does not yet accept lists)

### `wp revisions list`

List revisions.

 - `--post_type=<post_type>` *string*. Generate revisions for given post type. Default any
 - `--post_id=<post_id>` *integer*. Generate revisions for given post. (Does not yet accept lists)
 - `--yes` answer *yes* to confirmation message

### `wp revisions status`

Get revisions status. Namely, the value of `WP_POST_REVISIONS`


## Credits

## License

The MIT License (MIT)  
Copyright (c) 2016 Kailey Lampert  
[Full text license](LICENSE)