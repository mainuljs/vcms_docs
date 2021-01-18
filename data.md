## Common API Data.

### $content_type
 * Type: Property.
Post content type. Generally two type. Single and Multiple
 
```php
  if($content_type === 'single')
  echo $content->title;  
```


### $content
* Type: stdClass Object.

Content return the single Aarticle Post Data as stdClass Object.

```php
stdClass Object
(
    [title] => Our Definitive Guide to Cold and Flu
    [alias] => our-definitive-guide-to-cold-and-flu
    [introtext] => This is intro.... 
    [fulltexts] => This is Full Texts.....
    [featuredimg] => https://domain.com/public/images/uploads/respiratory-1024x554.jpg
    [hits] => 344
    [metakeys] => Guide to Cold, Flu, health
    [metades] => Our Definitive Guide to Cold and Flu 
    [is_menu] => 1
    [access] => 1
    [status] => active
    [cat_id] => 1
    [cat_title] => Blog
    [cat_alias] => blog
    [cat_picture] => https://domain.com/images/paper-boat-2.jpg
    [cat_description] => This is Blog Category. Any one can view blog post in this section
    [cat_status] => active
)
```

```php
 echo $content->title; // Our Definitive Guide to Cold and Flu
 
 echo $content->alias; // our-definitive-guide-to-cold-and-flu
 
```


### $baseSlider - Data for base slider.
 * Type: Associative array data.
 
 Base slider data can be found as array which need to be iterate.
 
 ```markdown
Array
(
    [0] => Array
        (
			[title] => Blog Post
			[alias] => blog-post
			[introtext] => This is intro...
			[featuredimg] => https://domain.com/images/blog-post.jpg 
			[created_at] => 2020-11-25 06:11:00
			[cat_title] => Blog
			[catlead] => 0            
			[cat_alias] => blog
        )
	.....
)
 ```
 
```php

  if( home() ):
   slider($baseSlider); 
  endif;
   
```


