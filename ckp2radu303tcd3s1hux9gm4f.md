## Notes for Cisco Certified Devnet Associate - Snippet 2

In [Snippet 1](https://routeswitch.in/notes-for-cisco-certified-devnet-associate/) we saw that Computers/machines communicating with each other might use different encoding/data formats. 

> The three formats that are heavily used in the networking world for the exchange of data are JSON, XML  and YAML.

## Objects

So all the languages described above are used in denoting what is called _objects_. Let's deep dive a bit. An object is a container for information. It is how we pass information between machines through API. So we need a way to describe the object, don't we? A way to describe the characteristics of the object.

> The multiple characteristics can always be denoted by key-value pairs. 

Say for example let's take an object which denotes an employee. An employee might have the following attributes. An ID number, a name, a department etc. All these characteristics can be described as a key and value pair.

Let us look into the details of the object language one by one:-

## XML ( eXtensible Markup Language )
![XML](https://bl6pap003files.storage.live.com/y4mSxvWGsw4nOk2xp1Mw5vvwB1aSaOVWX1NxxtX2QpnHjQFPZRsWbX1GBCQzHm5En0qsoX9gie-QNSWjHNOSDlUIvZYzTVFANYUx4bnh-jgUNbuAB3ymL7HFoSymRFXDWYGZ44KmDZepTWm1v78GMJzAY0AiriIzsbNKZmmkvtEMAuTcDpgq2buI3dJE_W3Mllo?width=1000&height=600&cropmode=none)

Amongst the discussed formats, XML is the heaviest data type; very difficult to comprehend by humans. It is often used when lots of data is exchanged between machines. If the XML data is very small then we can attempt to understand it with some effort. 
> But as the structure grows heavier, it becomes highly difficult to comprehend and interpret.

#### [Semantics](https://www.w3.org/XML/)

XML has been the language for the machine to machine communications for a very long time. It is very similar to HTML. Some of the key features of XML are:-

* It's a markup language.
* XML uses a system of tags to denote key-value pairs
* Tags are used in the format ``<tags></tags>``
* The value is contained inside a tag pair ``<key>value</key>``
* XML is case sensitive in the tag usage.

Let us look at a sample XML file to understand the semantics described above.
```
<employee>
  <name>Arjuna</name>
  <location>
    <city>Delhi</city>
    <state>Delhi</state>
  </location>
  <roles>Network Engineer</roles>
  <roles>Blogger</roles>
</employee>
```
___

## JSON ( JavaScript Object Notation)
![JSON](https://bl6pap003files.storage.live.com/y4moZgTRXiUbHO5QhUog20bUnWp_PI0Rjr-_MjC1mhVSm9pzSauqZOW8j938w4B_ceqENqybr3U4-cdWAdqSi2g6QoeAMAOHoLhTCHAjA-5ykG4kZK3RoNOpjGZrB740Y5-o9f-SVgpGHAdnjU9q3pEf4tdA5pl5sG_eb2_jrCmkut7siJZKOcKuT0GCIT0Y5Z4?width=997&height=501&cropmode=none)

If we compare the painfully heavy nature of XML with JSON, JSON is very light and more human-readable. But why was JSON needed in the first place? Imagine you are running an application on your phone. The application might fetch data from the server. Now, what format will you choose for the data exchange? Will you send HTML? Will you send plain text?  Now the plain text will increase complications at the client side. How would the client know about the data it has received? So in this object-oriented world, we need a structured data exchange between the client-server architecture. In this case, JSON comes to the rescue. It is a notation that will help applications running Javascript easily parse and get the value of objects. 

> Will it help only Javascript users?

No, it has become a common object notation language that is now being used by multiple languages. Many come with built-in or custom libraries to parse and use JSON objects.

#### Semantics

Some key points to keep in mind while constructing a JSON file.

* The syntax makes use of {} (curly braces) , [] (square braces and) , comma.
* Whitespaces don't matter.
* The Tag concept is not used here.

We can open a JSON object by using {} and go on to list the key-value pairs. Both the key and value are to be surrounded by quotes " if there is a need to denote the value as a string. Multiple attributes of an object are separated from each other using ','.

Let us look at the same data we represented using the YAML file above through JSON constructs:-

```
{
    "employee": {
        "name": "Arjuna", 
        "location": {
            "city": "Delhi", 
            "state": "Delhi"
        },
        "roles": [
            "network engineer",
            "blogger"
        ]
    }
}
```

> Notice how the square braces are used to denote an array in JSON ( Compared to the hyphens we used in YAML)

___

## [YAML ( YAML Aint Markup Language)](https://yaml.org/)

![YAML](https://bl6pap003files.storage.live.com/y4mzx_DACUjA79FuIwwhWUA05HTa4hjMWftJOvynqjTY_MonkMUvGwzfhjY8C9SWCAKQAWAocfuNYfI3hnQMVv9t8MlTDeXGBbeE620mQzBUj2FSnqYkegWncqwe4WCW5bHKIQ5qNI86VlOMxaGXgzCJ8HLEGQCf3PlOF3dT84gjaNJ3Ic6o29X4CZdXxz_U6GA?width=1024&height=353&cropmode=none)


YAML language was designed with one and the only thing in mind. 
> Human readability

It is designed to be a very clean language. As a developer, you can use two extensions for YAML files. They are yml and yaml. Both are acceptable.  We see YAML being converted to XML and JSON to make it mode machine-readable in a few use cases. YAML is mostly used to define configurations. It uses indentation to structure or define the objects. So people who are familiar with Python can understand YAML structure very easily.

#### Semantics

Some key points to keep in mind while constructing a YAML file.

* YAML is not a markup language. 
* There is no concept of tags.
* Whitespaces matter in YAML. Let us look at a sample YAML file.


```
---
employee:
  name: Arjuna
  location:
    city: Delhi
    state: Delhi
  roles:
    - network engineer
    - blogger

```
All data of a particular object uses the same indentation level. Key-value pairs are separated by the use of colon ":". "_ _ _" mentions the start of a YAML file.

In YAML, typically two spaces are used for indentation, but we can use any form of indentation we are comfortable with.

> Remember indentation using TABS is not supported in YAML. Use 2 space / 4 space indentations. 

YAML assumes the data type of the attributes based on the content. This applies to numbers strings etc. So there is no explicit need to append " to strings. Also note that there is no comma "," at the end of the value of a key-value pair. To denote the values forming part of a list use the dash/ hyphen "-" symbol.

___

Hope this article gave an introduction to various encoding languages used in API communication. Bye.