MobileBackend for PHP
=======


## Doc
http://mb.cloud.nifty.com/doc/current/rest/common/format.html


## Environment

* PHP 5.x
* Phalcon 1.x, 2.x


# YAML

```
prd:
  nifty:
    domain: mb.api.cloud.nifty.com
    version: /2013-09-01/
    application_key: XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
    client_key: XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
```


# Usage

```
$mobileBackend = new MobileBackend();
$json = $mobileBackend
    ->setMethod("GET")
    ->addQuery("target", [$os])
    ->setEndPoint("push")
    ->execute();
```


# commentary

http://qiita.com/ienaga/items/a97a318c833082150980

