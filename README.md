# pokeAPiWrapper.Net
A simple wrapper library for the PokeAPI found here: https://pokeapi.co/.  It is meant to be simple, easy to use and help beginners learn how to use APIs.

## Installation

Under construction

## Example Usage

Under construction

## Documentation

Under construction

### PokeAPI Class

This is the class you use to make API calls.  It uses the HttpClient class to make API calls, so you only ever need to make one PokeAPI object to do all of your calls. This class automatically caches data that you get from the API, so all you need to worry about is just getting the data you want.

#### PokeAPI Methods

##### getResource

This Method gets a singular resource from the API.

###### T getResource<T?>(int resourceID)

Get the resource of T type with the ID of resourceID. If it is not found, it returns null.

###### T getResource<T?>(string resourceName)

Get the resource of T type with the name of resourceName.  If it is not found, it returns null.

###### T getResource<T?>(ApiResource resourceToLoad)

Get the resource of T from the ApiResource resourceToLoad passed.  If it is not found, it returns null. This method is useful to load ApiResource from other ApiResources (ex: to get the Berryirmness Resource resource associated with a a Berry resource).

#### getResourceList

This method gets a list of resources from the API. Returns ResourceList object.  If the list cannot be retrieved from the API, returns null.

###### ResourceList<T>? getResourceList<T>(int limit, int offset, bool loadResources)

Get a list of resources with a type of ApiResource from the API. If the list cannot be loaded, it returns null.
The limit parameter represents how many resources to pull (ex: if the limit is 10, it will pull 10 resources), defaults to 20. 
The offset parameter represents where to start in the list (ex: if the offset is 0, start at the beginning of the list), defaults to 0.
The loadResources parameter determines if all the resources in the list are loaded from the API or not. If set to false, just a link to the resource will be returned. If set to true, all resources in the list will be loaded.

###### ResourceList<T>? getResourceList<T>(string url)

Get a list of resources with a type of ApiResource from the API. If the list cannot be loaded, it returns null.
The url is the url to the resource list.  
Used primarily to get the next or previous batch of a resourceList (ex: passing resourceList.next to this method will allow you to get the next page of resources).

#### clearCache()

Dispose of all data saved in the cache.

#### Resource Objects

All resource objects follow the structure in the [PokeAPI documentation](http://pokeapi.co/docsv2/), but following C# naming conventions. If I get the time, I will update the documentation breaking down all the resources

## Features
* Generate C# objects 
* Automatically caches data
* User Friendly