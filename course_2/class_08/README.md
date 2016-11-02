
## HTTP Request
```
GET /post/245145/ HTTP/1.1
Host: habrahabr.ru
Connection: keep-alive
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/54.0.2840.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Referer: https://habrahabr.ru/post/240219/
Accept-Encoding: gzip, deflate, sdch, br
Accept-Language: en-US,en;q=0.8,ru;q=0.6,uk;q=0.4
Cookie: tmid_no_check=1; _ym_uid=1462305295916250739; _gat=1; ab_test_vacancies_block_group=B; _pk_ref.5.b20b=%5B%22%22%2C%22%22%2C1478119311%2C%22https%3A%2F%2Fwww.google.com.ua%2F%22%5D; _ym_isad=1; _ga=GA1.2.1178804549.1462305294; _pk_id.5.b20b=9be9af2dedbbac5a.1478119311.1.1478119315.1478119311.; _pk_ses.5.b20b=*; _ym_visorc_24049213=w
```

## HTTP Response
```
HTTP/1.1 200 OK
Server: QRATOR
Date: Wed, 02 Nov 2016 20:45:30 GMT
Content-Type: text/html; charset=UTF-8
Transfer-Encoding: chunked
Connection: keep-alive
Keep-Alive: timeout=15
Vary: Accept-Encoding
X-Powered-By: PHP/5.6.22-1+donate.sury.org~trusty+1
X-Frame-Options: SAMEORIGIN
P3P: CP="CAO DSP COR CURa ADMa DEVa PSAa PSDa IVAi IVDi CONi OUR OTRi IND PHY ONL UNI FIN COM NAV INT DEM STA"
X-Content-Type-Options: nosniff
X-Engine: engine-slave
Strict-Transport-Security: max-age=7776000
Content-Encoding: gzip
```

## Типы
* GET
* POST
* PUT
* DELETE
* OPTIONS

## Коды статусов
* 200 OK
* 201 Created
* 400 Bad Request
* 401 Unauthorized
* 403 Forbidden
* 404 Not Found
* 500 Internal Server Error

## Prepare request string

```javascript
var requestData = {
  baseUrl: 'https://en.wikipedia.org/w/api.php',
  format: 'json',
  action: 'query',
  prop: 'revisions',
  rvprop: 'content',
  titles: ['JavaScript', 'ajax', 'http', 'Web development']
}

// write function to use this data and build string:
// https://en.wikipedia.org/w/api.php?format=json&action=query&titles=JavaScript|ajax|http|Web%20development&prop=revisions&rvprop=content
```

## XMLHttpRequest

### Синхронный запрос
```javascript
var req = new XMLHttpRequest();
req.open(
  'GET',
   'https://en.wikipedia.org/w/api.php?format=json&action=query&titles=JavaScript|ajax|http|Web%20development&prop=revisions&rvprop=content',
    false);
req.send(null); // yes it's sync HTTP request! 
console.log(req);
```

### Асинхронный запрос

```javascript
var req = new XMLHttpRequest();
req.open(
  'GET',
   'https://en.wikipedia.org/w/api.php?format=json&action=query&titles=JavaScript|ajax|http|Web%20development&prop=revisions&rvprop=content',
    true);
    
req.addEventListener('load', function() {
  console.log('response received');
  console.log(req);  
});
req.send(null); // yes it's sync HTTP request!
console.log('request sent');
```

### Отправка данных при помощи POST
```javascript
var req = new XMLHttpRequest();
req.open('POST', 'http://jsonplaceholder.typicode.com/users', true);
req.setRequestHeader('Content-type', 'application/json');
    
req.addEventListener('load', function() {
  console.log('response received');
  console.log(req);
  var responseObject = JSON.parse(req.responseText);
  console.log('Parsed response object: %O', responseObject)
});


var userData = {
  userId: 777,
  username: 'someUserName',
  role: 'developer'
}

req.send(JSON.stringify(userData));
console.log('request sent');
```


### Обработка ошибок

```javascript
var req = new XMLHttpRequest();
req.open('PUT', 'http://jsonplaceholder.typicode.com/users', true);
req.setRequestHeader('Content-type', 'application/json');
    
req.addEventListener('load', function() {
  console.log('response received');
  console.log(req);
  if (req.status > 400) {
    return console.log('HTTP request error with code: %s and status text: %s', req.status, req.statusText);       
  }
  var responseObject = JSON.parse(req.responseText);
  return console.log('Parsed response object: %O', responseObject);
});


var userData = {
  userId: 777,
  username: 'someUserName',
  role: 'developer'
}

req.send(JSON.stringify(userData));
console.log('request sent');
```

### Оборачиваем в Promise

```javascript
function createRequestPromise(options){
  return new Promise(function(resolvePromise, rejectPromise) {
    var req = new XMLHttpRequest();
    req.open(options.method, options.url, true);
    req.setRequestHeader('Content-type', options.contentType);
    
    req.addEventListener('load', function() {
      if (req.status > 400) {
          return rejectPromise(new Error(req.statusText));    
      }
      return resolvePromise(req.responseText);
    });
    
    req.send(JSON.stringify(options.data));
  })
}

var userData = {
  userName: 'fooBar',
  role: 'admin'
}

var requestData = {
  method: 'POST',
  url: 'http://jsonplaceholder.typicode.com/users',
  contentType: 'application/json',
  data: userData
}

var request = createRequestPromise(requestData);

request
  .then(function(fetchedData) {
    console.log('Data fetched succesfully: %O', fetchedData);
  })
  .catch(function(err) {
    console.log('Error catched');
    console.log(err);
  })
```







