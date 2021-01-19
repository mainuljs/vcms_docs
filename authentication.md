# Authentication
## Functions
### check_login()
> Check whether loggedIn or not.If loggedIn then return `username and flag` as global.

```php
check_login(); 
```


### is_admin()
> Check user admin.It returns `True or False`

```php
is_admin(); 
```


### get_username()
> Returns loggedIn `user name` from session

```php
get_username();
```


### is_loggedIn()
> Returns `loggedIn flag` from session

```php
is_loggedIn();
``` 

### user_validate($userLevel)
* $userLevel - 

> Check user is valid or not.Return `true or false`.

```php
user_validate($level = '');
```

### segment($segment, $default = 0, $slash = '')
* $segment - segment no of the uri. [1 or 2 or 3]
* $default - (optional) if segment not availabe then return 0 or user define value.
* $slash - (Optional) if given then return as trailing slash (abc/)

> segment() function returns the uri segment.

```php
  segment(1, '', '/');
  // abc/
``` 


### home()
> Returns `true or false` . Return true if it is system root

```php
home(); // https://domain.com/
// true
```


### params($lead = '')
> Return url query with the leading separators. 'add'=>'page=2', 'delete'=>['suggested']


### text_num($text, $length)
* $text - 
* $length - 

> Return `specific words`.

```php
text_num($text, $length);
```


### formatMenu($menu, $parent, $sub_trace="")
* $menu - 
* $parent - 
* $sub_trace - 

> Formats menu array according parent-child. Return an `multi-level array`

```php
formatMenu($menu, $parent, $sub_trace=false);
```



### see()
> It returns `data type` with properties and values

```php
see($variablename);
```



### isalphanumeric()
> Check it is alpha numeric or not.Return `true or false`.

```php
isalphanumeric(string $field);
```


### password_check()
> This function check current password.Return `True or False`.

```php
password_check(string $password, string $data)
```


### recaptcha()
> This function checks recapcha.Return `true or false`.

```php
recaptcha($captcha);
```

### formatMenu()
> formatMenu() formats menu array according parent-child. return an muti-level array






## Properties
 - $loggedIn;
 - $loggedInUser;
 - $userTitle;
 - $userEmail;
 - $userLevel;
