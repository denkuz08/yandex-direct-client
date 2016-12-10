Yandex Direct API v5 PHP client
===============================

Поддерживается только 5-ая версия [Yandex.Direct API](https://tech.yandex.ru/direct/doc/dg/concepts/about-docpage/).

### Требования
 * PHP 5.4 и выше с curl-расширением

### Установка  
В файле `composer.json`:
```php
{
    ...
    "require": {
        ...
        "gladyshev/yandex-direct-client": "dev-master"
    }
    ...
}
```

### Использование

```php
use Yandex\Direct\Client;
use Yandex\Direct\Credentials;

$credentials = new Credentials(YOUR_API_LOGIN, YOUR_API_TOKEN);
$api = new Client($credentials);

$response = $api->campaigns->get(
    ['Ids' => [123545345, 23423234]],  // SelectionCriteria
    ['Status', 'Currency', 'Funds']    // FieldNames
);

print_r($response);
  
// [
//     'units' => [
//         'debit' => 10, 
//         'limit' => 50,
//         'rest' => 100500
//     ],
//     'result' => [...]
// ]
```