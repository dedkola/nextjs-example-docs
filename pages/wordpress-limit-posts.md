---
title: Limit posts in WordPress in admin area
---

```
function my_post_queries( $query ) {

  if (is_admin() && $query->is_main_query()){


    if(is_admin()){
      $query->set('max_num_pages', 3);
    }

    if(is_category()){
      $query->set('max_num_pages', 3);
    }

  }
}
add_action( 'pre_get_posts', 'my_post_queries' );
```