# Authentication

### check_login()
 * Return: boolean

Check whether the user logged in or not. If logged then it returns true, otherwise false.


### get_username()
 * Return: true | NULL

Return the user name when looged in, otherwise return NULL

```php
echo get_username();
```


### user_validate($userlevel)
 * $userlevel { int | optional } - Validate user from 2 to 9 level.
 * Return: boolean

Validate logged in user by there level. Level must be 2 to 9.
if the level is 4 then it validates from 4 to 9. 

```php
 if( user_validate(7) )
 echo "Only 7, 8 and 9 level  can see it.";
 
```

### is_admin()
 * Return: boolean

Check whether a logged in user is admin or not. 3 to 9 level users are considered as admin users.

```php
 if( is_admin() )
 echo "You have permission to delete it.";
 
```


## Global vars to authenticate.

### $loggedIn;
True if the user is logged in, otherwise False.

```php
 if( $loggedIn )
 echo "You can see it.";
 
```

### $loggedInUser;
Return username of the logged in user or NULL.

```php
 if( $loggedIn ) echo "Username: ".$loggedInUser;
 
```
 
### $userTitle;
Return the group title of the logged in user or NULL if not.

```php
 if( $loggedIn ) echo "User Group: ".$userTitle;
 
``` 

### $userEmail;
Return the email address of the logged in user or NULL if not.

```php
 if( $loggedIn ) echo "User Email: ".$userEmail;
 
``` 


### $userLevel;
Return the level of the logged in user or NULL if not.

```php
 if( $loggedIn ) {
  if( is_admin($userLevel) ){
   echo "Only admin can see it";
  }
 }
 
``` 

