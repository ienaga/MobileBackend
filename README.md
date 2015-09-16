# MobileBackend for PHP


## Environment

* PHP 5.x
* Phalcon 1.x, 2.x


# Usage

```
$mobileBackend = new MobileBackend();
$json = $mobileBackend
    ->setMethod("GET")
    ->addQuery("target", [$os])
    ->setEndPoint("push")
    ->execute();
```


