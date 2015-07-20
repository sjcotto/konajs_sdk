JS SDK Specs

## Instalation

```
bower install konajs
```

## Configuration

Add some routes

Kona
  .addRoute('users')
  .addRoute('events')
  .addRoute('locations');

## APIs


### Get all objects

Kona.Users.find('', onSuccess);

### Query with pagination

var qs = {
	limit : 10,
	offset : 0,
	where : {
		name : 'bart'
	},
	select : {
		name : 1
	},
	sort : {
		name : 1
	}
};

Kona.Users.find(qs, function onSuccess(users) {
	console.log(users); //Array
});

Kona.Users.findOne(qs, function onSuccess(user) {
	console.log(user); //Object
});

Kona.Users.count(qs, function onSuccess(count) {
	console.log(count); //{count : 1000}
});

returns first 10 users with nane eq to 'bart' sort by name and only return the name of the user (select).

### Post object

Kona.Users.add( {name : 'el barto', age : 10}, function onSuccess(userInfo){
	console.log('User created with id: 'userInfo._id);
});

### Put object

//54bdsfsd431434 User id

Kona.Users.update('54bdsfsd431434', {name : 'el barto', age : 10}, function onSuccess(userInfo){
	console.log(userInfo);
}, onError);

### Delete object

//54bdsfsd431434 User id

Kona.Users.delete('54bdsfsd431434', function onSuccess(){

}, onError);

