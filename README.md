# Philippine Regions, Provinces, Municipalities scraper

## Usage
All returns are in json format

```
<?php
include "vendor/autoload.php";

use WarrenCA\PhilippineTowns\Parser;
use WarrenCA\PhilippineTowns\IoC;

// Basic Usage
// Create IoC for 'parser', you must always call this
// before using the Parser::getArea()
IoC::bind('parser', function(){
	return new Parser(new WarrenCA\PhilippineTowns\ParserHook);
});

// Will only return list of regions
// look for build/regions-only.json
echo $regions = Parser::getArea("Regions");

// // Will only return list of provinces
// // look for build/provinces-only.json
// $provinces = Parser::getArea("Provinces");

// // Will only return list of municipalities
// // look for build/municipalities-only.json
// $municipalities = Parser::getArea("Municipalities");

// // Will return list of regions
// // look for build/regions-all.json
// $regions = Parser::getArea("Regions")->all();

// // Will return list of provinces with respective region
// // look for build/provinces-all.json
// $provinces = Parser::getArea("Provinces")->all();

// // Will return list of municipalities with respective province and region
// // look for build/municipalities-all.json
// $municipalities = Parser::getArea("Municipalities")->all();
```
