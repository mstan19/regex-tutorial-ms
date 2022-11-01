# Regex-Tutorial-ms

Regular expression (also known as regex) is a sequence of characters that specifies a search pattern in text. Most people have use a form of regex without even realizing it. For instance, have you ever used "find and replace" algorithm? Then, congrats you have used a search variation of regex. If you are interested in learning how regex functions work, then this tutorial is for you. The aim of this gist is to explain regex functions by breaking down each part of the expression and describing what it does. By the end of this tutorial, you will be able to build email validation in JavaScript (JS) using regex. 

## Summary

As mention, this tutorial will go over how to use regex when validating user's email address in JS. For example, a typical email validation will look like this: ```/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/```. This snippet of code will force the user to input an email that meet certain conditions. By the end of this tutorial, you will be able to understand this snippet of code.


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components
When building an email validation function, there are three components to consider: username, domain, and extension. When you put it together, this is what it looks: (username)@(domain).(extension)  . Since each components have different conditons to be met, they are defined within ```()```. 
                ```/^([a-z0-9_\.-]+)@([a-zA-Z0-9-]+)\.([a-z]{2,6})$/```

Username Component ```([a-z0-9_\.-]+)```: This component can have any letters, numbers, dot, and/or hyphens. For instance, ```mstan1``` is a valid username, but ```m$tan1``` is not valid since special characters is not one of the conditions specified in username component. It's worth mentioning that the user does not have to use letters, numbers, dot, and hyphens. The input would still be valid is the user only inputted numbers and letters as shown in the example. The ``` +``` means there is no limit on how characters can be inputted for the user component. See Dot ```\.``` for explanation.

@: The user must include ```@``` in order to consider a valid email.

Domain Component ```([a-zA-Z0-9-]+)```: This component can only have any letters, numbers, and/or hyphens. For example, ```catmail``` is valid domain but ```cat.mail``` is not valid domain since the condition did not include ```\.```. See username component for the ``` +``` explanation. 

Dot: Dots can be used in the username but they are written as ```\.``` since ```.``` means it will matche a single character, without caring what character it actaully is, but ```\.``` means user can use the literal dot.

Extension Component ```([a-z]{2,6})```: In this condition, only 2 to 6 lower case letters can be vaild for the exntion component. For example, ```com``` is valid but ```c``` is not valid since this condition requires at least 2 letters in order to be valid. 
                            

### Anchors


### Quantifiers

### Grouping Constructs

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author
For more information about this application, please email me at melissastan91@gmail.com. Interested in my work? Checkout my GitHUb repositories. My GitHub username is mstan19, and here is my GitHub profile: https://github.com/mstan19.
