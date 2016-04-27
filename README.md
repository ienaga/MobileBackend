MobileBackend for PHP
=======


## Doc
http://mb.cloud.nifty.com/doc/current/rest/common/format.html


## Environment

* PHP 5.x
* Phalcon 1.x, 2.x

# Composer

```
{
    "require": {
       "mobile-backend/phalcon": "*"
    }
}
```

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

## GET

```
$mobileBackend = new MobileBackend();
$json = $mobileBackend
    ->setMethod("GET")
    ->addQuery("target", [$os])
    ->setEndPoint("push")
    ->execute();
```

## POST

```
// message
$message = "A Happy New Year!!";

// send time
$dateTime = new DateTime("2016-01-01 00:00:00");
$dateTime->setTimeZone(new DateTimeZone("UTC"));
$deliveryTime = $dateTime->format("Y-m-d\TH:i:s.\0\0\0\Z");

$mobileBackend = new \MobileBackend\Phalcon\MobileBackend();
$mobileBackend
    ->setMethod("POST")
    ->addQuery("message", $message)
    ->addQuery("deliveryTime", [
        "__type" => "Date",
        "iso" => $deliveryTime
    ])
    ->setEndPoint("push")
    ->execute();
```

## PUT

```
// message
$message = "Edit Message";

// objectId
$objectId = "Edit Push Message ObjectId";

$mobileBackend = new \MobileBackend\Phalcon\MobileBackend();
$mobileBackend
    ->setMethod("PUT")
    ->addQuery("message", $message)
    ->setEndPoint("push/". $objectId)
    ->execute();
```

## DELETE

```
$mobileBackend = new \MobileBackend\Phalcon\MobileBackend();
$mobileBackend
    ->setMethod("DELETE")
    ->setEndPoint("push/" . $objectId)
    ->execute();
```

# commentary

http://qiita.com/ienaga/items/a97a318c833082150980

