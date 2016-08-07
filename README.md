DotNetRandomNameGenerator
=========================

Generates random people and place names drawn from freely available US census data.

[![Join the chat at https://gitter.im/m4bwav/DotNetRandomNameGenerator](https://badges.gitter.im/m4bwav/DotNetRandomNameGenerator.svg)](https://gitter.im/m4bwav/DotNetRandomNameGenerator?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Nuget package: https://www.nuget.org/packages/RandomNameGeneratorLibrary/

The library contains a stripped down lists of human names from the US Census names list, and a list of place names from another census list. The library allows you to get random first and last names or both and you can get male and female first names. You can also generate random place names as well. To access this functionality create a NameGenerator in namespace RandomNameGenerator, and call one of the functions like GenerateRandomFirstAndLastName(). The functions names describe literally and simply what those functions do.

Typical Usage (generating a person name):  
```C#
var personGenerator = new PersonNameGenerator();
var name = _personGenerator.GenerateRandomFirstAndLastName();
	
Console.WriteLine(name); //Outputs some random first and last name combination in the format "{first} {last}" example: "Mark Rogers"
```

Generating a place name:
```C#
var placeGenerator = new PlaceNameGenerator();
var name = _personGenerator.GenerateRandomPlaceName();
	
Console.WriteLine(name); //Outputs some random place name, example: "Hoboken"
```
Male and female first names can be generated with or without a last name
```C#
var personGenerator = new PersonNameGenerator();
var name = _personGenerator.GenerateRandomFemaleFirstName();
	
Console.WriteLine(name); //Outputs some random first female name, example: "Jane"
```

More than one name can be generated at a time.  There are a variety of functions that let you choose gender if desired, and the number of names to be produced.
```C#
var personGenerator = new PersonNameGenerator();
var numberOfNames = 1;
var names = _personGenerator.GenerateRandomFemaleFirstAndLastName(numberOfNames);
var name = names.First();
	
Console.WriteLine(name); //Outputs some random first and last female name combination in the format "{first} {last}" example: "Rose Jones"
```