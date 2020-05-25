## RFC: How to standardize PlantUML stdlib definition ?

# Problem
The PlantUML Standard Library does not define any uniform way of writing library.
Until now, each library author has made her/his best effort but there are no general guidance to be followed.

# Duration
September 30th 2020


# Proposers

* Crashedmind (crashedmind@gmail.com)
* Arnaud Roques (plantuml@gmail.com)

## How to contribute ?
This RFC is hosted at https://github.com/plantuml/rfc-for-standard-plantuml-stdlib
You can use regular Github tools to open issues or submit modifications.


# Detail

## What it the final user needs ?
This section focus on what people *using* the standard library need.

* Usage has to be simple
* It has to be versatile
* It has to be backward compatible with the existing library


## What it the library author needs ?
This section focus on what people *creating* or *updating* a section of the standard library need.

* Code duplication need to be minimized
* Sprite definition must be very simple
* Macro should be extendable
