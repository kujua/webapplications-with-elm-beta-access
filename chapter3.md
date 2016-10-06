[ToC](https://github.com/kujua/webapplications-with-elm-beta-access/blob/master/Readme.md)

## Work in Progress

In the first chapter we have seen several Elm application examples. We did not go into details of the implementations and studying Elm code without knowledge of the language is certainly overwhelming. This chapter provides a deeper look into Elm. The goal is that after reading this primer, you can then go back to the examples in the first chapter and understand more what is going on in the implementation of the examples. This chapter is all about the language and the organization of a project, we will meet libraries and tools in Chapter 4.

#### Elm Style Guide and Syntax

The creator of Elm is very clear about how he envisions Elm code to be written. It may not be what you are used to from other languages or would like yourself, but a consistent coding style makes it easier to read code from somebody else or maintain code later.

Editors with Elm plugins as discussed in Chapter 2 may have code formatting already built in. Most of them rely on [elm-format](https://github.com/avh4/elm-format) which can also be run from the command line. It is in *alpha* and at the time of writing (October 2016) there are issues open that may make the formatting fail or format a way you don't want it. By default, the tool overwrites the source code file, so be careful and check the formatted output. When you find an issue, just report it - there are many contributors working on this project and most probably the issue will be resolved in the next release. The tool can be built from source as well, but you will need to have a working Haskell installation on your
computer. See Appendix C for setting this up.

Let's have a look at a short example:

![Listing 3-1]
(https://github.com/kujua/webapplications-with-elm-beta-access/blob/master/assets/example-3-1.png)



![Listing 3-2]
(https://github.com/kujua/webapplications-with-elm-beta-access/blob/master/assets/example-3-1-formatted.png)


#### Elm as functional language

The definition of a functional language is hard to pin down. Many times the discussion about this will go into arguments about pure and impure. Often, functional languages may have features of other paradigms embedded. For example, Scala or F# are certainly considered functional languages, but they also allow imperative or object-oriented constructs.

What we can say for sure is that the main feature of a functional language is that functions are first-class citizens. A function can be seen in mathematical terms as a map of input values to output values and having no other effects than this mapping. When we call such a function we know that nothing else happens to any data outside of this function.

As we have seen in Chapter 1 elm is rooted in Haskell, so it is no surprise that Elm is a functional language with all the features normally associated with the functional paradigm.

*Immutable data*

*Functions are first-class citizens*

*Handling of lists*

*No side effects*

*Avoiding global state*

*Declarative*

*Recursion*



#### Elm as type safe language

* Static Types (no Kinds)


#### Elm as modular language

* Modules

#### Elm Architecture

model - update - view


#### Code Organization

How is an Elm application organized? The simplest way is to have all [Elm architectural parts](#part3-chapter10) in one file:

![Simple Directory Structure]
(https://github.com/kujua/webapplications-with-elm-beta-access/blob/master/assets/elm_directorystructure_simple.png)

Here we have one file - *main.elm* - and access all functions and the model from within this file. Most examples will adhere to this structure.

Everything a little bit more complex will have something like the following:

![Complex Directory Structure]
(https://github.com/kujua/webapplications-with-elm-beta-access/blob/master/assets/elm_directorystructure_complex.png)

We can have a discussion about the additional folders underneath *src*, but the important part is to separate the Elm architectural parts into files. I also believe that the names of models and functions should be a little more descriptive than just *model*, *init*, *update* or *view*.
