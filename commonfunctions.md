## segment( $segment, $default = 0, $slash = '' ) 
 * $segment - segment no of the uri. [1 or 2 or 3]
 * $default - (optional) if segment not availabe then return 0 or user define value.
 * $slash - (Optional) if given then return as trailing slash (abc/)

```php
  segment(1, '', '/');
  // abc/
``` 
  segment() function returns the uri segment.
  
