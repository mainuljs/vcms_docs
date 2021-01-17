# Authentication
## Functions
### check_login()
> Check whether loggedIn or not.It returns `username and flag` as global.

**How it works**
```php
check_login()			
```


### is_admin()
> Check user admin.It returns `True or False`

**How is works**
```php
is_admin()
```


### get_username()
> Returns loggedIn `user name` from session

**How it works**
```php
get_username()

```


### is_loggedIn()
> Returns `loggedIn flag` from session

**How it works**
```php
is_loggedIn()

``` 

### user_validate($userLevel)
> Check user is valid or not.Return `true or false`.

**How it works**
```php
user_validate($user_level)

```



## Properties
 - $loggedIn;
 - $loggedInUser;
 - $userTitle;
 - $userEmail;
 - $userLevel;
