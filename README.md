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


# Annex 

## Observations on Standard Library


#### OBV_DEFINE_DEPRECATED
Marcos use define and definelong which are deprecated in favor of function and procedure per https://plantuml.com/en/preprocessing


#### OBV_DRY

DRY (Don't Repeat Yourself)

The macros are repeated 
    
*  within a file -repeat the macro to add each new parameter
* across files - the macro content is largely the same - but the macro name changes to specify the icon to use
    
#### OBV_CLOSE_COUPLING

Macros are defined in the icon file for each icon.

The parameters, and order of parameters, are fixed.
     
#### OBV_CONSISTENCY

icon sizes
* some have multiple sizes
* for those that have one size, it is not standard/common with the other stdlib libraries

icon files
* some break up the icons into categories sub-directories, some don't
* some have an all.puml file that includes all sprite content per category, some don'target       
    
    
#### OBV_NO_SCALE

There's no way to scale the icons from the macros (the !define statements) except for Material. 

    
#### OBV_NO_TEXTATTRIB

There's no way to change the size, colour etc... of the text description, label, technology fields
            
#### OBV_3PARAMS_MIN

At least 3 parameters are required and are rendered in the diagams  
* alias
* label
* technology

In other words, the marcos force a user to specify things they may not care about e.g. to specify color in this macro, the user needs to specify the preceeding parameters also

So if we wanted a colored or scaled icon only (with no label or technology), we have to implement it ourselves.
    
#### OBV_ALL_PUML

Some libaries have an all.puml that includes all icons and their macros for a given category/subset of icons. 

This allows including all icons by including one file - rather than an include per icon.
    
    

## User Stories

### *As a User, I want X, so I am empowered to do Y*

#### US_HIGHLIGHT
To highlight certain parts of a diagram
* so I can show the relevant or important parts in the context of an overall diagram
* e.g. a diagram may have 10 icons/components, but I want to highlight the ones being discussed or changed in my current system
    
    
#### US_THEME
To use, or create, a theme, 
* so I can create diagams consistent with my other (personal, organisation, company) documentation.
    
    
#### US_ICONSET
To use, or create and contribute, an icon set easily
* so I have all the icons I need for my diagrams
        
#### US_COMPAT_FUTURE
To use my existing diagram code, with future stdlib libraries (even if I don't use all the new features).


### *As a Library Author, I want X, so I am empowered to do Y*