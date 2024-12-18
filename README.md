# OSIPi REST Api Integration

## About OSIPi Rest

The OSIPi REST API is HATEOAS based, and provides access to the entire Asset Framework Structure.
For more information about the API itself, please take a look at [the official page](https://techsupport.osisoft.com/Documentation/PI-Web-API/help/getting-started.html). Also, this [article](https://pisquare.osisoft.com/community/developers-club/restful-pi-system-access/blog/2015/04/17/getting-started-with-pi-web-api) goes a long way explaining the concepts.

## Thingworx Implementation.

In thingworx, the following functionality is available:

* Automatically generate the Thingmodel based on the AF from Pi. Generation can be recursive (meaning create a thing for each element in the AF structure) or flat, meaning that you only go one level deep.
* Automatically update the properties values based on the latest OSIPi data.

### Thingworx Entities

* `OsiPiWebConnectorThingTemplate`: Responsable for connecting to OSIPi, and doing basic requests
* `OsiPiWebTransformerThing`: Handles transforming the OSiPi data into an infotable, as well as generating the Thingmodel based on that infotable. 
    * The flat method also looks at the tagId for each property, and includes it in the property name.
    * The generated property descriptions contains essential information about the property, linking it to OsiPi. It cannot be manually modified.
* `OsiPiWebThingShape`: ThingShape that marks all the OSIPi exported elements. A service is availalbe on each allowing the automatic property updates
* `OsiPiUpdaterScheduler`: Automatically updates all properties of all things marked with the above thingshape.

# Authors

Petrisor Lacatus - IOT Presales Engineer, Romania CoE Team

# Disclaimer
By downloading this software, the user acknowledges that it is unsupported, not reviewed for security purposes, and that the user assumes all risk for running it.

Users accept all risk whatsoever regarding the security of the code they download.

This software is not an official PTC product and is not officially supported by PTC.

PTC is not responsible for any maintenance for this software.

PTC will not accept technical support cases logged related to this Software.

This source code is offered freely and AS IS without any warranty.

The author of this code cannot be held accountable for the well-functioning of it.

The author shared the code that worked at a specific moment in time using specific versions of PTC products at that time, without the intention to make the code compliant with past, current or future versions of those PTC products.

The author has not committed to maintain this code and he may not be bound to maintain or fix it.


# License
I accept the MIT License (https://opensource.org/licenses/MIT) and agree that any software downloaded/utilized will be in compliance with that Agreement. However, despite anything to the contrary in the License Agreement, I agree as follows:

I acknowledge that I am not entitled to support assistance with respect to the software, and PTC will have no obligation to maintain the software or provide bug fixes or security patches or new releases.

The software is provided “As Is” and with no warranty, indemnitees or guarantees whatsoever, and PTC will have no liability whatsoever with respect to the software, including with respect to any intellectual property infringement claims or security incidents or data loss.
