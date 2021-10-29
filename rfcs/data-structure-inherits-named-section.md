---
RFC: XXXX
Author: Heinz Wiesinger
Status: Draft
Created: 2021-10-29
Last Modified: 2021-10-29
---

# API Blueprint RFC XXXX: Inherit Named Section in Data Structures Section

## Table of Contents

- [Abstract](#abstract)
- [Motivation](#motivation)
- [Rationale](#rationale)
- [Backwards Compatibility](#backwards-compatibility)

## Abstract

This RFS proposes to inherit `Named section` in the `Data Structures section`
to allow for better structuring and categorization of data structures.

## Motivation

APIs may have a large amount of data structures being used. Currently, all of them are sorted
in a single list, where one can quickly lose overview if the list grows beyong a certain size.

Often the data structures can be grouped into sections, wich allows for a more semantic separation
of the data structures and may lead to better discoverability for larger APIs.

## Rationale

This RFC proposes to inherit `Named section` in the `Data Structures section` to introduce
new functionality that would allow better structure, categorization and description of
data structures. Specifically this adds:

- Support for having named identifiers follow the `Data Structures` keyword
- Allow descriptions in the `Data Structures` section

With `Data Structures section` now being able to carry an identifier, this will
also allow more than one `Data Structures section` to be defined.

### Named identifiers

Inheriting from `Named section` will extend the specification of the `Data Structures section`
to allow definitions of either

```
# Data Structures
```

or

```
# Data Structures <identifier>
```

The implication here is that with the former, original defintion, only one `Data Structures` section
can be present. In order to have more than one section one would have to use the latter structure.

### Descriptions

Inheriting from `Named section` would also introduce the capability to define descriptions for data
structures:

```
# Data Structures Content

These are content related data objects.

## Message (object)

+ text (string) - text of the message
+ author (Author) - author of the message

# Data Structures Users

These are structures for various user types in the system

### Author (object)

+ name: John
+ email: john@appleseed.com
```

## Backwards Compatibility

Since all of the new functionality is optional, there should be no backwards
incompatibility.
