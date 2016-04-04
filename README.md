ZF2 SimplePageCrawler module
===================

Version 0.3.0 Created by [Vincent Blanchon](http://developpeur-zend-framework.fr/)

Introduction
------------

SimplePageCrawler is a web page crawler.
You can get informations :

* Title
* Meta (decsription, open graph, etc.)
* H1, H2, etc.
* List of the images
* List of the links

Usage
------------

Get page informations :

```php
$crawler = $this->getServiceLocator('SimplePageCrawler');
$page = $crawler->get('http://www.nytimes.com');

echo sprintf('The title is "%s"', $page->getTitle());
echo sprintf('The description is "%s"', $page->getMeta('description'));
```

Updated: ZF2 2.4.0
The first method get() belongs to ServiceLocator(), the second, use it to get the page information.
```php
$crawler = $this->getServiceLocator()->get('SimplePageCrawler');
$page = $crawler->get('http://www.nytimes.com');

echo sprintf('The title is "%s"', $page->getTitle());
echo sprintf('The description is "%s"', $page->getMeta('description'));
```
You can use th action helper :

```php
$page = $this->simplePageCrawler('http://www.nytimes.com');

echo sprintf('The title is "%s"', $page->getTitle());
echo sprintf('The description is "%s"', $page->getMeta('description'));
```

Advanced usage
------------

You can get Open graph metadatas : 

```php
$page = $this->simplePageCrawler('http://www.nytimes.com');
$metas = $page->getMeta()->getOpenGraph();
```
