# Authentication
## Functions
### check_login()
> Check whether loggedIn or not.It returns `username and flag` as global.

**How it works**
```php
public function check_login(){
			
	$user = new Users();
	
	$loggedIn = session('loggedIn');
	$username = $user->log_data('username');				
	$token = session('log_token');			
	$token_validate = $user->check_token();				
	
	//dd(session());	
	if( $loggedIn == FALSE || $username == FALSE || empty($token) ||  $token_validate == FALSE ){			
		$user->add_active_guest($_SERVER['REMOTE_ADDR'], session_id(),  time());
		$user->remove_inactive_users();
		$user->remove_inactive_guests();
		session()->remove(['loggedIn', 'log_token', 'log_data']); //unset everything.				
		return false;
	}else{					
		$user->remove_inactive_users();
		$user->remove_inactive_guests();			
		return true;
	}			
}
```


### is_admin()
> Check user admin.It returns `True or False`

**How is works**
```php
public function is_admin(){
	$user = new Users();	
	$userlevel = $user->log_data('level');	
	$admins = ['9', '8', '7', '6', '5', '4', '3'];
	if(in_array($userlevel, $admins) ){
		return true;
	}else{
		return false;
	}											
} 
```


### get_username()
> Returns loggedIn `user name` from session

**How it works**
```php
public function get_username(){
	$user = new Users();
	return $user->log_data('username');
}
```


### is_loggedIn()
> Returns `loggedIn flag` from session

**How it works**
```php
public function is_loggedIn(){
   return session('loggedIn');
}
``` 

### user_validate($userLevel)
> Check user is valid or not.Return `true or false`.

**How it works**
```php
function user_validate($user_level){
 	$users = new \App\Models\Users();
	
	if($users->user_validate($user_level) )
		return true;
	else
		return false; 
}
```

### segment()
> Return `uri segment`. Return default if not get.

**How it works**
```php
function segment($segment, $default = 0, $slash = ''){
  	
	$request = \Config\Services::request();	
	
	if($request->uri->getTotalSegments() >= $segment) 
		return $request->uri->getSegment($segment).$slash;	
	else
		return $default.$slash; 
}
```

### url()
> Return `uri segment`. return default if not get.

**How it works**
```php
function url($segment, $prep = 'post', $slash = ''){ 
 	if(!empty($prep) ) $prep = $prep.'/'; 	
	$url = base_url()."/".$prep.$segment;		
	return $url.$slash; 
}
```


### home()
> Return `true` if it is homepage

**How it works**
```php
function home(){  	
	$segment_1 = segment(1, '');		
	//no uri means it is homepage
	if(!empty($segment_1) ) return false;
	else return true;
}
```


### show_404()
> Page not found error. supported for CI 3

**How it works**
```php
function show_404(){
   throw \CodeIgniter\Exceptions\PageNotFoundException::forPageNotFound();
}
```


### text_num()
> Return `specific words`.

**How it works**
```php
function text_num($text, $length){
	if(strlen($text) > $length) $text = substr($text, 0, strpos($text, ' ', $length));
	return $text;
}
```


### formatMenu()
> Formats menu array according parent-child. Return an `muti-level array`

**How it works**
```php
 function formatMenu($menu, $parent, $sub_trace=false){
	$menu2 = array();
	foreach($menu as $i => $item){
		if($item['parent'] == $parent){
			$menu2[$item['m_id']] = $item;
			if($sub_trace) $menu2[$item['m_id']]['is_sub']=TRUE;
			$menu2[$item['m_id']]['submenu'] = formatMenu($menu, $item['m_id'], true);
		}
	}		
	return $menu2;
}
```


### see()
> It return `data type` with properties and values

**How it works**
```php
function see($data, $way = ''){
  	if($way === 'dump' ){
		echo "<pre>"; var_dump($data); die();
	}else{
		echo "<pre>"; print_r($data); die();	
	}
}
```

## Properties
 - $loggedIn;
 - $loggedInUser;
 - $userTitle;
 - $userEmail;
 - $userLevel;
