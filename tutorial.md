# Regex-Tutorial-ms

Regular expression (also known as regex) is a sequence of characters that specifies a search pattern in text. Most people have use a form of regex without even realizing it. For instance, have you ever used "find and replace" algorithm? Then, congrats you have used a search variation of regex. If you are interested in learning how regex functions work, then this tutorial is for you. The aim of this gist is to explain regex functions by breaking down each part of the expression and describing what it does. By the end of this tutorial, you will be able to build email validation in JavaScript (JS) using regex. 

## Summary

As mentioned, this tutorial will go over how to use regex when validating user's email address in JS. For example, a typical email validation will look like this: ```/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/```. This snippet of code will force the user to input an email that meet certain conditions. By the end of this tutorial, you will be able to understand this snippet of code.


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

When building an email validation function, there are three components to consider: username, domain, and extension. When you put it together, this is what it looks like: (username)@(domain).(extension)  . Since each components have different conditons to be met, they are separated and defined within ```()```. 
                ```/^([a-zA-Z0-9_\.-]+)@([a-zA-Z0-9-]+)\.([a-z]{2,6})$/```

Username Component ```([a-zA-Z0-9_\.-]+)```: This component can have any letters, numbers, dot, and/or hyphens. For instance, ```mstan1``` is a valid username, but ```m$tan1``` is not valid since special characters is not one of the conditions specified in username component. It's worth mentioning that the user does not have to use letters, numbers, dot, and hyphens. The input would still be valid is the user only inputted numbers and letters as shown in the example. The ``` +``` means there is no limit on how characters can be inputted for the user component. See Dot ```\.``` for explanation.

@: The user must include ```@``` in order to be consider a valid email.

Domain Component ```([a-zA-Z0-9-]+)```: This component can only have any letters, numbers, and/or hyphens. For example, ```catmail``` is valid domain but ```cat.mail``` is not valid domain since the condition did not include ```\.```. See username component for the ``` +``` explanation. 

Dot: Dots can be used in the username but they are written as ```\.``` since ```.``` means it will matche a single character, without caring what character it actually is, but ```\.``` means user can use the literal dot.

Extension Component ```([a-z]{2,6})```: In this condition, only 2 to 6 lower case letters can be vaild for the exntion component. For example, ```com``` is valid but ```c``` is not valid since this condition requires at least 2 letters in order to be valid. 
                            

### Anchors

Anchors informs us the start and end of the matching process. Anchors do not actually matches character. The ```^``` informs us the start of the  position in the string; this is before the first character. While ```$``` is the position after the last character in the string. For instance, ```stan1@catmail.com```, the ```^``` will be before the ```s``` while ```$``` is after ```m```.

### Quantifiers

Quantifier sets the number of characters in your string. In our regex email validation function: ```/^([a-zA-Z0-9_\.-]+)@([a-zA-Z0-9-]+)\.([a-z]{2,6})$/```, notice in both username and doamin component have ``` +```. The ``` +``` means there is no limit on how characters can be inputted for the user component. This is added since users can have a short or long username and domain.

In our regex, we have another set of quantifiers. In our extension component, the 2 and 6 in ```{2,6}``` are the quantifiers, which means user can only input only be 2 to 6 letters long (specifically lower case letters) in their extension component.

### Grouping Constructs

For the email validation function, we have groups, which are separted by ```()```. Once the username component is valid (meaning it meets the stated condition), then regex can move on to the next component/match which is domain. For example, the username component is defined as ```([a-zA-Z0-9_\.-]+)```. If the user inputted ``` maze123``` as a username, it's valid and it will go on to the domain component. Remember, user needs to input ```@``` after the username or else it would be invalid.

Disclaimer: Capturing and non-capturing are two types of grouping constructs. We will not be going over capturing and non-capturing groups in this gist.


### Bracket Expressions

Bracket expression (also known as Positive character group) indicates the range of characters to match. For example, ```[mc]stan```, meaning we are matching any letters that start with ```m``` or ```c``` but end with ```stan```. To include a range you can use a dash. For instance, ```[a-zA-Z]stan```, we can look for any lower or upper case letter that ends with ```stan```. 

### Character Classes

Examples of character classes are ```.```, ```\d```, and ```\w```.

For ```.```, see character escapes.

The ````\w``` matches any word character

The ```\s``` matches any white spaces between words.

Note: Both ````\w``` and ```\s``` are not used in email validation.

### The OR Operator

Although we didn't use the OR operator, ```|```, in our email example, we will go over it anyway. For example, ```(m|M)aze```, we are looking for either a lower case or upper case 'm' that has ```aze``` after it. It is importnat to note that regex is case sensitive, which is why we have to include both lower and upper case range. Also, ```(m|M)aze``` and ```(mM)aze``` will return the same because in the latter example the or is implied.

<!-- ### Flags -->

### Character Escapes

Using character escapes indicates that regex should be looking for that specific special character. For instance, dots can be used in the username but they are written as ```\.``` since ```.``` means it will match a single character, without caring what character it actually is, but ```\.``` means user can use the literal dot. Let's use an example of the latter meaning. This example ```.zae``` translates find any character that ends with 'aze', so both ```maze``` and ```daze``` are valid. In the email example, the dot is the escaped character; therefore, it needs the backslash in order to be read as a dot.

## Author

For more information about this application, please email me at melissastan91@gmail.com. Interested in my work? Checkout my GitHUb repositories. My GitHub username is mstan19, and here is my GitHub profile: https://github.com/mstan19.
