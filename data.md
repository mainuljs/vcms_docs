## Common API Data.

### $appName
 * Type: Property.
 
Name of the Application.
 
```php  
  echo $appName; // VisualCMS  
```


### $title
 * Type: Property.
 
Title of the Application or page title from an specific page.
 
```php  
  echo $title; // VisualCMS for Publisher
```


### $description
 * Type: Property.
 
Description of the Application or page description from an specific page.
 
```php  
  echo $description;
```


### $content_type
 * Type: Property.
 
 Post content type. Generally two types. Single and Multiple
 
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


### $baseSlider
 * Type: Associative array data.
 
 Data for base slider.
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

### $homePosts
 * Type: Associative array data.
 
 Content data for home page. Maximum 6 to 10 post data.
 homePosts data can be found as array which need to be iterate.
  
 ```markdown
 Array
(
    [0] => Array
        (
		[title] => Blog Post
		[alias] => blog-post
		[introtext] => This is intro...
		[featuredimg] => 
		[created_at] => 2020-11-25 06:11:00
		[cat_title] => Blog
		[cat_alias] => blog
		[catlead] => 0                       
            
        )
 ...
)
 
 ```
 
 
 ### $next
  * Type: Associative array data.
 
 Next Article/Post if available
  
 ### $previous
 * Type: Associative array data.
 
 Previous Article/post if available.
  
 ### $related
  * Type: Associative array data.
 
 Related article data.
 
 
### $recent
  * Type: Associative array data.
 
Recent published article.



### $most
  * Type: Associative array data.
 
 Most viewed articles.
 
 

