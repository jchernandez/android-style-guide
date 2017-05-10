# Android Style Code

## Index

1. [Project structure](#project-structure)
2. [Naming](#naming)
3. [Resources](#resources)
	3.1. [Layout files](#layout-files)
    3.2. [Resources Ids](#resouces-ids)
4. [Drawables](#drawable-files)
5. [Java](#java)
	5.1 [File Name](#file-name)
    5.2 [Souce Files](#source-files)
    5.3 [Package Name](#package-name)
    5.4 [Classes Name](#classes-names)
    5.5 [Method Names](#method-names)
    5.6 [Constants Names](#constants-names)
    
6 [References](#references)

## Project structure

Package by features and not by layers, Android is already an MVC project on a global structure because it has the Views layer (layouts), Controllers (Activities, Fragments) and Models (all extra Java code). 

So splitting package by layers inside the Java module, it becomes redundant, a better way to package an Android Java module is by features. If the code is divided by features or modules it becomes more readable for developers and can be more efficient to find the Classes, Objects or Components that interacts with some process.

## Naming

In order to have a unified code, the Android components must have their own name convention; all the names must be descriptive.

### Resources

In general use __namespaces__ to the name of all the resources.

* Consider prefix with function, layout or section. E.g.: `error_404, field_name`, `confirmation_message`, etc.

#### Layout files

The naming of layouts should be prefixed according to the table below:

| Component     | Prefix         |
| ------------- |:--------------:|
| Activity      | activity_      |
| Fragment      | fragment_      |
| Dialog        | dialog_        |
| AdapterView	| item_          |
| Menu			| menu_			 |
| View			| view_			 |
| Header		| header_		 |
.

#### Resources Ids

| Component			| Prefix		|
| ----------------- |:-------------:|
| Button			| btn_			|
| TextView			| txt_			|
| ListView			| lv_			|
| RecyclerView		| rv_			|
| TextInputLayout	| input_		|
| ImageView			| img_			|
| CustomView		| cv_			|

In case there are same identifiers in different layouts, elements must be the same and have the same function.

__Example__

`activity_login` has  an `et_email`,
`activity_profile_edit` has an `et_email`

It is safe to use the same id only if in the both layouts `et_email` is an `EditText` and their function is to contain an email text.

It is also recommended to prefix a layout identifier (e.g. `activity_login` -> `login_`) and set short names for the components and add a description, try to keep a short name.


### Drawable Files

Android do not allow creating sub directories to split the assets or drawable components, unless you change the build.gradle to add other directories to the res/ module, so it is better to naming them by their type.

| Assert Type		| Prefix		|
| ----------------- |:-------------:|
| Button			| btn_			|
| Divider			| divider_		|
| Icon				| ic_			|
| Image				| image_		|
| Selector			| input_		|

In case the asset is not defined by its type, it can be prefixed by its function (E.g. `card_backgorund`, `circle_white`, `square_black_rounded`, etc.).

## Java


As the Android uses the Java Code language, the [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html) is the main reference for code style.

### File Name

The source file name consists of the case-sensitive name of the top-level class it contains, plus the .java extension.

### Source files

* Source files are encoded in __UTF-8__.
* Variables are in __CamelCase__.
* Variables must be descriptive.
* No line break before the opening brace.
* Line break after the opening brace.
* Line break before the closing brace.

### Package Name

Package names are all lowercase, with consecutive words simply concatenated together (no underscores). For example:  `com.example.deepspace`, not `com.example.deepSpace` or `com.example.deep_space`.

### Classes Names

Class names are written in __UpperCamelCase__.

Class names are typically nouns or noun phrases. For example: `Character` or `ImmutableList`. Interface names may also be nouns or noun phrases (for example, List), but may sometimes be adjectives or adjective phrases instead (for example, Readable).

There are no specific rules or even well-established conventions for naming annotation types.
Test classes are named starting with the name of the class they are testing, and ending with Test. For example:  `HashTest` or `HashIntegrationTest`.

### Method Names

Method names are written in __lowerCamelCase__.

Method names are typically verbs or verb phrases. For example: `sendMessage` or `stop`.

Underscores may appear in JUnit test method names to separate logical components of the name. One typical pattern is `test<MethodUnderTest>_<state>`, for example `testPop_emptyStack`. There is no One Correct Way to name test methods.

### Constants Names

Constant names use `CONSTANT_CASE`: all uppercase letters, with words separated by underscores. But what is a constant, exactly?


[Google Java Style Guide](https://google.github.io/styleguide/javaguide.html) and [Code Style for Contributors](https://source.android.com/source/code-style) for further information.

---

#### References

[Code Style for Contributors](https://source.android.com/source/code-style)
[Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)
[Package by features, not layers](https://hackernoon.com/package-by-features-not-layers-2d076df1964d)
[Best practices in Android development](https://github.com/futurice/android-best-practices)
