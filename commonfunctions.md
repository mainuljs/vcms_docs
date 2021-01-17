
### clean_url( $str, $separator, $lowercase ) 
 * $str {string} - string to clean for the url
 * $separator {string} (Optional) - for word separator. Default value is "-". Other can be "_"
 * $lowercase {boolen} (Optional) - lowercase url or not. Default value is FALSE; 

Return url-friendly string. Bengali suported.

```php
  clean_url('clean url friendly string');  // clean-url-friendly-string 
``` 


### text_num( $text, $length) 
 * $text {string} - Full text.
 * $length {integer} - Expected length of the return text.
 * Return: string

Return text from begining to specified length.

```php
  text_num('this is full-text', 2);  // this
``` 
 

### segment($segment, $default, $slash ) 
 * $segment {integer} - segment number of the uri. [1 or 2 or 3]
 * $default {string } (Optional)  - if segment not availabe then return 0 or user define value.
 * $slash {string} (Optional) - if given then return as trailing slash (abc/)

Returns the specified uri segment.

```php
  // http://www.domain.com/abc
  echo segment(1, '', '/'); // abc/
  
``` 


### home() 
 * Return: boolean

return true if it is system root .
  
```php
  // https://domain.com/
  home(); 
  // true;
``` 

  
