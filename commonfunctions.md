
## clean_url( $str, $separator, $lowercase ) 
 * @param {string} $str - string to clean for the url
 * @param - {string | optional} $separator - for word separator. Default value is "-". Other can be "_"
 * $lowercase - {boolen | optional} $lowercase - lowercase url or not. Default value is FALSE; 

Return url-friendly string. Bengali suported.

```php
  clean_url('clean url friendly string');  // clean-url-friendly-string 
``` 


## text_num( $text, $length) 
 * @param {string} $text - Full text.
 * @param - {integer} $length - Expected length of the return text.
 * @return - {string}

Return text from begining to specified length.

```php
  text_num('this is full-text', 2);  // this
``` 
 

## segment($segment, $default, $slash ) 
 * @param {integer} $segment - segment number of the uri. [1 or 2 or 3]
 * @param {string | Optional} $default - (optional) if segment not availabe then return 0 or user define value.
 * @param {string | Optional } $slash - (Optional) if given then return as trailing slash (abc/)

Returns the specified uri segment.

```php
  // http://www.domain.com/abc
  echo segment(1, '', '/'); // abc/
  
``` 


## home() 
 * @return {boolean}  true | false;

return true if it is system root .
  
```php
  // https://domain.com/
  home(); 
  // true;
``` 

  
