---
layout: default
title: Stata Styleguide - BID SCL
parent: code
nav_order: 1
---

# Stata Styleguide - BID SCL

## A.	Basic guidelines for do-file writers based on Baum (2016) and Cox (2005)

Are our do-files readable and comprehensible – not only today, but also in several months?
To assure this, we might apply some general rules to our codes. In this case the main ones would be:
### 1.	Presentation.
1.1.	Always include a comment containing the version number of your program, your name or initials, and the date the program was last modified above the program line. Be consistent with the information you provide in your do-files. I like to use the command dotemplate to be sure all my do-files are equally structured, and I can keep track of any version of my programs.
### 2.	Names.
2.1.	Use sensible, intelligible names where possible for programs, variables, and macros.
Choose a name for your programs, indicators or variables that does not conflict with anything already existing.
2.2.	Use logical names for logical constants or variables.
Ex. local ok should be 1 if true and 0 if false, permitting idioms such as if ok.

2.3.	Brevity of names is also a virtue. However, no platform on which Stata is currently supported requires an 8-character limit. Tastes are in consequence slowly shifting: an intelligible long name for something used only occasionally would usually be considered preferable to something more cryptic.
Ex.
Indicator name tasa_ocupacion is easy to understand, logical and natural for all users but a bit long.
Indicator name tocu_ci can’t be naturally understood. Let’s avoid this kind of names if it is not a wide well-known acronym (such as PIB, IPC so on).

### 3.	Expressions.
Type expressions so they are readable. Some possible rules are as follows:
a.	Put spaces around each binary operator except ^ (gen z = x + y is clear, but x ^ 2 looks odder than x^2).

b.	and / allow different choices. num / den is arguably clearer than num/den, but readers might well prefer 2/3 to 2 / 3. Overall readability is paramount; compare, for example, hours + minutes / 60 + seconds / 3600 with hours + minutes/60 + seconds/3600.

c.	Put a space after each comma in a function, etc. d. Use parentheses for readability. Note, however, that such a spaced-out style may make it difficult to fit expressions on one line, another desideratum



### 4.	Flow control.

Adopt a consistent style for flow control.
Stata has if, while, foreach, and forvalues structures that resemble those in many mainstream programming languages. Here is our set of rules:
Tab lines consistently after if or else or while or foreach or forvalues.

Do not put anything on a line after a brace—an opening { or a closing } (comments are a possible exception).

Put a space before braces.

Align the i of if and the e of else, and align closing braces } with the i, or the e, or the w of while, or the f of foreach or forvalues:


                                                if ... {
                                                   ...
                                                   ...
                                                }

                                 else {
                                     ...
                                     ...
                                 }

         while ... {
            ...
            ...
         }

               foreach ... {
                   ...
                   ...
               }


Be mindful of the hierarchies of your loops so you don’t lose track of your flow:



                       foreach ano of local anos {
	                         foreach mes of local meses {
		                    …
		                    …
	                         }
                       }


***

You can find further general recommendations following this link: https://journals.sagepub.com/doi/pdf/10.1177/1536867X0500500406
