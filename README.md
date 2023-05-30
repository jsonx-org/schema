# JSON Schema Definition Language

> **JSON Schema for the enterprise**

[![Build Status](https://github.com/jsonx-org/schema/actions/workflows/test.yml/badge.svg)](https://github.com/jsonx-org/schema/actions/workflows/test.yml)
[![XSD](https://img.shields.io/badge/schema.xsd-v0.4-blue.svg)](http://jsonx.org/schema-0.4.xsd)
[![JSDx](https://img.shields.io/badge/schema.jsdx-v0.4-blue.svg)](http://jsonx.org/schema-0.4.jsdx)
[![JSD](https://img.shields.io/badge/schema.jsd-v0.4-blue.svg)](http://jsonx.org/schema-0.4.jsd)<br>
[![Build Status](https://img.shields.io/badge/test-passing-orange.svg)](https://github.com/jsonx-org/schema/actions/workflows/test.yml)
[![XSD](https://img.shields.io/badge/schema.xsd-v0.3-orange.svg)](http://jsonx.org/schema-0.3.xsd)
[![JSDx](https://img.shields.io/badge/schema.jsdx-v0.3-orange.svg)](http://jsonx.org/schema-0.3.jsdx)
[![JSD](https://img.shields.io/badge/schema.jsd-v0.3-orange.svg)](http://jsonx.org/schema-0.3.jsd)<br>
[![Build Status](https://img.shields.io/badge/test-passing-yellow.svg)](https://github.com/jsonx-org/schema/actions/workflows/test.yml)
[![XSD](https://img.shields.io/badge/schema.xsd-v0.2-yellow.svg)](http://jsonx.org/schema-0.2.xsd)
[![JSDx](https://img.shields.io/badge/schema.jsdx-v0.2-yellow.svg)](http://jsonx.org/schema-0.2.jsdx)
[![JSD](https://img.shields.io/badge/schema.jsd-v0.2-yellow.svg)](http://jsonx.org/schema-0.2.jsd)<br>
[![Build Status](https://img.shields.io/badge/test-passing-yellow.svg)](https://github.com/jsonx-org/schema/actions/workflows/test.yml)
[![XSD](https://img.shields.io/badge/schema.xsd-v0.1-yellow.svg)](http://jsonx.org/schema-0.1.xsd)
[![JSDx](https://img.shields.io/badge/schema.jsdx-v0.1-inactive.svg)]()
[![JSD](https://img.shields.io/badge/schema.jsd-v0.1-inactive.svg)]()

## Abstract

This document specifies the <ins>JSON Schema Definition Language</ins>, which allows for the description of the structure and to constrain the contents of JSON documents. The <ins>schema language</ins> is represented in two different but equally translatable vocabularies: a JSON vocabulary, and an XML vocabulary. The <ins>schema language</ins> extends the capabilities found in JSON documents.

## Table of Contents

<samp>&nbsp;&nbsp;</samp>1 [<ins>Introduction</ins>](#1-introduction)<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;</samp>1.1 [Dependencies on Other Specifications](#11-dependencies-on-other-specifications)<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;</samp>1.2 [Conventions Used in This Document](#12-conventions-used-in-this-document)<br>
<samp>&nbsp;&nbsp;</samp>2 [<ins>Purpose</ins>](#2-purpose)<br>
<samp>&nbsp;&nbsp;</samp>3 [<ins>Requirements</ins>](#3-requirements)<br>
<samp>&nbsp;&nbsp;</samp>4 [<ins>Specification</ins>](#4-specification)<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.1 [Schema Document][#schema]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2 [Constraint Types][#constraint-types]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.1 [<code>boolean</code>][#boolean]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.2 [<code>number</code>][#number]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.2.1 [<code>number.scale</code>][#number-scale]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.2.2 [<code>number.range</code>][#number-range]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.3 [<code>string</code>][#string]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.3.1 [<code>string.pattern</code>][#string-pattern]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.4 [<code>object</code>][#object]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.4.1 [<code>object.properties</code>][#object-properties]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.4.2 [Property Names][#property-names]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.4.3 [<code>object.abstract</code>][#object-abstract]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.4.4 [<code>object.extends</code>][#object-extends]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.4.4.1 [Type Declarations][#object-type-declarations]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.4.4.2 [Object Properties][#object-object-properties]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.5 [<code>array</code>][#array]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.5.1 [<code>array.elements</code>][#array-array-elements]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.5.2 [<code>array.minIterate</code> and <code>array.maxIterate</code>][#array-iterate]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.6 [<code>reference</code>][#reference]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.6.1 [<code>reference.type</code>][#reference-type]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.6.1.1 [Object Properties][#reference-object-properties]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.6.1.2 [Array Elements][#reference-array-elements]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.7 [<code>any</code>][#any]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.7.1 [<code>any.types</code>][#any-types]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.7.1.1 [Object Properties][#any-object-properties]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.7.1.2 [Array Elements][#any-array-elements]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.3 [Type Declarations][#type-declarations]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.4 [Object Properties][#object-properties]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.5 [Array Elements][#array-elements]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.6 [Language specific bindings][#bindings]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.6.1 [Type Bindings][#type-bindings]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.6.2 [Field Bindings][#field-bindings]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.6.3 [Type/Field Bindings][#typefield-bindings]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.6.4 [Examples](#464-examples)<br>
<samp>&nbsp;&nbsp;</samp>5 [<ins>Related Resources for JSON Schema</ins>](#5-related-resources-for-json-schema)<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;</samp>5.1 [Schemas for JSON Schema](#51-schemas-for-json-schema)<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>5.1.1 [Current](#511-current)<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>5.1.2 [Obsolete](#512-obsolete)<br>
<samp>&nbsp;&nbsp;</samp>6 [<ins>Sample Schemas</ins>](#6-sample-schemas)<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;</samp>6.1 [`structure.jsdx`](#61-structurejsdx)<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;</samp>6.2 [`structure.jsd`](#62-structurejsd)<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;</samp>6.3 [`datatype.jsdx`](#63-datatypesjsdx)<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;</samp>6.4 [`datatype.jsd`](#64-datatypesjsd)<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;</samp>6.5 [`bindings.jsdx`](#65-bindingsjsdx)<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;</samp>6.6 [`bindings.jsd`](#65-bindingsjsd)<br>
<samp>&nbsp;&nbsp;</samp>7 [<ins>Contributing</ins>](#7-contributing)<br>
<samp>&nbsp;&nbsp;</samp>8 [<ins>Special Thanks</ins>](#8-special-thanks)<br>
<samp>&nbsp;&nbsp;</samp>9 [<ins>License</ins>](#9-license)

## <b>1</b> <ins>Introduction</ins>

This document sets out the structural part of the <ins>JSON Schema Definition Language</ins>. It also contains a directory of links to these related resources.

The <ins>JSON Schema Definition Language</ins> is designed to describe JSON documents by using schema components to constrain and document the meaning, usage and relationships of their constituent parts: value types and their content. Schemas may also provide for the specification of additional document information, such as normalization and defaulting of values. Schemas have facilities for self-documentation. Thus, the <ins>JSON Schema Definition Language</ins> can be used to define, describe and catalogue JSON vocabularies for JSON documents.

Any application that consumes well-formed JSON can use the <ins>JSON Schema Definition Language</ins> formalism to express syntactic, structural and value constraints applicable to its document instances. The <ins>JSON Schema Definition Language</ins> formalism allows a useful level of constraint checking to be described and implemented for a wide spectrum of JSON applications. However, the language defined by this specification does not attempt to provide _all_ the facilities that might be needed by any application. Some applications may require constraint capabilities not expressible in this language, and so may need to perform their own additional validations.

### <b>1.1</b> Dependencies on Other Specifications

The definition of the <ins>JSON Schema Definition Language</ins> depends on the following specifications: [RFC4627<sup>❐</sup>][rfc4627], [RFC7159<sup>❐</sup>][rfc7159], and [XMLSchema<sup>❐</sup>][xmlschema].

### <b>1.2</b> Conventions Used in This Document

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC2119][rfc2119].

## <b>2</b> <ins>Purpose</ins>

Provide a <ins>schema language</ins> to describe normative contracts between producer and consumer ends of a protocol exchanging JSON documents.

## <b>3</b> <ins>Requirements</ins>

1. The <ins>schema language</ins> MUST constrain and document the meaning, usage, constraints and relationships of the constituent parts of a JSON document.

1. The <ins>schema language</ins> MUST provide meaningful and useful constraint rules for the 5 JSON value types: `boolean`, `number`, `string`, `object`, and `array`.

1. The <ins>schema language</ins> MUST support schema descriptions for any and all legal JSON documents, as specified by [RFC2119][rfc2119].

1. The <ins>schema language</ins> MUST be free-of and agnostic-to patterns specific to any particular programming language.

1. The <ins>schema language</ins> MUST be able to describe itself.

## <b>4</b> <ins>Specification</ins>

The <ins>JSON Schema Definition Language</ins> (JSD) is normatively defined in an <ins>XML Schema Document</ins>, with translations expressed in the <ins>JSON/XML Schema Definition Language</ins> (JSDx), as well as the <ins>JSON Schema Definition Language</ins> (JSD) itself.

The <ins>JSDx</ins> format offers XML validation, and using an XML IDE like [oXygen XML Editor<sup>❐</sup>][oxygenxml] offers edit-time XML validation, such as:

<img src="https://user-images.githubusercontent.com/1258414/61751752-aae93800-ada9-11e9-88b1-65de08f125b5.png" width="75%">

When using the <ins>JSDx</ins> format with the [oXygen XML Editor<sup>❐</sup>][oxygenxml], the auto-completion features of the editor will guide you in writing the schema. With the <ins>JSDx</ins> format, the XML editor will also validate keys and keyrefs to ensure that declared types are referenced correctly.

The JSD is comprised of 5 structural abstractions:

<samp>&nbsp;&nbsp;</samp>4.1 [Schema Document][#schema]<br>
<samp>&nbsp;&nbsp;</samp>4.2 [Constraint Types][#constraint-types]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.1 [<code>boolean</code>][#boolean]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.2 [<code>number</code>][#number]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.2.1 [<code>number.scale</code>][#number-scale]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.2.2 [<code>number.range</code>][#number-range]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.3 [<code>string</code>][#string]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.3.1 [<code>string.pattern</code>][#string-pattern]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.4 [<code>object</code>][#object]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.4.1 [<code>object.properties</code>][#object-properties]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.4.2 [Property Names][#property-names]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.4.3 [<code>object.abstract</code>][#object-abstract]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.4.4 [<code>object.extends</code>][#object-extends]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.4.4.1 [Type Declarations][#object-type-declarations]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.4.4.2 [Object Properties][#object-object-properties]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.5 [<code>array</code>][#array]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.5.1 [<code>array.elements</code>][#array-array-elements]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.5.2 [<code>array.minIterate</code> and <code>array.maxIterate</code>][#array-iterate]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.6 [<code>reference</code>][#reference]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.6.1 [<code>reference.type</code>][#reference-type]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.6.1.1 [Object Properties][#reference-object-properties]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.6.1.2 [Array Elements][#reference-array-elements]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.7 [<code>any</code>][#any]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.7.1 [<code>any.types</code>][#any-types]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.7.1.1 [Object Properties][#any-object-properties]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.2.7.1.2 [Array Elements][#any-array-elements]<br>
<samp>&nbsp;&nbsp;</samp>4.3 [Type Declarations][#type-declarations]<br>
<samp>&nbsp;&nbsp;</samp>4.4 [Object Properties][#object-properties]<br>
<samp>&nbsp;&nbsp;</samp>4.5 [Array Elements][#array-elements]<br>
<samp>&nbsp;&nbsp;</samp>4.6 [Language specific bindings][#bindings]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.6.1 [Type Bindings][#type-bindings]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.6.2 [Field Bindings][#field-bindings]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.6.3 [Type/Field Bindings][#typefield-bindings]<br>
<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>4.6.4 [Examples](#464-examples)

### <b>4.1</b> Schema Document

The <samp>**schema**</samp> is the root object of the JSD, and contains [type][#type-declarations] definitions.

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Name**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Value**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|:-|:-|:-|
| <samp>( **schema** )</samp><br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp; | <samp>jx:ns</samp><br>&nbsp;<br>&nbsp;<br><samp>jx:schemaLocation</samp><br>&nbsp;<br>&nbsp;<br>&nbsp;<br><samp>doc</samp><br><samp>[a-zA-Z_$][-a-zA-Z\\d_$]*</samp><br>&nbsp;<br>&nbsp; | _Namespace of the JSON Schema._ Required.<br>&nbsp;&nbsp;Used by schema processors to determine to which<br>&nbsp;&nbsp;version of the JSON Schema the JSD is written.<br>_Location URL of namespace._ Optional.<br>&nbsp;&nbsp;Specified as: `"%NAMESPACE_URI% %LOCATION_URL%"`<br>&nbsp;&nbsp;Used by schema processors to determine location of<br>&nbsp;&nbsp;schema definition for a namespace.<br>Text comments. Optional.<br>_[Type Declaration][#type-declarations]_. Optional.<br>&nbsp;&nbsp;Root object definitions that are referenceable<br>&nbsp;&nbsp;throughout the schema. |

<!-- tabs:start -->

###### **JSD**

```json
{
  "jx:ns": "http://www.jsonx.org/schema-0.4.jsd",
  "jx:schemaLocation": "http://www.jsonx.org/schema-0.4.jsd http://www.jsonx.org/schema.jsd",
  ...
}
```

###### **JSDx**

```xml
<schema
   xmlns="http://www.jsonx.org/schema-0.4.xsd"
   xsi:schemaLocation="http://www.jsonx.org/schema-0.4.xsd http://www.jsonx.org/schema.xsd">
  ...
</schema>
```

<!-- tabs:end -->

### <b>4.2</b> Constraint Types

The <ins>Constraint Types</ins> define the constraint properties for the five JSON value types: <samp>**boolean**</samp>, <samp>**number**</samp>, <samp>**string**</samp>, <samp>**object**</samp>, and <samp>**array**</samp>. Aditionally, the <ins>JSON Schema Definition Language</ins> defines two meta <ins>Constraint Types</ins> named <samp>**any**</samp> and <samp>**reference**</samp>.

The JSD has 3 different scopes where <ins>Constraint Types</ins> can be defined, which provide different sets of their own constraint properties that apply to all <ins>Constraint Types</ins>:

1. [Type Declarations][#type-declarations].
1. [Object Properties][#object-properties].
1. [Array Elements][#array-elements].

Each <ins>Constraint Type</ins> supports the `doc` attribute.

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Name**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Value**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|:-|:-|:-|
| <samp>( [**boolean**][#boolean] \|&nbsp;</samp><br><samp>&nbsp;&nbsp;[**number**][#number] \|</samp><br><samp>&nbsp;&nbsp;[**string**][#string] \|</samp><br><samp>&nbsp;&nbsp;[**object**][#object] \|</samp><br><samp>&nbsp;&nbsp;[**array**][#array] \|</samp><br><samp>&nbsp;&nbsp;[any][#any] \|</samp><br><samp>&nbsp;&nbsp;[reference][#reference] )</samp> | <samp>doc</samp><br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp; | Text comments. Optional.<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp; |

<!-- tabs:start -->

###### **JSD**

```json
{ "doc": "Comment for this element",
  ...
}
```

###### **JSDx**

```xml
<any doc="Comment for this element">
  ...
</any>
```

<!-- tabs:end -->

#### <b>4.2.1</b> `boolean`

The <samp>**boolean**</samp> type is used for the boolean values: `true` and `false`.

The <samp>**boolean**</samp> type does not have validation constraints.

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Name**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Value**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|:-|:-|:-|
| <samp>( **boolean** )</samp><br>&nbsp;<br>&nbsp; | <samp>jx:type</samp><br><samp>bindings</samp><br>&nbsp; | <samp>boolean</samp><br>[Bindings declaration][#bindings]<br>&nbsp;&nbsp;Specifies the language specific bindings. |

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations], [object properties][#object-properties], and [array elements][#array-elements]:

```json
{ "jx:type": "boolean" }
```

###### **JSDx**

Usage for [type declarations][#type-declarations] and [array elements][#array-elements]:

```xml
<boolean/>
```

Usage for [object properties][#object-properties]:

```xml
<property xsi:type="boolean"/>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `true` | :white_check_mark: | The value `true`. |
| `false` | :white_check_mark: | The value `false`. |
| `TRUE` | :x: | `TRUE` is not a valid **boolean** type. |
| `FALSE` | :x: | `FALSE` is not a valid **boolean** type. |
| `0` | :x: | `0` is not a valid **boolean** type. |
| `1` | :x: | `1` is not a valid **boolean** type. |
| `"true"` | :x: | Boolean as string. |

#### <b>4.2.2</b> `number`

Used for any numeric type, either integers or floating point numbers.

The <samp>**number**</samp> type defines two constraint properties for <samp>**number**</samp> JSON value type: <samp>scale</samp>, and <samp>range</samp>.

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Name**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Value**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|:-|:-|:-|
| <samp>( **number** )</samp><br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp; | <samp>jx:type</samp><br><samp>scale</samp><br>&nbsp;<br>&nbsp;<br><samp>range</samp><br>&nbsp;<br>&nbsp;<br><samp>bindings</samp><br>&nbsp; | <samp>number</samp><br><samp>(0\|1\|2\|...)</samp><br>&nbsp;&nbsp;The number of digits to the right of the decimal point.<br>&nbsp;&nbsp;**If a value is not specified, the scale is unbounded.**<br>_Numerical range_<br>&nbsp;&nbsp;Specifies the minimum and maximum limits in [interval<br>notation<sup>❐</sup>][interval-notation].<br>[Bindings declaration][#bindings]<br>&nbsp;&nbsp;Specifies the language specific bindings. |

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations], [object properties][#object-properties], and [array elements][#array-elements]:

```json
{ "jx:type": "number" }
```

###### **JSDx**

Usage for [type declarations][#type-declarations] and [array elements][#array-elements]:

```xml
<number/>
```

Usage for [object properties][#object-properties]:

```xml
<property xsi:type="number"/>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `5` | :white_check_mark: | Integer. |
| `-7.12` | :white_check_mark: | Floating point number. |
| `12.332794E-5` | :white_check_mark: | Exponential notation. |
| `"7"` | :x: | Number as string. |

##### <b>4.2.2.1</b> `number.scale`

The `scale` property specifies the maximum number of accepted digits after the decimal point.

A `scale` of `3` represents a number with a maximum of 3 digits after the decimal.<br>A `scale` of `0` represents an integer.

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations], [object properties][#object-properties], and [array elements][#array-elements]:

```json
{ "jx:type": "number", "scale": 2 }
```

###### **JSDx**

Usage for [type declarations][#type-declarations] and [array elements][#array-elements]:

```xml
<number scale="2"/>
```

Usage for [object properties][#object-properties]:

```xml
<property xsi:type="number" scale="2"/>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `5.12` | :white_check_mark: | Floating point number with 2 digits after the decimal point. |
| `9.2E-1` | :white_check_mark: | Exponential notation representing a number with 2 digits after the decimal point. |
| `-0.1` | :white_check_mark: | Floating point number with 1 digit after the decimal point. |
| `8.123` | :x: | Floating point number with 3 digits after the decimal point. |
| `8.3-2` | :x: | Exponential notation representing a number with 3 digits after the decimal point. |
| `"7.65"` | :x: | Number as string. |

##### <b>4.2.2.2</b> `number.range`

The `range` property specifies the numerical range (min and max) of accepted values in [interval notation<sup>❐</sup>][interval-notation].

A `range` of `[0,10]` represents a number between `0` (inclusive) and `10` (inclusive).<br>A `range` of `(0,10)` represents a number between `0` (exclusive) and `10` (exclusive).<br>A `range` of `(1.2E1,)` represents a number greater than `1.2E1` (exclusive).<br>A `range` of `(,-9.8]` represents a number less than `9.8` (inclusive).

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations], [object properties][#object-properties], and [array elements][#array-elements]:

```json
{ "jx:type": "number", "range": "[-2,7.5)" }
```

###### **JSDx**

Usage for [type declarations][#type-declarations] and [array elements][#array-elements]:

```xml
<number range="[-2,7.5)"/>
```

Usage for [object properties][#object-properties]:

```xml
<property xsi:type="number" range="[-2,7.5)"/>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `5.12` | :white_check_mark: | Floating point number between `-2` (inclusive) and `7.5` (exclusive). |
| `0.3E1` | :white_check_mark: | Exponential notation representing a number between `-2` (inclusive) and `7.5` (exclusive). |
| `-2` | :white_check_mark: | Integer between `-2` (inclusive) and `7.5` (exclusive). |
| `7.49999999999` | :white_check_mark: | Floating point number between `-2` (inclusive) and `7.5` (exclusive). |
| `-2.0000000001` | :x: | Floating point number less than `-2` (inclusive). |
| `7.5` | :x: | Floating point number greater than `7.5` (exclusive). |
| `"6.65"` | :x: | Number as string. |

#### <b>4.2.3</b> `string`

The <samp>**string**</samp> type is used for strings of text. It may contain Unicode characters.

The <samp>**string**</samp> type defines one constraint property for <samp>**string**</samp> JSON value type: <samp>pattern</samp>.

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Name**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Value**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|:-|:-|:-|
| <samp>( **string** )</samp><br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp; | <samp>jx:type</samp><br><samp>pattern</samp><br>&nbsp;<br><samp>bindings</samp><br>&nbsp; | <samp>string</samp><br>_Regular expression_<br>&nbsp;&nbsp;Specifies the regular expression.<br>[Bindings declaration][#bindings]<br>&nbsp;&nbsp;Specifies the language specific bindings. |

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations], [object properties][#object-properties], and [array elements][#array-elements]:

```json
{ "jx:type": "string" }
```

###### **JSDx**

Usage for [type declarations][#type-declarations] and [array elements][#array-elements]:

```xml
<string/>
```

Usage for [object properties][#object-properties]:

```xml
<property xsi:type="string"/>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `"Déjà vu"` | :white_check_mark: | String with unicode. |
| `"D\u00e9j\u00e0 vu"` | :white_check_mark: | String with escaped unicode. |
| `""` | :white_check_mark: | Empty string. |
| `"42"` | :white_check_mark: | String representing a number. |
| `42` | :x: | A number. |

##### <b>4.2.3.1</b> `string.pattern`

The `pattern` property is used to restrict a string to a particular regular expression, as defined in JavaScript ([ECMA 262<sup>❐</sup>][ecma262]).

A `pattern` of `^[a-z]+$` represents a string of one or more lowercase latin characters.<br>A `pattern` of `^.{12}$` represents a string of any 12 characters.<br>A `pattern` of `^(\(\d{3}\) )?\d{3}-\d{4}$` represents a string matching a US phone number.

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations], [object properties][#object-properties], and [array elements][#array-elements]:

```json
{ "jx:type": "string", "pattern": "^(\\(\\d{3}\\) )?\\d{3}-\\d{4}$" }
```

###### **JSDx**

Usage for [type declarations][#type-declarations] and [array elements][#array-elements]:

```xml
<string pattern="^(\\(\\d{3}\\) )?\\d{3}-\\d{4}$"/>
```

Usage for [object properties][#object-properties]:

```xml
<property xsi:type="string" pattern="^(\\(\\d{3}\\) )?\\d{3}-\\d{4}$"/>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `"(800) 356-9377"` | :white_check_mark: | String with a 10 digit phone number. |
| `"356-9377"` | :white_check_mark: | String with a 7 digit phone number. |
| `"(888) 356-9377 ext. 111"` | :x: | Unmatched "ext. 111". |
| `"(800) FLO-WERS"` | :x: | Phone number with letters. |
| `""` | :x: | Empty string. |

#### <b>4.2.4</b> `object`

The <samp>**object**</samp> type is used for mapping "keys" to "values".

The <samp>**object**</samp> type defines three constraint properties for <samp>**object**</samp> JSON value type: <samp>abstract</samp>, <samp>extends</samp>, and named <samp>properties</samp>.

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Name**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Value**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|:-|:-|:-|
| <samp>( **object** )</samp><br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp; | <samp>jx:type</samp><br><samp>properties</samp><br>&nbsp;<br><samp>abstract</samp><br>&nbsp;<br><samp>extends</samp><br>&nbsp;<br>&nbsp; | <samp>object</samp><br>_[Property declarations][#object-properties]_<br>&nbsp;&nbsp;Map of object properties.<br><samp>(true\|**false**)</samp><br>&nbsp;&nbsp;Whether the object is not allowed to be instantiated.<br>_Name [<samp>( [**object**][#object] )</samp> type][#object]_<br>&nbsp;&nbsp;Name of root-level object type declaration specifying<br>&nbsp;&nbsp;object inheritence. |

_The default **object** is not very useful, because it has no property mappings._

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations], [object properties][#object-properties], and [array elements][#array-elements]:

```json
{ "jx:type": "object" }
```

###### **JSDx**

Usage for [type declarations][#type-declarations] and [array elements][#array-elements]:

```xml
<object/>
```

Usage for [object properties][#object-properties]:

```xml
<property xsi:type="object"/>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `{}` | :white_check_mark: | An object without properties. |
| `{"foo":"bar"}` | :x: | An object with property "foo" mapping to value "bar". |

##### <b>4.2.4.1</b> `object.properties`

The `properties` property specifies a map of accepted properties for the object.

Keys in the `properties` map are considered as regular expressions (for more info, see [Property Names][#property-names]).<br>Values in the `properties` map are objects specifying accepted [constraint types][#object-properties].

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations], [object properties][#object-properties], and [array elements][#array-elements]:

```json
{ "jx:type": "object", "properties": {
  "foo": { "jx:type": "string", "pattern": "^[a-z]{,3}$", "nullable": true, "use": "optional" } }
}
```

###### **JSDx**

Usage for [type declarations][#type-declarations] and [array elements][#array-elements]:

```xml
<object>
  <property name="foo" xsi:type="string" pattern="^[a-z]{,3}$" nullable="true" use="optional"/>
</object>
```

Usage for [object properties][#object-properties]:

```xml
<property xsi:type="object">
  <property name="foo" xsi:type="string" pattern="^[a-z]{,3}$" nullable="true" use="optional"/>
</property>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `{"foo":"bar"}` | :white_check_mark: | An object with property "foo" mapping to value "bar". |
| `{"foo":""}` | :white_check_mark: | An object with property "foo" mapping to empty string. |
| `{}` | :white_check_mark: | An object without properties is ok, because "foo" is optional. |
| `{"foo":null}` | :white_check_mark: | An object with property "foo" mapping to `null` is ok, because "foo" is nullable. |
| `{"foo":false}` | :x: | An object with property "foo" mapping to `false`. |
| `{"other":""}` | :x: | An object with property "other" mapping to empty string. |

##### <b>4.2.4.2</b> Property Names

Names of object properties are considered as regular expressions. If an object declaration defines a property with the name <samp>"[a-z]+"</samp>, it means that this name matches any property whose name is one or more alpha characters. This also means that the name <samp>"foo"</samp> will only match "foo". If an object defines a property with a regular expression name that matches more than 1 string, the object will accept all the matching names (i.e. an object with multiple properties that match a single property definition with a regular expression name will be valid). If, however, there are multiple defined properties with regular expression name patterns that capture the same name, an associated value will be validated against the first matching property definition. The example below shows an <samp>**any**</samp> property that matches all names. Such a definition of an **object** type will match any object, except for `{}` (because at least one <samp>**any**</samp> property is required).

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations], [object properties][#object-properties], and [array elements][#array-elements]:

```json
{ "jx:type": "object", "properties": {
  ".*": { "jx:type": "any" } }
}
```

###### **JSDx**

Usage for [type declarations][#type-declarations] and [array elements][#array-elements]:

```xml
<object>
  <property name=".*" xsi:type="any"/>
</object>
```

Usage for [object properties][#object-properties]:

```xml
<property xsi:type="object">
  <property name=".*" xsi:type="any"/>
</property>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `{"foo":"bar"}` | :white_check_mark: | Any property is valid. |
| `{"foo":"bar","wow":true}` | :white_check_mark: | Any property is valid. |
| `{"foo":"bar","wow":true,"cool":42}` | :white_check_mark: | Any property is valid. |
| `{}` | :x: | At least one <samp>**any**</samp> property is required. |

##### <b>4.2.4.3</b> `object.abstract`

The `abstract` property specifies whether the declared object is allowed to represent a value instance.

If `abstract` is true, a value of the declared type is allowed to exits.<br>If `abstract` is false, the declared type can only be used as a super-type of another object type declaration specifying the `extends` property that links to the name of the abstract type.<br>_**The `abstract` property is only allowed to appear on [type declarations][#type-declarations].**_

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations]:

```json
{ "myAbstractObject":
    { "jx:type": "object", "abstract": true, "properties": {
      "foo": { "jx:type": "string", "pattern": "^[a-z]{,3}$", "nullable": true, "use": "optional" } } }
}
```

###### **JSDx**

Usage for [type declarations][#type-declarations]:

```xml
<object name="myAbstractObject" abstract="true">
  <property name="foo" xsi:type="string" pattern="^[a-z]{,3}$" nullable="true" use="optional"/>
</object>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `{"foo":"bar"}` | :x: | Instances of `myAbstractObject` are not allowed.<br>Refer to `extends` property below. |

##### <b>4.2.4.4</b> `object.extends`

The `extends` property accepts a name of an **object** type declaration, which specifies object inheritence.

The `extends` property can only specify names of **object** [type declarations][#type-declarations].<br>The `extends` property can specify names of **object** [type declarations][#type-declarations] that are `abstract`, or not.

###### <b>4.2.4.4.1</b> Type declarations

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations]:

```json
{ "myAbstractObject":
    { "jx:type": "object", "abstract": true, "properties": {
      "foo": { "jx:type": "string", "pattern": "^[a-z]{,3}$", "nullable": true, "use": "optional" } } },
  "myRealObject":
    { "jx:type": "object", "extends": "myAbstractObject", "properties": {
      "thisIsCool": { "jx:type": "boolean", "nullable": false } } }
}
```

###### **JSDx**

Usage for [type declarations][#type-declarations]:

```xml
<object name="myAbstractObject" abstract="true">
  <property name="foo" xsi:type="string" pattern="^[a-z]{,3}$" nullable="true" use="optional"/>
</object>
<object name="myRealObject" extends="myAbstractObject">
  <property name="thisIsCool" xsi:type="boolean" nullable="false"/>
</object>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `{"foo":"bar"}` | :white_check_mark: | An instance of `myRealObject` object with property "foo" mapping to value "bar". |
| `{"foo":"bar","thisIsCool":true}` | :white_check_mark: | An instance of `myRealObject` object with property "foo" mapping to value "bar", and "thisIsCool" to true. |
| `{"foo":""}` | :white_check_mark: | An instance of `myRealObject` object with property "foo" mapping to empty string. |
| `{"thisIsCool":true}` | :white_check_mark: | An instance of `myRealObject` object with property "thisIsCool" mapping to true. |
| `{"thisIsCool":null}` | :x: | The property "thisIsCool" is not nullable. |

###### <b>4.2.4.4.2</b> Object Properties

<!-- tabs:start -->

###### **JSD**

Usage for [object properties][#object-properties]:

```json
{ "myAbstractObject":
    { "jx:type": "object", "abstract": true, "properties": {
      "foo": { "jx:type": "string", "pattern": "^[a-z]{,3}$", "nullable": true, "use": "optional" } } },
  "rootObject":
    { "jx:type": "object", "abstract": true, "properties": {
      "myRealObject":
        { "jx:type": "object", "extends": "myAbstractObject", "properties": {
          "thisIsCool": { "jx:type": "boolean", "nullable": false } } }
}
```

###### **JSDx**

Usage for [object properties][#object-properties]:

```xml
<object name="myAbstractObject" abstract="true">
  <property name="foo" xsi:type="string" pattern="^[a-z]{,3}$" nullable="true" use="optional"/>
</object>
<object name="rootObject">
  <property xsi:type="object" extends="myAbstractObject">
    <property name="thisIsCool" xsi:type="boolean" nullable="false"/>
  </property>
</object>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `{"myRealObject": {"foo":"bar"}}` | :white_check_mark: | A `rootObject` object with an instance of `myRealObject` object with property "foo" mapping to value "bar". |
| `{"myRealObject": {"foo":"bar","thisIsCool":true}}` | :white_check_mark: | A `rootObject` object with an instance of `myRealObject` object with property "foo" mapping to value "bar", and "thisIsCool" to true. |
| `{"myRealObject": {"foo":""}}` | :white_check_mark: | A `rootObject` object with an instance of `myRealObject` object with property "foo" mapping to empty string. |
| `{"myRealObject": {"thisIsCool":true}}` | :white_check_mark: | A `rootObject` object with an instance of `myRealObject` object with property "thisIsCool" mapping to true. |
| `{"myRealObject": {"thisIsCool":null}}` | :x: | The property "thisIsCool" is not nullable. |
| `{"thisIsCool":null}` | :x: | The `rootObject` does not declare the "thisIsCool" property. |

#### <b>4.2.5</b> `array`

The <samp>**array**</samp> type is used for ordered member elements.

The <samp>**array**</samp> type defines three constraint properties for <samp>**array**</samp> JSON value type: <samp>minIterate</samp>, <samp>maxIterate</samp>, and member <samp>elements</samp>.

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Name**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Value**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|:-|:-|:-|
| <samp>( **array** )</samp><br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;  | <samp>jx:type</samp><br><samp>elements</samp><br>&nbsp;<br><samp>minIterate</samp><br>&nbsp;<br>&nbsp;<br><samp>maxIterate</samp><br>&nbsp;<br>&nbsp; | <samp>array</samp><br><samp>\[</samp> [Element declaration][#array-elements]<samp> , ...\]</samp><br>&nbsp;&nbsp;Array of member element declarations.<br><samp>(**1**\|2\|...)</samp><br>&nbsp;&nbsp;Specifies the minimum inclusive number of iterations of<br>&nbsp;&nbsp;child member elements.<br><samp>(**1**\|2\|...\|unbounded)</samp><br>&nbsp;&nbsp;Specifies the maximum inclusive number of iterations of<br>&nbsp;&nbsp;child member elements. |

_The default **array** is not very useful, because it has no member elements._

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations], [object properties][#object-properties], and [array elements][#array-elements]:

```json
{ "jx:type": "array" }
```

###### **JSDx**

Usage for [type declarations][#type-declarations] and [array elements][#array-elements]:

```xml
<array/>
```

Usage for [object properties][#object-properties]:

```xml
<property xsi:type="array"/>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `[]` | :white_check_mark: | An array without member elements. |
| `[null]` | :x: | An array with one `null` element. |

##### <b>4.2.5.1</b> `array.elements`

The `elements` property specifies a list of accepted member elements.

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations], [object properties][#object-properties], and [array elements][#array-elements]:

```json
{ "jx:type": "array", "elements": [
    { "jx:type": "boolean", "minOccurs": "0", "maxOccurs": "1" },
    { "jx:type": "string", "minOccurs": "1", "maxOccurs": "2" } ]
}
```

###### **JSDx**

Usage for [type declarations][#type-declarations] and [array elements][#array-elements]:

```xml
<array>
  <boolean minOccurs="0" maxOccurs="1"/>
  <string minOccurs="1" maxOccurs="2"/>
</array>
```

Usage for [object properties][#object-properties]:

```xml
<property xsi:type="array">
  <boolean minOccurs="0" maxOccurs="1"/>
  <string minOccurs="1" maxOccurs="2"/>
</property>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `[true, "hello"]` | :white_check_mark: | An array with one boolean element, and one string element. |
| `["hello"]` | :white_check_mark: | An array with only one string element, since zero boolean elements is allowed. |
| `["hello", "world"]` | :white_check_mark: | An array with only two string elements, since zero boolean elements is allowed. |
| `["hello", "world", "again"]` | :x: | A maximum of 2 string elements is allowed. |
| `[true, "hello", "world"]` | :white_check_mark: | An array with one boolean element and two string elements. |
| `[true, false, "hello"]` | :x: | A maximum of 1 boolean elements is allowed. |
| `[true]` | :x: | A minimum of 1 string elements are required. |
| `["hello", true]` | :x: | The boolean element must precede the string element. |
| `[]` | :x: | At least one string element is required. |

##### <b>4.2.5.2</b> `array.minIterate` and `array.maxIterate`

The `minIterate` and `maxIterate` properties specify the cardinality of allowed iterations (repetitions) of the member elements.

By default, both `minIterate` and `maxIterate` are `1`, which allows a single iteration of the specified member elements.<br>If `minIterate` is `0`, an empty array is valid regardless of the member elements specified.<br>If `maxIterate` is `n`, the sequence of member elements can repeat `n` times.

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations], [object properties][#object-properties], and [array elements][#array-elements]:

```json
{ "jx:type": "array", "minIterate": "0", "maxIterate": "2", "elements": [
    { "jx:type": "boolean", "minOccurs": "0", "maxOccurs": "1" },
    { "jx:type": "string", "minOccurs": "1", "maxOccurs": "2" } ]
}
```

###### **JSDx**

Usage for [type declarations][#type-declarations] and [array elements][#array-elements]:

```xml
<array minIterate="0" maxIterate="2">
  <boolean minOccurs="0" maxOccurs="1"/>
  <string minOccurs="1" maxOccurs="2"/>
</array>
```

Usage for [object properties][#object-properties]:

```xml
<property xsi:type="array" minIterate="0" maxIterate="2">
  <boolean minOccurs="0" maxOccurs="1"/>
  <string minOccurs="1" maxOccurs="2"/>
</property>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `[true, "hello"]` | :white_check_mark: | An array with one boolean element, and one string element. |
| `["hello"]` | :white_check_mark: | An array with only one string element, since zero boolean elements is allowed. |
| `["hello", "world"]` | :white_check_mark: | An array with only two string elements, since zero boolean elements is allowed. |
| `["hello", "world", "again"]` | :white_check_mark: | The 3rd string element satisfies the 2nd iteration. |
| `["hello", "world", "again", "and", "again"]` | :x: | The 5th string element would require 3 iterations, but `maxIterate` is `2`. |
| `[true, "hello", "world", true, "and", "again"]` | :white_check_mark: | An array with two full iterations. |
| `[true, false, "hello"]` | :x: | A maximum of 1 boolean elements is allowed to appear before a required string element. |
| `[true]` | :x: | A minimum of 1 string elements are required. |
| `["hello", true, "world"]` | :white_check_mark: | The boolean element and "world" satisfy the 2nd iteration. |
| `[]` | :white_check_mark: | An empty array is allowed due to `minIterate` set to `0`. |

#### <b>4.2.6</b> `reference`

The <samp>**reference**</samp> type defines one validation constraint: <samp>type</samp>.

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Name**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Value**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|:-|:-|:-|
| <samp>( **reference** )</samp><br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp; | <samp>jx:type</samp><br><samp>type</samp><br>&nbsp;<br><samp>bindings</samp><br>&nbsp; | <samp>reference</samp><br>_Name of [type declaration][#type-declarations]_<br>&nbsp;&nbsp;Name of root-level type declaration to reference.<br>[Bindings declaration][#bindings]<br>&nbsp;&nbsp;Specifies the language specific bindings. |

##### <b>4.2.6.1</b> `reference.type`

The **reference** type is used to restrict content by specifying a single type declaration reference.<br>
_The **reference** type is only allowed to appear as an object property or an array member._

The `type` property specifies the accepted type declaration.

###### <b>4.2.6.1.1</b> Object Properties

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations], [object properties][#object-properties], and [array elements][#array-elements]:

```json
{ "jx:ns": "http://www.jsonx.org/schema-0.4.jsd",
  "myNumber": { "jx:type": "number" },
  "myObject": { "jx:type": "object", "properties": {
    "numOrStr": { "jx:type": "reference", "type": "myNumber" } } }
}
```

###### **JSDx**

Usage for [object properties][#object-properties]:

```xml
<schema xmlns="http://www.jsonx.org/schema-0.4.xsd">
  <number name="myNumber"/>
  <object name="myArray">
    <property name="numOrStr" xsi:type="reference" type="myNumber"/>
  </object>
</schema>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `{"numOrStr":5.2}` | :white_check_mark: | A number is allowed. |
| `{"numOrStr":"hello"}` | :x: | A string is not allowed. |
| `{"numOrStr":false}` | :x: | A boolean is not allowed. |
| `{}` | :x: | The `numOrStr` property is required (by default, all properties specify `use=required`). |

###### <b>4.2.6.1.2</b> Array Elements

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations], [object properties][#object-properties], and [array elements][#array-elements]:

```json
{ "jx:ns": "http://www.jsonx.org/schema-0.4.jsd",
  "myNumber": { "jx:type": "number" },
  "myArray": { "jx:type": "array", "elements": [
    { "jx:type": "reference", "type": "myNumber" } ] }
}
```

###### **JSDx**

Usage for [array elements][#array-elements]:

```xml
<schema xmlns="http://www.jsonx.org/schema-0.4.xsd">
  <number name="myNumber"/>
  <array name="myArray">
    <reference type="myNumber"/>
  </string>
</schema>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `[5.2]` | :white_check_mark: | A number is allowed. |
| `["hello"]` | :x: | A string is not allowed. |
| `[false]` | :x: | A boolean is not allowed. |
| `[]` | :x: | The `any` element is required (by default, all [array elements][#array-elements] specify `minOccurs=1`). |
| `[5.2,6,4,2]` | :white_check_mark: | Repeating occurrences of **myNumber** are allowed (by default, all [array elements][#array-elements] specify `maxOccurs=unbounded)`. |

#### <b>4.2.7</b> `any`

The <samp>**any**</samp> type is used to restrict content by specifying a list of accepted [type declarations][#type-declarations], or an empty list for wildcard.<br>_The **any** type is only allowed to appear as an object property or an array member._

The <samp>**any**</samp> type defines one validation constraint: <samp>types</samp>.

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Name**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Value**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|:-|:-|:-|
| <samp>( **any** )</samp><br>&nbsp;<br>&nbsp; | <samp>jx:type</samp><br><samp>types</samp><br>&nbsp; | <samp>any</samp><br><samp>\[</samp> Name of [type declaration][#array-elements]<samp> , ...\]</samp><br>&nbsp;&nbsp;Array of [type declarations][#type-declarations]. |

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations], [object properties][#object-properties], and [array elements][#array-elements]:

```json
{ "jx:type": "any" }
```

###### **JSDx**

Usage for [array elements][#array-elements]:

```xml
<any/>
```

Usage for [object properties][#object-properties]:

```xml
<property xsi:type="any"/>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `true` | :white_check_mark: | Any constraint type is allowed. |
| `"hello"` | :white_check_mark: | Any constraint type is allowed. |
| `4.53` | :white_check_mark: | Any constraint type is allowed. |
| `{"foo":"bar"}` | :white_check_mark: | Any constraint type is allowed. |
| `[true,"world"]` | :white_check_mark: | Any constraint type is allowed. |
| `[]` | :white_check_mark: | Any constraint type is allowed. |

##### <b>4.2.7.1</b> `any.types`

The `types` property specifies accepted [type declarations][#type-declarations].

###### <b>4.2.7.1.1</b> Object Properties

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations], [object properties][#object-properties], and [array elements][#array-elements]:

```json
{ "jx:ns": "http://www.jsonx.org/schema-0.4.jsd",
  "myNumber": { "jx:type": "number" },
  "myString": { "jx:type": "string" },
  "myObject": { "jx:type": "object", "properties": {
    "numOrStr": { "jx:type": "any", "types": "myNumber myString" } } }
}
```

###### **JSDx**

Usage for [object properties][#object-properties]:

```xml
<schema xmlns="http://www.jsonx.org/schema-0.4.xsd">
  <number name="myNumber"/>
  <string name="myString"/>
  <object name="myArray">
    <property name="numOrStr" xsi:type="any" types="myNumber myArray"/>
  </object>
</schema>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `{"numOrStr":5.2}` | :white_check_mark: | A number is allowed. |
| `{"numOrStr":"hello"}` | :white_check_mark: | A string is allowed. |
| `{"numOrStr":false}` | :x: | A boolean is not allowed. |
| `{}` | :x: | The `numOrStr` property is required (by default, all properties specify `use=required`). |

###### <b>4.2.7.1.2</b> Array Elements

<!-- tabs:start -->

###### **JSD**

Usage for [type declarations][#type-declarations], [object properties][#object-properties], and [array elements][#array-elements]:

```json
{ "jx:ns": "http://www.jsonx.org/schema-0.4.jsd",
  "myNumber": { "jx:type": "number" },
  "myString": { "jx:type": "string" },
  "myArray": { "jx:type": "array", "elements": [
    { "jx:type": "any", "types": "myNumber myString" } ] }
}
```

###### **JSDx**

Usage for [array elements][#array-elements]:

```xml
<schema xmlns="http://www.jsonx.org/schema-0.4.xsd">
  <number name="myNumber"/>
  <string name="myString"/>
  <array name="myArray">
    <any types="myNumber myArray"/>
  </string>
</schema>
```

<!-- tabs:end -->

**Examples**

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp>Value | Pass | Description<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|-:|-|-|
| `[5.2]` | :white_check_mark: | A number is allowed. |
| `["hello"]` | :white_check_mark: | A string is allowed. |
| `[false]` | :x: | A boolean is not allowed. |
| `[]` | :x: | The `any` element is required (by default, all [array elements][#array-elements] specify `minOccurs=1`). |
| `["hello",5.2,"world","foo","bar",6,4,2]` | :white_check_mark: | Repeating occurrences of **myNumber** or **myString** are allowed (by default, all [array elements][#array-elements] specify `maxOccurs=unbounded)`. |

### <b>4.3</b> Type Declarations

The declarative <samp>**type**</samp> objects are immediate children of the <samp>[**schema**][#schema]</samp> object, and represent type definitions that are referenceable throughout the schema, via [`any.types`](#4271-anytypes), [`object.extends`](#4244-objectextends), [`array.elements.reference`](#42612-array-elements), and [`object.properties.reference`](#42611-object-properties). The <samp>**type**</samp> objects inherit constraint properties from <samp>[**model**][#constraint-types]</samp> definitions with the following extensions: (Note that the <samp>**any**</samp> and <samp>**reference**</samp> <ins>Constraint Types</ins> are not available as a declarative <samp>**type**s</samp>).

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Name**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Value**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|:-|:-|:-|
| <samp>( [**boolean**][#boolean] \|&nbsp;&nbsp;</samp><br><samp>&nbsp;&nbsp;[**number**][#number] \|</samp><br><samp>&nbsp;&nbsp;[**string**][#string] \|</samp><br><samp>&nbsp;&nbsp;[**object**][#object] \|</samp><br><samp>&nbsp;&nbsp;[**array**][#array] \|</samp><br><samp>&nbsp;&nbsp;[~~any~~][#any] \|</samp><br><samp>&nbsp;&nbsp;[~~reference~~][#reference] )</samp> | <samp>name</samp><br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp; | _Name of declared type_<br>&nbsp;&nbsp;Name of type declaration to be used as reference<br>&nbsp;&nbsp;throuthout the JSD.<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp; |

<!-- tabs:start -->

###### **JSD**

```json
{ "jx:ns": "http://www.jsonx.org/schema-0.4.jsd",
  ...
  "rootArray": { "jx:type": "array",
    "elements": [...] },
  "rootBoolean": { "jx:type": "boolean" },
  "rootNumber": { "jx:type": "number" },
  "rootString": { "jx:type": "string" },
  "rootObject": { "jx:type": "object",
    "properties": {...} }
 ...
}
```

###### **JSDx**

```xml
<schema xmlns="http://www.jsonx.org/schema-0.4.xsd">
  ...
  <array name="rootArray">
    ...
  </array>
  <boolean name="rootBoolean"/>
  <number name="rootNumber"/>
  <string name="rootString"/>
  <object name="rootObject">
    ...
  </object>
  ...
</schema>
```

<!-- tabs:end -->

### <b>4.4</b> Object Properties

The <samp>**property**</samp> objects define properties for the declarative objects that belong to an <samp>**[object][#object]**</samp>. The <samp>**property**</samp> objects inherit constraint properties from <samp>[**model**][#constraint-types]</samp> definitions with the following extensions:

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Name**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Value**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|:-|:-|:-|
| <samp>( [**boolean**][#boolean] \|&nbsp;</samp><br><samp>&nbsp;&nbsp;[**number**][#number] \|</samp><br><samp>&nbsp;&nbsp;[**string**][#string] \|</samp><br><samp>&nbsp;&nbsp;[**object**][#object] \|</samp><br><samp>&nbsp;&nbsp;[**array**][#array] \|</samp><br><samp>&nbsp;&nbsp;[any][#any] \|</samp><br><samp>&nbsp;&nbsp;[reference][#reference] )</samp> | <samp>use</samp><br>&nbsp;<br><samp>nullable</samp><br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp; | <samp>(**required**\|optional)</samp><br>&nbsp;&nbsp;Specifies whether the property use is required or optional.<br><samp>(**true**\|false)</samp><br>&nbsp;&nbsp;Specifies whether the property is nullable.<br>&nbsp;<br>&nbsp;<br>&nbsp; |

<!-- tabs:start -->

###### **JSD**

```json
{ "jx:ns": "http://www.jsonx.org/schema-0.4.jsd",
  ...
  "rootObject": { "jx:type": "object",
    "properties": {
      "propArray": { "jx:type": "array", "nullable": true, "use": "required",
        "elements": [...] },
      "propBoolean": { "jx:type": "boolean", "nullable": true, "use": "required" },
      "propNumber": { "jx:type": "number", "nullable": true, "use": "required" },
      "propString": { "jx:type": "string", "nullable": true, "use": "required" },
      "propObject": { "jx:type": "object", "nullable": true, "use": "optional",
        "properties": {...} },
      "propReference": { "jx:type": "reference", "nullable": true, "use": "required", "type": "..." },
      ".*": { "jx:type": "any", "nullable": true, "use": "optional", "types": "..." }
    }
  }
 ...
}
```

###### **JSDx**

```xml
<schema xmlns="http://www.jsonx.org/schema-0.4.xsd">
  ...
  <object name="rootObject">
    <property name="propArray" xsi:type="array" nullable="true" use="required">
      ...
    </property>
    <property name="propBoolean" xsi:type="boolean" nullable="true" use="required"/>
    <property name="propNumber" xsi:type="number" nullable="true" use="required"/>
    <property name="propString" xsi:type="string" nullable="true" use="required"/>
    <property name="propObject" xsi:type="object" nullable="true" use="optional">
      ...
    </property>
    <property name="propReference" xsi:type="reference" nullable="true" use="required" type="..."/>
    <property names=".*" xsi:type="any" nullable="true" use="optional" types="..."/>
  </object>
  ...
</schema>
```

<!-- tabs:end -->

### <b>4.5</b> Array Elements

The <samp>**element**</samp> objects define properties for the declarative objects that belong to an <samp>**[array][#array]**</samp>. The <samp>**element**</samp> objects inherit constraint properties from [constraint type][#constraint-types] definitions with the following extensions:

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Name**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Value**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|:-|:-|:-|
| <samp>( [**boolean**][#boolean] \|&nbsp;</samp><br><samp>&nbsp;&nbsp;[**number**][#number] \|</samp><br><samp>&nbsp;&nbsp;[**string**][#string] \|</samp><br><samp>&nbsp;&nbsp;[**object**][#object] \|</samp><br><samp>&nbsp;&nbsp;[**array**][#array] \|</samp><br><samp>&nbsp;&nbsp;[any][#any] \|</samp><br><samp>&nbsp;&nbsp;[reference][#reference] )</samp><br>&nbsp; | <samp>nullable</samp><br>&nbsp;<br><samp>minOccurs</samp><br>&nbsp;<br>&nbsp;<br><samp>maxOccurs</samp><br>&nbsp;<br>&nbsp; | <samp>(**true**\|false)</samp><br>&nbsp;&nbsp;Specifies whether the property is nullable.<br><samp>(0\|**1**\|2\|...)</samp><br>&nbsp;&nbsp;Specifies the minimum inclusive number of occurrence of<br>&nbsp;&nbsp;the member element.<br><samp>(0\|1\|2\|...\|**unbounded**)</samp><br>&nbsp;&nbsp;Specifies the maximum inclusive number of occurrence of<br>&nbsp;&nbsp;the member element. |

<!-- tabs:start -->

###### **JSD**

```json
{ "jx:ns": "http://www.jsonx.org/schema-0.4.jsd",
  ...
  "rootArray": {
    "jx:type": "array",
    "elements": [
      { "jx:type": "boolean", "minOccurs": "1", "maxOccurs": "unbounded", "nullable": true},
      { "jx:type": "number", "minOccurs": "1", "maxOccurs": "unbounded", "nullable": true },
      { "jx:type": "string", "minOccurs": "1", "maxOccurs": "unbounded", "nullable": true },
      { "jx:type": "array", "minOccurs": "1", "maxOccurs": "unbounded", "nullable": true,
        "elements": [...] },
      { "jx:type": "reference", "minOccurs": "1", "maxOccurs": "unbounded", "nullable": true, "type": "..." },
      { "jx:type": "any", "minOccurs": "1", "maxOccurs": "unbounded", "nullable": true, "types": "..." }
    ]
  }
  ...
}
```

###### **JSDx**

```xml
<schema xmlns="http://www.jsonx.org/schema-0.4.xsd">
  ...
  <array name="rootArray">
    <boolean minOccurs="1" maxOccurs="unbounded" nullable="true"/>
    <number minOccurs="1" maxOccurs="unbounded" nullable="true"/>
    <string minOccurs="1" maxOccurs="unbounded" nullable="true"/>
    <array minOccurs="1" maxOccurs="unbounded" nullable="true">
      ...
    </array>
    <reference minOccurs="1" maxOccurs="unbounded" nullable="true" type="...">
    <any minOccurs="1" maxOccurs="unbounded" nullable="true" types="..."/>
  </array>
  ...
</schema>
```

<!-- tabs:end -->

### <b>4.6</b> Language specific bindings

As of <ins>JSON Schema 0.4</ins>, language specific bindings allow schema document declarations to bind information pertainig to zero or many target languages.

Bindings enable a schema to provide schema processors with information to bridge between JSON and the application layer in a custom way.

The binding information is comprised of five identifiers that belong to a single `binding` element:

| <samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Name**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> | **Property&nbsp;Value**<samp>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</samp> |
|:-|:-|:-|
| <samp>( **binding** )</samp><br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp; | <samp>**lang**</samp><br>&nbsp;<br><samp>type</samp><br>&nbsp;<br><samp>decode</samp><br>&nbsp;<br>&nbsp;<br><samp>encode</samp><br>&nbsp;<br>&nbsp;<br><samp>field</samp><br>&nbsp; | The language for which the binding is directed.<br>&nbsp;&nbsp;&nbsp;&nbsp;(i.e. "java", "python", "ruby", "custom").<br>The language specific "type" to which the declaration<br>&nbsp;&nbsp;&nbsp;&nbsp;is to be bound.<br>The method, constructor, or executable that consumes JSON<br>&nbsp;&nbsp;&nbsp;&nbsp;and produces an instance of **type** (if **type** is specified),<br>&nbsp;&nbsp;&nbsp;&nbsp;or of the default native type if **type** is not specified).<br>The method, constructor, or executable that consumes an<br>&nbsp;&nbsp;&nbsp;&nbsp;instance of **type** (if **type** is specified), or of the default<br>&nbsp;&nbsp;&nbsp;&nbsp;native type (if **type** is not specified), and produces JSON.<br>The language specific "field" to which the particular<br>&nbsp;&nbsp;&nbsp;&nbsp;declaration is to be bound. |

<sup>_Note: **lang** has been marked in bold to indicate that it is required property._</sup>

There are three types of `binding` objects:

#### <b>4.6.1</b> <ins>Type Bindings</ins>

<ins>Type Bindings</ins> only allow for the specification of **type**, **decode**, and **encode** properties.

These bindings are allowed on [Type Declarations](#43-type-declarations) and [Array Elements](#45-array-elements)

#### <b>4.6.2</b> <ins>Field Bindings</ins>

<ins>Field Bindings</ins> only allow for the specification of a **field** property.

These bindings are allowed on [`reference` Types](#426-reference), and [Object Properties of type `object`, `array`, or `any`](#4241-objectproperties).

#### <b>4.6.3</b> <ins>Type/Field Bindings</ins>

<ins>Type/Field Bindings</ins> only allow for the specification of all properties: **type**, **decode**, **encode**, and **field**.

These bindings are allowed on [Object Properties of type `boolean`, `number`, or `string`](#4241-objectproperties).

#### <b>4.6.4</b> Examples

1. [`datatypes.jsdx`](#63-datatypesjsdx)
1. [`datatypes.jsd`](#64-datatypesjsd)
1. [`bindings.jsdx`](#65-bindingsjsdx)
1. [`bindings.jsd`](#66-bindingsjsd)

## <b>5</b> <ins>Related Resources for JSON Schema</ins>

### <b>5.1</b> Schemas for JSON Schema

#### <b>5.1.1</b> Current

* <ins>JSON Schema 0.4</ins> **[Current]**

  * A JSON Schema schema document XSD [schema-0.4.xsd](http://www.jsonx.org/schema-0.4.xsd) for JSON Schema documents. It incorporates an auxiliary XSD, [datatypes-0.9.xsd](http://www.openjax.org/xml/datatypes-0.9.xsd).

  * A JSON Schema schema document JSDx [schema-0.4.jsdx](http://www.jsonx.org/schema-0.4.jsdx) for JSON Schema documents.

  * A JSON Schema schema document JSD [schema-0.4.jsd](http://www.jsonx.org/schema-0.4.jsd) for JSON Schema documents.

#### <b>5.1.2</b> Obsolete

* <ins>JSON Schema 0.3</ins> **[Deprecated]**

  * A JSON Schema schema document XSD [schema-0.3.xsd](http://www.jsonx.org/schema-0.3.xsd) for JSON Schema documents. It incorporates an auxiliary XSD, [datatypes-0.9.xsd](http://www.openjax.org/xml/datatypes-0.9.xsd).

  * A JSON Schema schema document JSDx [schema-0.3.jsdx](http://www.jsonx.org/schema-0.3.jsdx) for JSON Schema documents.

  * A JSON Schema schema document JSD [schema-0.3.jsd](http://www.jsonx.org/schema-0.3.jsd) for JSON Schema documents.

* <ins>JSON Schema 0.2</ins> **[Deprecated]**

  * A JSON Schema schema document XSD [schema-0.2.xsd](http://www.jsonx.org/schema-0.2.xsd) for JSON Schema documents. It incorporates an auxiliary XSD, [datatypes-0.8.xsd]( http://www.openjax.org/xml/datatypes-0.8.xsd).

  * A JSON Schema schema document JSDx [schema-0.2.jsdx](http://www.jsonx.org/schema-0.2.jsdx) for JSON Schema documents.

  * A JSON Schema schema document JSD [schema-0.2.jsd](http://www.jsonx.org/schema-0.2.jsd) for JSON Schema documents.

* <ins>JSON Schema 0.1</ins> **[Deprecated]**

  * A JSON Schema schema document XSD [schema-0.1.xsd](http://www.jsonx.org/schema-0.1.xsd) for JSON Schema documents. It incorporates an auxiliary XSD, [datatypes-0.8.xsd](http://www.openjax.org/xml/datatypes-0.8.xsd).

  * A JSON Schema schema document JSDx ~~schema-0.1.jsdx~~ for JSON Schema documents.

  * A JSON Schema schema document JSD ~~schema-0.1.jsd~~ for JSON Schema documents.

### <b>6</b> <ins>Sample Schemas</ins>

This section provides sample schemas in both `jsdx` and `jsd` representations.

#### <b>6.1</b> `structure.jsdx`

```xml
<schema
  xmlns="http://www.jsonx.org/schema-0.4.xsd"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://www.jsonx.org/schema-0.4.xsd http://www.jsonx.org/schema.xsd">
  <array name="array">
    <boolean nullable="true"/>
    <number range="[-1,1)" nullable="true"/>
    <string pattern="pattern" nullable="true"/>
    <array nullable="true">
      <boolean nullable="true"/>
      <number range="[-1,1)" nullable="true"/>
      <string pattern="pattern" nullable="true"/>
      <any types="boolean number string array object"/>
    </array>
    <reference type="object"/>
    <any types="boolean number string array object" nullable="true"/>
  </array>
  <boolean name="boolean"/>
  <number name="number" range="[-1,1)"/>
  <string name="string" pattern="pattern"/>
  <object name="object">
    <property name="array" xsi:type="array" nullable="true" use="required">
      <boolean nullable="true"/>
      <number range="[-1,1)" nullable="true"/>
      <string pattern="pattern" nullable="true"/>
      <array nullable="true">
        <boolean nullable="true"/>
        <number range="[-1,1)" nullable="true"/>
        <string pattern="pattern" nullable="true"/>
        <any types="boolean number string array object"/>
      </array>
      <reference type="object"/>
      <any types="boolean number string array object" nullable="true"/>
    </property>
    <property name="boolean" xsi:type="boolean" nullable="true" use="required"/>
    <property name="number" xsi:type="number" range="[-1,1)" nullable="true" use="required"/>
    <property name="string" xsi:type="string" pattern="pattern" nullable="true" use="required"/>
    <property name="booleanRef" xsi:type="reference" type="boolean" nullable="true" use="required"/>
    <property name="subObject" xsi:type="object" extends="object" nullable="true" use="optional">
      <property name="subBoolean" xsi:type="boolean" nullable="true" use="required"/>
      <property name="subNumber" xsi:type="number" range="[-1,1)" nullable="true" use="required"/>
      <property name="subString" xsi:type="string" pattern="pattern" nullable="true" use="required"/>
      <property name="subBooleanRef" xsi:type="reference" type="boolean" nullable="true" use="required"/>
      <property name="subArray" xsi:type="array" nullable="true" use="required">
        <boolean nullable="true"/>
        <number range="[-1,1)" nullable="true"/>
        <string pattern="pattern" nullable="true"/>
        <array nullable="true">
          <boolean nullable="true"/>
          <number range="[-1,1)" nullable="true"/>
          <string pattern="pattern" nullable="true"/>
          <any types="boolean number string array object"/>
        </array>
        <reference type="object"/>
        <any types="boolean number string array object" nullable="true"/>
      </property>
    </property>
    <property names=".*" xsi:type="any" types="boolean number string array object" nullable="true" use="optional"/>
  </object>
</schema>
```

#### <b>6.2</b> `structure.jsd`

```json
{
  "jx:ns": "http://www.jsonx.org/schema-0.4.jsd",
  "jx:schemaLocation": "http://www.jsonx.org/schema-0.4.jsd http://www.jsonx.org/schema.jsd",
  "array": {
    "jx:type": "array",
    "elements": [{
      "jx:type": "boolean"
    }, {
      "jx:type": "number",
      "range": "[-1,1)"
    }, {
      "jx:type": "string",
      "pattern": "pattern"
    }, {
      "jx:type": "array",
      "elements": [{
        "jx:type": "boolean"
      }, {
        "jx:type": "number",
        "range": "[-1,1)"
      }, {
        "jx:type": "string",
        "pattern": "pattern"
      }, {
        "jx:type": "any",
        "types": "boolean number string array object"
      }]
    }, {
      "jx:type": "reference",
      "type": "object"
    }, {
      "jx:type": "any",
      "types": "boolean number string array object"
    }]
  },
  "boolean": {
    "jx:type": "boolean"
  },
  "number": {
    "jx:type": "number",
    "range": "[-1,1)"
  },
  "string": {
    "jx:type": "string",
    "pattern": "pattern"
  },
  "object": {
    "jx:type": "object",
    "properties": {
      "array": {
        "jx:type": "array",
        "elements": [{
          "jx:type": "boolean"
        }, {
          "jx:type": "number",
          "range": "[-1,1)"
        }, {
          "jx:type": "string",
          "pattern": "pattern"
        }, {
          "jx:type": "array",
          "elements": [{
            "jx:type": "boolean"
          }, {
            "jx:type": "number",
            "range": "[-1,1)"
          }, {
            "jx:type": "string",
            "pattern": "pattern"
          }, {
            "jx:type": "any",
            "types": "boolean number string array object"
          }]
        }, {
          "jx:type": "reference",
          "type": "object"
        }, {
          "jx:type": "any",
          "types": "boolean number string array object"
        }]
      },
      "boolean": {
        "jx:type": "boolean"
      },
      "number": {
        "jx:type": "number",
        "range": "[-1,1)"
      },
      "string": {
        "jx:type": "string",
        "pattern": "pattern"
      },
      "booleanRef": {
        "jx:type": "reference",
        "type": "boolean"
      },
      "subObject": {
        "jx:type": "object",
        "extends": "object",
        "use": "optional",
        "properties": {
          "subBoolean": {
            "jx:type": "boolean"
          },
          "subNumber": {
            "jx:type": "number",
            "range": "[-1,1)"
          },
          "subString": {
            "jx:type": "string",
            "pattern": "pattern"
          },
          "subBooleanRef": {
            "jx:type": "reference",
            "type": "boolean"
          },
          "subArray": {
            "jx:type": "array",
            "elements": [{
              "jx:type": "boolean"
            }, {
              "jx:type": "number",
              "range": "[-1,1)"
            }, {
              "jx:type": "string",
              "pattern": "pattern"
            }, {
              "jx:type": "array",
              "elements": [{
                "jx:type": "boolean"
              }, {
                "jx:type": "number",
                "range": "[-1,1)"
              }, {
                "jx:type": "string",
                "pattern": "pattern"
              }, {
                "jx:type": "any",
                "types": "boolean number string array object"
              }]
            }, {
              "jx:type": "reference",
              "type": "object"
            }, {
              "jx:type": "any",
              "types": "boolean number string array object"
            }]
          }
        }
      },
      ".*": {
        "jx:type": "any",
        "types": "boolean number string array object",
        "use": "optional"
      }
    }
  }
}
```

#### <b>6.3</b> `datatypes.jsdx`

```xml
<schema
  doc="Schema intended to express full variability of type declarations"
  xmlns="http://www.jsonx.org/schema-0.4.xsd"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://www.jsonx.org/schema-0.4.xsd http://www.jsonx.org/schema.xsd">
  <array name="arrayArr" doc="Array of arrays">
    <reference type="arrayBool" maxOccurs="1" doc="Reference to array of booleans"/>
    <reference type="arrayNum" maxOccurs="1" doc="Reference to array of numbers"/>
    <reference type="arrayObj" maxOccurs="1" doc="Reference to array of objects"/>
    <reference type="arrayObj" maxOccurs="1" doc="Another reference to array of objects"/>
    <reference type="arrayStr" maxOccurs="1" doc="Reference to array of strings"/>
    <reference type="arrayStr" maxOccurs="1" doc="Another reference to array of strings"/>
    <any types="defaultDecimal StringDecimal defaultBoolean StringBoolean" minOccurs="0" maxOccurs="1" nullable="false" doc="Any of defaultDecimal, StringDecimal, defaultBoolean, or StringBoolean type"/>
  </array>
  <array name="arrayBool" doc="Array of booleans">
    <any maxOccurs="1" nullable="false" doc="Any type"/>
    <reference type="primitiveBoolean" minOccurs="1" maxOccurs="1" nullable="false" doc="Not-nullable reference to primitiveBoolean"/>
    <reference type="defaultBoolean" minOccurs="1" maxOccurs="1" doc="Reference to defaultBoolean"/>
  </array>
  <array name="arrayNum" doc="Array of numbers">
    <any minOccurs="1" maxOccurs="1" nullable="false" doc="Any type"/>
    <reference type="defaultDecimal" minOccurs="1" maxOccurs="1" doc="Reference to defaultDecimal"/>
    <reference type="byte" minOccurs="1" maxOccurs="1" nullable="false" doc="Reference to byte"/>
    <reference type="StringDecimal" minOccurs="1" maxOccurs="1" doc="Reference to StringDecimal"/>
    <reference type="numRange" minOccurs="1" maxOccurs="1" nullable="false" doc="Reference to numRange"/>
    <reference type="cachedInteger" minOccurs="1" maxOccurs="1" doc="Reference to num"/>
    <reference type="plainDecimal" minOccurs="1" maxOccurs="1" nullable="false" doc="Reference to plainDecimal"/>
    <reference type="cachedPlainDecimal" minOccurs="1" maxOccurs="1" doc="Reference to plainDecimalRange"/>
    <reference type="byte" minOccurs="1" maxOccurs="1" nullable="false" doc="Reference to byte"/>
    <reference type="numRange" minOccurs="1" maxOccurs="1" nullable="false" doc="Reference to numRange"/>
    <reference type="cachedInteger" minOccurs="1" maxOccurs="1" doc="Reference to cachedInteger"/>
    <reference type="defaultDecimalRange2" minOccurs="0" maxOccurs="1" doc="Reference to plainDecimalRange"/>
  </array>
  <array name="arrayObj" doc="Array of object references">
    <reference type="objArr" maxOccurs="1" doc="Reference to objArr"/>
    <reference type="objBool" maxOccurs="1" doc="Reference to objBool"/>
    <reference type="objNum" maxOccurs="1" doc="Reference to objNum"/>
    <reference type="objObj" maxOccurs="1" doc="Reference to objObj"/>
    <reference type="objStr" maxOccurs="1" doc="Reference to objStr"/>
  </array>
  <array name="arrayStr" doc="Array of string references">
    <any types="byte primitiveBoolean" maxOccurs="1" nullable="false" doc="Any type with primitive byte and boolean"/>
    <reference type="defaultString" maxOccurs="1" doc="Reference to defaultString"/>
    <reference type="charArray" maxOccurs="1" nullable="false" doc="Not-nullable reference to charArray"/>
    <reference type="uuid" maxOccurs="1" doc="Reference to uuid"/>
    <reference type="uuid" maxOccurs="1" nullable="false" doc="Not-nullable to uuid"/>
    <reference type="url" maxOccurs="1" doc="Reference to url"/>
    <reference type="url" maxOccurs="1" nullable="false" doc="Not-nullable to url"/>
    <reference type="StringBigDecimal" maxOccurs="1" doc="Reference to StringBigDecimal"/>
    <reference type="StringBigDecimal" maxOccurs="1" nullable="false" doc="Not-nullable to StringBigDecimal"/>
    <reference type="nonEmptyString" maxOccurs="1" doc="Reference to nonEmptyString"/>
    <reference type="nonEmptyString" minOccurs="2" maxOccurs="3" nullable="false" doc="Not-nullable to nonEmptyString"/>
  </array>
  <boolean name="defaultBoolean" doc="Default boolean"/>
  <boolean name="primitiveBoolean" doc="Primitive boolean">
    <binding lang="java" type="boolean" encode="java.lang.String.valueOf"/>
  </boolean>
  <boolean name="StringBoolean">
    <binding lang="java" type="java.lang.String" decode="java.lang.String.valueOf"/>
  </boolean>
  <number name="defaultDecimal" doc="Default decimal type"/>
  <number name="defaultInteger" scale="0" doc="Default integer type"/>
  <number name="byte" scale="0" range="[-64,63]" doc="Primitive byte type">
    <binding lang="java" type="byte"/>
  </number>
  <number name="Short" scale="0" range="[-16384,16383]" doc="Short number type">
    <binding lang="java" type="java.lang.Short"/>
  </number>
  <number name="StringDecimal">
    <binding lang="java" type="java.lang.CharSequence"/>
  </number>
  <number name="numRange" range="[1e10,]" doc="Template for number type with range"/>
  <number name="cachedInteger" scale="0" range="[1,]" doc="Template for integer number type with range">
    <binding lang="java" type="java.math.BigInteger" decode="org.libj.math.BigIntegers.intern"/>
  </number>
  <number name="plainDecimal" scale="2" doc="Template cached BigDecimal">
    <binding lang="java" type="java.math.BigDecimal" encode="this.toPlainString"/>
  </number>
  <number name="cachedPlainDecimal" scale="3" range="[-2.222e-12,]" doc="First template for real number type with range">
    <binding lang="java" type="java.math.BigDecimal" decode="org.libj.math.BigDecimals.intern" encode="this.toPlainString"/>
  </number>
  <number name="defaultDecimalRange2" scale="3" range="[-2.222e-12,]" doc="Second template for real number type with range"/>

  <string name="defaultString" doc="Default string type"/>
  <string name="charArray" doc="char[] type">
    <binding lang="java" type="char[]" decode="org.libj.lang.Characters.valueOf" encode="java.lang.String.&lt;init&gt;"/>
  </string>
  <string name="uuid" pattern="[0-9]{8}-[a-f]{4}-[0-9]{4}-[a-f]{4}-[0-9]{12}" doc="UUID pattern with UUID type">
    <binding lang="java" type="java.util.UUID" decode="org.libj.lang.Strings.toUuidOrNull"/>
  </string>
  <string name="url" pattern="((https?|ftp)://jsonx.org/[\w\d:#@%/;$()~_?'\+-=\\\.&amp;]+)" doc="URL pattern with URL type">
    <binding lang="java" type="java.net.URL" decode="java.net.URL.&lt;init&gt;"/>
  </string>
  <string name="StringBigDecimal" pattern="\d+(\.\d+)?([eE][+-]?\d{1,5})?" doc="An integer with BigDecimal type represented as a string">
    <binding lang="java" type="java.math.BigDecimal" decode="java.math.BigDecimal.&lt;init&gt;"/>
  </string>
  <string name="nonEmptyString" pattern="(\S)|(\S.*\S)" doc="Non-empty string"/>
  <object name="objTest" doc="Object with array references">
    <property names="anyNumStr" xsi:type="any" types="defaultDecimal charArray" use="optional" doc="Optional property named anyNumStr of type 'defaultDecimal' or 'charArray'"/>
  </object>
  <object name="objArr" doc="Object with array references">
    <property names=".*" xsi:type="any" nullable="false" doc="Property accepting any name and any type">
      <binding lang="java" field="any1"/>
    </property>
    <property name="arrayBool" xsi:type="reference" type="arrayBool" doc="Property with bool array">
      <binding lang="java" field="ab"/>
    </property>
    <property name="arrayBoolOptional" xsi:type="reference" type="arrayBool" use="optional" doc="Optional property with bool array">
      <binding lang="java" field="abO"/>
    </property>
    <property name="arrayBoolOptionalNotNullable" xsi:type="reference" type="arrayBool" use="optional" nullable="false" doc="Optional, not-nullable property with bool array">
      <binding lang="java" field="abONN"/>
    </property>
    <property name="arrayNum" xsi:type="reference" type="arrayNum" doc="Property with num array">
      <binding lang="java" field="an"/>
    </property>
    <property name="arrayNumOptional" xsi:type="reference" type="arrayNum" use="optional" doc="Optional property with num array">
      <binding lang="java" field="anO"/>
    </property>
    <property name="arrayNumOptionalNotNullable" xsi:type="reference" type="arrayNum" use="optional" nullable="false" doc="Optional, not-nullable property with num array">
      <binding lang="java" field="anONN"/>
    </property>
    <property name="arrayStr" xsi:type="reference" type="arrayStr" doc="Property with str array">
      <binding lang="java" field="as"/>
    </property>
    <property name="arrayStrOptional" xsi:type="reference" type="arrayStr" use="optional" doc="Optional property with str array">
      <binding lang="java" field="asO"/>
    </property>
    <property name="arrayStrOptionalNotNullable" xsi:type="reference" type="arrayStr" use="optional" nullable="false" doc="Optional, not-nullable property with str array">
      <binding lang="java" field="asONN"/>
    </property>
    <property names="anyNumStr" xsi:type="any" types="defaultDecimal charArray" use="optional" doc="Optional property named anyNumStr of type 'defaultDecimal' or 'charArray'">
      <binding lang="java" field="any2"/>
    </property>
  </object>
  <object name="objBool" doc="Object with boolean properties">
    <property name="bo+l" xsi:type="reference" type="primitiveBoolean" nullable="false" doc="Not-nullable property with name matching a regex of type primitiveBoolean">
      <binding lang="java" field="bool1"/>
    </property>
    <property names=".*" xsi:type="any" types="primitiveBoolean defaultDecimal" nullable="false" doc="Not-nullable property of any name and of type 'primitiveBoolean' or 'defaultDecimal'">
      <binding lang="java" field="any"/>
    </property>
    <property name="bo+lOptional" xsi:type="reference" type="StringBoolean" use="optional" doc="Optional property with name matching a regex of type StringBoolean">
      <binding lang="java" field="bool2"/>
    </property>
    <property name="boolOptionalNotNullable" xsi:type="reference" type="defaultBoolean" use="optional" nullable="false" doc="Not-nullable, optional property with name matching a regex of type defaultBoolean">
      <binding lang="java" field="bool3"/>
    </property>
  </object>
  <object name="objNum" doc="Object with number properties">
    <property name="num.+" xsi:type="reference" type="defaultDecimal" doc="Property with name matching a regex of type defaultDecimal">
      <binding lang="java" field="regexNum"/>
    </property>
    <property name="numRequired" xsi:type="reference" type="defaultDecimal" doc="Required property for defaultDecimal type"/>
    <property name="numOptional" xsi:type="reference" type="defaultDecimal" use="optional" doc="Optional property for defaultDecimal type"/>
    <property name="numRequiredNotNullable" xsi:type="reference" type="defaultDecimal" nullable="false" doc="Required and not-nullable property for defaultDecimal type"/>
    <property name="numOptionalNotNullable" xsi:type="reference" type="defaultDecimal" use="optional" nullable="false" doc="Optional and not-nullable property for defaultDecimal type"/>
    <property names="any" xsi:type="any" types="defaultDecimal charArray" nullable="false" doc="Property named 'any' of type 'defaultDecimal or 'charArray'"/>
    <property name="numIntRequired" xsi:type="reference" type="Short" doc="Required property referencing type byte"/>
    <property name="numIntOptional" xsi:type="reference" type="StringDecimal" use="optional" doc="Optional property referencing type StringDecimal"/>
    <property name="numIntRequiredNotNullable" xsi:type="reference" type="byte" nullable="false" doc="Required, not-nullable property referencing type byte"/>
    <property name="numIntOptionalNotNullable" xsi:type="reference" type="defaultInteger" use="optional" nullable="false" doc="Optional, not-nullable property referencing type defaultInteger"/>
    <property name="numRangeRequired" xsi:type="reference" type="numRange" doc="Required property referencing type numRange"/>
    <property name="numRangeOptional" xsi:type="reference" type="numRange" use="optional" doc="Optional property referencing type numRange"/>
    <property name="numRangeRequiredNotNullable" xsi:type="reference" type="numRange" nullable="false" doc="Required, not-nullable property referencing type numRange"/>
    <property name="numRangeOptionalNotNullable" xsi:type="reference" type="numRange" use="optional" nullable="false" doc="Optional, not-nullable property referencing type numRange"/>
    <property name="cachedIntegerRequired" xsi:type="reference" type="cachedInteger" doc="Required property referencing type cachedInteger"/>
    <property name="cachedIntegerOptional" xsi:type="reference" type="cachedInteger" use="optional" doc="Optional property referencing type cachedInteger"/>
    <property name="cachedIntegerRequiredNotNullable" xsi:type="reference" type="cachedInteger" nullable="false" doc="Required, not-nullable property referencing type cachedInteger"/>
    <property name="cachedIntegerOptionalNotNullable" xsi:type="reference" type="cachedInteger" use="optional" nullable="false" doc="Optional, not-nullable property referencing type cachedInteger"/>
    <property name="plainDecimalRequired" xsi:type="reference" type="plainDecimal" doc="Required property referencing type plainDecimal"/>
    <property name="plainDecimalOptional" xsi:type="reference" type="plainDecimal" use="optional" doc="Optional property referencing type plainDecimal"/>
    <property name="plainDecimalRequiredNotNullable" xsi:type="reference" type="plainDecimal" nullable="false" doc="Required, not-nullable property referencing type plainDecimal"/>
    <property name="plainDecimalOptionalNotNullable" xsi:type="reference" type="plainDecimal" use="optional" nullable="false" doc="Optional, not-nullable property referencing type plainDecimal"/>
    <property name="plainDecimalRangeRequired" xsi:type="reference" type="cachedPlainDecimal" doc="Required property referencing type cachedPlainDecimal"/>
    <property name="plainDecimalRangeOptional" xsi:type="reference" type="defaultDecimalRange2" use="optional" doc="Optional property referencing type defaultDecimalRange2"/>
    <property name="plainDecimalRangeRequiredNotNullable" xsi:type="reference" type="defaultDecimalRange2" nullable="false" doc="Required, not-nullable property referencing type defaultDecimalRange2"/>
    <property name="plainDecimalRangeOptionalNotNullable" xsi:type="reference" type="cachedPlainDecimal" use="optional" nullable="false" doc="Optional, not-nullable property referencing type cachedPlainDecimal"/>
  </object>
  <object name="objObj" doc="Object of objects">
    <property name="objOptional" xsi:type="reference" type="objBool" use="optional" doc="Optional reference to objBool">
      <binding lang="java" field="obj1"/>
    </property>
    <property name="objOptionalNotNullable" xsi:type="reference" type="objNum" use="optional" nullable="false" doc="Optional, not-nullable reference to objNum">
      <binding lang="java" field="obj2"/>
    </property>
    <property name="objExtends1" xsi:type="object" extends="objObj" use="optional" doc="Nested definition of optional object extending objObj">
      <property name="objExtends2" xsi:type="object" extends="objObj" use="optional" doc="Further nested definition of optional object extending objObj">
        <property name="objExtends3" xsi:type="object" extends="objObj" use="optional" doc="Further more nested definition of optional object extending objObj">
          <property name="objExtends4" xsi:type="object" extends="objObj" use="optional" doc="And yet further more nested definition of optional object extending objObj">
            <property name="defaultDecimal" xsi:type="reference" type="defaultDecimal" use="optional" doc="Optional property named 'defaultDecimal' of type 'defaultDecimal'">
              <binding lang="java" field="objX"/>
            </property>
            <binding lang="java" field="objX"/>
          </property>
        </property>
        <binding lang="java" field="objX"/>
      </property>
      <binding lang="java" field="obj3"/>
    </property>
    <property name="objExtendsOptional" xsi:type="object" extends="objBool" use="optional" doc="Optional property of nested object definition extending objBool">
      <property name="defaultString" xsi:type="reference" type="defaultString" doc="Optional property named 'defaultString' of type 'defaultString'"/>
      <property name="charArray" xsi:type="reference" type="charArray" doc="Optional property named 'charArray' of type 'charArray'"/>
      <binding lang="java" field="obj4"/>
    </property>
    <property name="objExtendsOptionalNotNullable" xsi:type="object" extends="objBool" use="optional" nullable="false">
      <property name="arrayBool" xsi:type="reference" type="arrayBool" doc="Optional property named 'arrayBool' of type 'arrayBool'"/>
      <binding lang="java" field="obj5"/>
    </property>
  </object>
  <object name="objStr" doc="Object definition with properties of string types">
    <property name="defaultString" xsi:type="reference" type="defaultString" doc="Property referencing 'defaultString' type"/>
    <property name="defaultStringOptional" xsi:type="reference" type="defaultString" use="optional" doc="Optional property referencing 'defaultString' type"/>
    <property name="defaultStringOptionalNotNullable" xsi:type="reference" type="defaultString" use="optional" nullable="false" doc="Optional, not-nullable property referencing 'defaultString' type"/>
    <property name="charArray" xsi:type="reference" type="charArray" doc="Property referencing 'charArray' type"/>
    <property name="charArrayOptional" xsi:type="reference" type="charArray" use="optional" doc="Optional property referencing 'charArray' type"/>
    <property name="charArrayOptionalNotNullable" xsi:type="reference" type="charArray" use="optional" nullable="false" doc="Optional, not-nullable property referencing 'charArray' type"/>
    <property name="uuid" xsi:type="reference" type="uuid" doc="Property referencing 'uuid' type"/>
    <property name="uuidOptional" xsi:type="reference" type="uuid" use="optional" doc="Optional property referencing 'uuid' type"/>
    <property name="uuidOptionalNotNullable" xsi:type="reference" type="uuid" use="optional" nullable="false" doc="Optional, not-nullable property referencing 'uuid' type"/>
    <property name="url" xsi:type="reference" type="url" doc="Property referencing 'url' type"/>
    <property name="urlOptional" xsi:type="reference" type="url" use="optional" doc="Optional property referencing 'url' type"/>
    <property name="urlOptionalNotNullable" xsi:type="reference" type="url" use="optional" nullable="false" doc="Optional, not-nullable property referencing 'url' type"/>
    <property name="StringBigDecimal" xsi:type="reference" type="StringBigDecimal" doc="Property referencing 'StringBigDecimal' type"/>
    <property name="StringBigDecimalOptional" xsi:type="reference" type="StringBigDecimal" use="optional" doc="Optional property referencing 'StringBigDecimal' type"/>
    <property name="StringBigDecimalOptionalNotNullable" xsi:type="reference" type="StringBigDecimal" use="optional" nullable="false" doc="Optional, not-nullable property referencing 'StringBigDecimal' type"/>
    <property name="nonEmptyString" xsi:type="reference" type="nonEmptyString" doc="Property referencing 'nonEmptyString' type"/>
    <property name="nonEmptyStringOptional" xsi:type="reference" type="nonEmptyString" use="optional" doc="Optional property referencing 'nonEmptyString' type"/>
    <property name="nonEmptyStringOptionalNotNullable" xsi:type="reference" type="nonEmptyString" use="optional" nullable="false" doc="Optional, not-nullable property referencing 'nonEmptyString' type"/>
  </object>
</schema>
```

#### <b>6.4</b> `datatypes.jsd`

```json
{
  "doc": "Schema intended to express full variability of type declarations",
  "jx:ns": "http://www.jsonx.org/schema-0.4.jsd",
  "jx:schemaLocation": "http://www.jsonx.org/schema-0.4.jsd http://www.jsonx.org/schema-0.4.jsd",
  "arrayArr": {
    "jx:type": "array",
    "doc": "Array of arrays",
    "elements": [{
      "jx:type": "reference",
      "type": "arrayBool",
      "maxOccurs": "1",
      "doc": "Reference to array of booleans"
    }, {
      "jx:type": "reference",
      "type": "arrayNum",
      "maxOccurs": "1",
      "doc": "Reference to array of numbers"
    }, {
      "jx:type": "reference",
      "type": "arrayObj",
      "maxOccurs": "1",
      "doc": "Reference to array of objects"
    }, {
      "jx:type": "reference",
      "type": "arrayObj",
      "maxOccurs": "1",
      "doc": "Another reference to array of objects"
    }, {
      "jx:type": "reference",
      "type": "arrayStr",
      "maxOccurs": "1",
      "doc": "Reference to array of strings"
    }, {
      "jx:type": "reference",
      "type": "arrayStr",
      "maxOccurs": "1",
      "doc": "Another reference to array of strings"
    }, {
      "jx:type": "any",
      "types": "defaultDecimal StringDecimal defaultBoolean StringBoolean",
      "minOccurs": "0",
      "maxOccurs": "1",
      "nullable": false,
      "doc": "Any of defaultDecimal, StringDecimal, defaultBoolean, or StringBoolean type"
    }]
  },
  "arrayBool": {
    "jx:type": "array",
    "doc": "Array of booleans",
    "elements": [{
      "jx:type": "any",
      "maxOccurs": "1",
      "nullable": false,
      "doc": "Any type"
    }, {
      "jx:type": "reference",
      "type": "primitiveBoolean",
      "maxOccurs": "1",
      "nullable": false,
      "doc": "Not-nullable reference to primitiveBoolean"
    }, {
      "jx:type": "reference",
      "type": "defaultBoolean",
      "maxOccurs": "1",
      "doc": "Reference to defaultBoolean"
    }]
  },
  "arrayNum": {
    "jx:type": "array",
    "doc": "Array of numbers",
    "elements": [{
      "jx:type": "any",
      "maxOccurs": "1",
      "nullable": false,
      "doc": "Any type"
    }, {
      "jx:type": "reference",
      "type": "defaultDecimal",
      "maxOccurs": "1",
      "doc": "Reference to defaultDecimal"
    }, {
      "jx:type": "reference",
      "type": "byte",
      "maxOccurs": "1",
      "nullable": false,
      "doc": "Reference to byte"
    }, {
      "jx:type": "reference",
      "type": "StringDecimal",
      "maxOccurs": "1",
      "doc": "Reference to StringDecimal"
    }, {
      "jx:type": "reference",
      "type": "numRange",
      "maxOccurs": "1",
      "nullable": false,
      "doc": "Reference to numRange"
    }, {
      "jx:type": "reference",
      "type": "cachedInteger",
      "maxOccurs": "1",
      "doc": "Reference to num"
    }, {
      "jx:type": "reference",
      "type": "plainDecimal",
      "maxOccurs": "1",
      "nullable": false,
      "doc": "Reference to plainDecimal"
    }, {
      "jx:type": "reference",
      "type": "cachedPlainDecimal",
      "maxOccurs": "1",
      "doc": "Reference to plainDecimalRange"
    }, {
      "jx:type": "reference",
      "type": "byte",
      "maxOccurs": "1",
      "nullable": false,
      "doc": "Reference to byte"
    }, {
      "jx:type": "reference",
      "type": "numRange",
      "maxOccurs": "1",
      "nullable": false,
      "doc": "Reference to numRange"
    }, {
      "jx:type": "reference",
      "type": "cachedInteger",
      "maxOccurs": "1",
      "doc": "Reference to cachedInteger"
    }, {
      "jx:type": "reference",
      "type": "defaultDecimalRange2",
      "minOccurs": "0",
      "maxOccurs": "1",
      "doc": "Reference to plainDecimalRange"
    }]
  },
  "arrayObj": {
    "jx:type": "array",
    "doc": "Array of object references",
    "elements": [{
      "jx:type": "reference",
      "type": "objArr",
      "maxOccurs": "1",
      "doc": "Reference to objArr"
    }, {
      "jx:type": "reference",
      "type": "objBool",
      "maxOccurs": "1",
      "doc": "Reference to objBool"
    }, {
      "jx:type": "reference",
      "type": "objNum",
      "maxOccurs": "1",
      "doc": "Reference to objNum"
    }, {
      "jx:type": "reference",
      "type": "objObj",
      "maxOccurs": "1",
      "doc": "Reference to objObj"
    }, {
      "jx:type": "reference",
      "type": "objStr",
      "maxOccurs": "1",
      "doc": "Reference to objStr"
    }]
  },
  "arrayStr": {
    "jx:type": "array",
    "doc": "Array of string references",
    "elements": [{
      "jx:type": "any",
      "types": "byte primitiveBoolean",
      "maxOccurs": "1",
      "nullable": false,
      "doc": "Any type with primitive byte and boolean"
    }, {
      "jx:type": "reference",
      "type": "defaultString",
      "maxOccurs": "1",
      "doc": "Reference to defaultString"
    }, {
      "jx:type": "reference",
      "type": "charArray",
      "maxOccurs": "1",
      "nullable": false,
      "doc": "Not-nullable reference to charArray"
    }, {
      "jx:type": "reference",
      "type": "uuid",
      "maxOccurs": "1",
      "doc": "Reference to uuid"
    }, {
      "jx:type": "reference",
      "type": "uuid",
      "maxOccurs": "1",
      "nullable": false,
      "doc": "Not-nullable to uuid"
    }, {
      "jx:type": "reference",
      "type": "url",
      "maxOccurs": "1",
      "doc": "Reference to url"
    }, {
      "jx:type": "reference",
      "type": "url",
      "maxOccurs": "1",
      "nullable": false,
      "doc": "Not-nullable to url"
    }, {
      "jx:type": "reference",
      "type": "StringBigDecimal",
      "maxOccurs": "1",
      "doc": "Reference to StringBigDecimal"
    }, {
      "jx:type": "reference",
      "type": "StringBigDecimal",
      "maxOccurs": "1",
      "nullable": false,
      "doc": "Not-nullable to StringBigDecimal"
    }, {
      "jx:type": "reference",
      "type": "nonEmptyString",
      "maxOccurs": "1",
      "doc": "Reference to nonEmptyString"
    }, {
      "jx:type": "reference",
      "type": "nonEmptyString",
      "minOccurs": "2",
      "maxOccurs": "3",
      "nullable": false,
      "doc": "Not-nullable to nonEmptyString"
    }]
  },
  "defaultBoolean": {
    "jx:type": "boolean",
    "doc": "Default boolean"
  },
  "primitiveBoolean": {
    "jx:type": "boolean",
    "doc": "Primitive boolean",
    "bindings": [{
      "lang": "java",
      "type": "boolean",
      "encode": "java.lang.String.valueOf"
    }]
  },
  "StringBoolean": {
    "jx:type": "boolean",
    "bindings": [{
      "lang": "java",
      "type": "java.lang.String",
      "decode": "java.lang.String.valueOf"
    }]
  },
  "defaultDecimal": {
    "jx:type": "number",
    "doc": "Default decimal type"
  },
  "defaultInteger": {
    "jx:type": "number",
    "scale": 0,
    "doc": "Default integer type"
  },
  "byte": {
    "jx:type": "number",
    "scale": 0,
    "range": "[-64,63]",
    "doc": "Primitive byte type",
    "bindings": [{
      "lang": "java",
      "type": "byte"
    }]
  },
  "Short": {
    "jx:type": "number",
    "scale": 0,
    "range": "[-16384,16383]",
    "doc": "Short number type",
    "bindings": [{
      "lang": "java",
      "type": "java.lang.Short"
    }]
  },
  "StringDecimal": {
    "jx:type": "number",
    "bindings": [{
      "lang": "java",
      "type": "java.lang.CharSequence"
    }]
  },
  "numRange": {
    "jx:type": "number",
    "range": "[1E+10,]",
    "doc": "Template for number type with range"
  },
  "cachedInteger": {
    "jx:type": "number",
    "scale": 0,
    "range": "[1,]",
    "doc": "Template for integer number type with range",
    "bindings": [{
      "lang": "java",
      "type": "java.math.BigInteger",
      "decode": "org.libj.math.BigIntegers.intern"
    }]
  },
  "plainDecimal": {
    "jx:type": "number",
    "scale": 2,
    "doc": "Template cached BigDecimal",
    "bindings": [{
      "lang": "java",
      "type": "java.math.BigDecimal",
      "encode": "this.toPlainString"
    }]
  },
  "cachedPlainDecimal": {
    "jx:type": "number",
    "scale": 3,
    "range": "[-2.222E-12,]",
    "doc": "First template for real number type with range",
    "bindings": [{
      "lang": "java",
      "type": "java.math.BigInteger",
      "decode": "org.libj.math.BigDecimals.intern",
      "encode": "this.toPlainString"
    }]
  },
  "defaultDecimalRange2": {
    "jx:type": "number",
    "scale": 3,
    "range": "[-2.222E-12,]",
    "doc": "Second template for real number type with range"
  },
  "defaultString": {
    "jx:type": "string",
    "doc": "Default string type"
  },
  "charArray": {
    "jx:type": "string",
    "doc": "char[] type",
    "bindings": [{
      "lang": "java",
      "type": "char[]",
      "decode": "org.libj.lang.Characters.valueOf",
      "encode": "java.lang.String.<init>"
    }]
  },
  "uuid": {
    "jx:type": "string",
    "pattern": "[0-9]{8}-[a-f]{4}-[0-9]{4}-[a-f]{4}-[0-9]{12}",
    "doc": "UUID pattern with UUID type",
    "bindings": [{
      "lang": "java",
      "type": "java.util.UUID",
      "decode": "org.libj.lang.Strings.toUuidOrNull"
    }]
  },
  "url": {
    "jx:type": "string",
    "pattern": "((https?|ftp)://jsonx.org/[\\w\\d:#@%/;$()~_?'\\+-=\\\\\\.&]+)",
    "doc": "URL pattern with URL type",
    "bindings": [{
      "lang": "java",
      "type": "java.net.URL",
      "decode": "java.net.URL.<init>"
    }]
  },
  "StringBigDecimal": {
    "jx:type": "string",
    "pattern": "\\d+(\\.\\d+)?([eE][+-]?\\d{1,5})?",
    "doc": "An integer with BigDecimal type represented as a string",
    "bindings": [{
      "lang": "java",
      "type": "java.math.BigDecimal",
      "decode": "java.math.BigDecimal.<init>"
    }]
  },
  "nonEmptyString": {
    "jx:type": "string",
    "pattern": "(\\S)|(\\S.*\\S)",
    "doc": "Non-empty string"
  },
  "objTest": {
    "jx:type": "object",
    "doc": "Object with array references",
    "properties": {
      "anyNumStr": {
        "jx:type": "any",
        "types": "defaultDecimal charArray",
        "use": "optional",
        "doc": "Optional property named anyNumStr of type 'defaultDecimal' or 'charArray'"
      }
    }
  },
  "objArr": {
    "jx:type": "object",
    "doc": "Object with array references",
    "properties": {
      ".*": {
        "jx:type": "any",
        "nullable": false,
        "doc": "Property accepting any name and any type",
        "bindings": [{
          "lang": "java",
          "field": "any1"
        }]
      },
      "arrayBool": {
        "jx:type": "reference",
        "type": "arrayBool",
        "doc": "Property with bool array",
        "bindings": [{
          "lang": "java",
          "field": "ab"
        }]
      },
      "arrayBoolOptional": {
        "jx:type": "reference",
        "type": "arrayBool",
        "use": "optional",
        "doc": "Optional property with bool array",
        "bindings": [{
          "lang": "java",
          "field": "abO"
        }]
      },
      "arrayBoolOptionalNotNullable": {
        "jx:type": "reference",
        "type": "arrayBool",
        "use": "optional",
        "nullable": false,
        "doc": "Optional, not-nullable property with bool array",
        "bindings": [{
          "lang": "java",
          "field": "abONN"
        }]
      },
      "arrayNum": {
        "jx:type": "reference",
        "type": "arrayNum",
        "doc": "Property with num array",
        "bindings": [{
          "lang": "java",
          "field": "an"
        }]
      },
      "arrayNumOptional": {
        "jx:type": "reference",
        "type": "arrayNum",
        "use": "optional",
        "doc": "Optional property with num array",
        "bindings": [{
          "lang": "java",
          "field": "anO"
        }]
      },
      "arrayNumOptionalNotNullable": {
        "jx:type": "reference",
        "type": "arrayNum",
        "use": "optional",
        "nullable": false,
        "doc": "Optional, not-nullable property with num array",
        "bindings": [{
          "lang": "java",
          "field": "anONN"
        }]
      },
      "arrayStr": {
        "jx:type": "reference",
        "type": "arrayStr",
        "doc": "Property with str array",
        "bindings": [{
          "lang": "java",
          "field": "as"
        }]
      },
      "arrayStrOptional": {
        "jx:type": "reference",
        "type": "arrayStr",
        "use": "optional",
        "doc": "Optional property with str array",
        "bindings": [{
          "lang": "java",
          "field": "asO"
        }]
      },
      "arrayStrOptionalNotNullable": {
        "jx:type": "reference",
        "type": "arrayStr",
        "use": "optional",
        "nullable": false,
        "doc": "Optional, not-nullable property with str array",
        "bindings": [{
          "lang": "java",
          "field": "asONN"
        }]
      },
      "anyNumStr": {
        "jx:type": "any",
        "types": "defaultDecimal charArray",
        "use": "optional",
        "doc": "Optional property named anyNumStr of type 'defaultDecimal' or 'charArray'",
        "bindings": [{
          "lang": "java",
          "field": "any2"
        }]
      }
    }
  },
  "objBool": {
    "jx:type": "object",
    "doc": "Object with boolean properties",
    "properties": {
      "bo+l": {
        "jx:type": "reference",
        "type": "primitiveBoolean",
        "nullable": false,
        "doc": "Not-nullable property with name matching a regex of type primitiveBoolean",
        "bindings": [{
          "lang": "java",
          "field": "bool1"
        }]
      },
      ".*": {
        "jx:type": "any",
        "types": "primitiveBoolean defaultDecimal",
        "nullable": false,
        "doc": "Not-nullable property of any name and of type 'primitiveBoolean' or 'defaultDecimal'",
        "bindings": [{
          "lang": "java",
          "field": "any"
        }]
      },
      "bo+lOptional": {
        "jx:type": "reference",
        "type": "StringBoolean",
        "use": "optional",
        "doc": "Optional property with name matching a regex of type StringBoolean",
        "bindings": [{
          "lang": "java",
          "field": "bool2"
        }]
      },
      "boolOptionalNotNullable": {
        "jx:type": "reference",
        "type": "defaultBoolean",
        "use": "optional",
        "nullable": false,
        "doc": "Not-nullable, optional property with name matching a regex of type defaultBoolean",
        "bindings": [{
          "lang": "java",
          "field": "bool3"
        }]
      }
    }
  },
  "objNum": {
    "jx:type": "object",
    "doc": "Object with number properties",
    "properties": {
      "num.+": {
        "jx:type": "reference",
        "type": "defaultDecimal",
        "doc": "Property with name matching a regex of type defaultDecimal",
        "bindings": [{
          "lang": "java",
          "field": "regexNum"
        }]
      },
      "numRequired": {
        "jx:type": "reference",
        "type": "defaultDecimal",
        "doc": "Required property for defaultDecimal type"
      },
      "numOptional": {
        "jx:type": "reference",
        "type": "defaultDecimal",
        "use": "optional",
        "doc": "Optional property for defaultDecimal type"
      },
      "numRequiredNotNullable": {
        "jx:type": "reference",
        "type": "defaultDecimal",
        "nullable": false,
        "doc": "Required and not-nullable property for defaultDecimal type"
      },
      "numOptionalNotNullable": {
        "jx:type": "reference",
        "type": "defaultDecimal",
        "use": "optional",
        "nullable": false,
        "doc": "Optional and not-nullable property for defaultDecimal type"
      },
      "any": {
        "jx:type": "any",
        "types": "defaultDecimal charArray",
        "nullable": false,
        "doc": "Property named 'any' of type 'defaultDecimal or 'charArray'"
      },
      "numIntRequired": {
        "jx:type": "reference",
        "type": "Short",
        "doc": "Required property referencing type byte"
      },
      "numIntOptional": {
        "jx:type": "reference",
        "type": "StringDecimal",
        "use": "optional",
        "doc": "Optional property referencing type StringDecimal"
      },
      "numIntRequiredNotNullable": {
        "jx:type": "reference",
        "type": "byte",
        "nullable": false,
        "doc": "Required, not-nullable property referencing type byte"
      },
      "numIntOptionalNotNullable": {
        "jx:type": "reference",
        "type": "defaultInteger",
        "use": "optional",
        "nullable": false,
        "doc": "Optional, not-nullable property referencing type defaultInteger"
      },
      "numRangeRequired": {
        "jx:type": "reference",
        "type": "numRange",
        "doc": "Required property referencing type numRange"
      },
      "numRangeOptional": {
        "jx:type": "reference",
        "type": "numRange",
        "use": "optional",
        "doc": "Optional property referencing type numRange"
      },
      "numRangeRequiredNotNullable": {
        "jx:type": "reference",
        "type": "numRange",
        "nullable": false,
        "doc": "Required, not-nullable property referencing type numRange"
      },
      "numRangeOptionalNotNullable": {
        "jx:type": "reference",
        "type": "numRange",
        "use": "optional",
        "nullable": false,
        "doc": "Optional, not-nullable property referencing type numRange"
      },
      "cachedIntegerRequired": {
        "jx:type": "reference",
        "type": "cachedInteger",
        "doc": "Required property referencing type cachedInteger"
      },
      "cachedIntegerOptional": {
        "jx:type": "reference",
        "type": "cachedInteger",
        "use": "optional",
        "doc": "Optional property referencing type cachedInteger"
      },
      "cachedIntegerRequiredNotNullable": {
        "jx:type": "reference",
        "type": "cachedInteger",
        "nullable": false,
        "doc": "Required, not-nullable property referencing type cachedInteger"
      },
      "cachedIntegerOptionalNotNullable": {
        "jx:type": "reference",
        "type": "cachedInteger",
        "use": "optional",
        "nullable": false,
        "doc": "Optional, not-nullable property referencing type cachedInteger"
      },
      "plainDecimalRequired": {
        "jx:type": "reference",
        "type": "plainDecimal",
        "doc": "Required property referencing type plainDecimal"
      },
      "plainDecimalOptional": {
        "jx:type": "reference",
        "type": "plainDecimal",
        "use": "optional",
        "doc": "Optional property referencing type plainDecimal"
      },
      "plainDecimalRequiredNotNullable": {
        "jx:type": "reference",
        "type": "plainDecimal",
        "nullable": false,
        "doc": "Required, not-nullable property referencing type plainDecimal"
      },
      "plainDecimalOptionalNotNullable": {
        "jx:type": "reference",
        "type": "plainDecimal",
        "use": "optional",
        "nullable": false,
        "doc": "Optional, not-nullable property referencing type plainDecimal"
      },
      "plainDecimalRangeRequired": {
        "jx:type": "reference",
        "type": "cachedPlainDecimal",
        "doc": "Required property referencing type cachedPlainDecimal"
      },
      "plainDecimalRangeOptional": {
        "jx:type": "reference",
        "type": "defaultDecimalRange2",
        "use": "optional",
        "doc": "Optional property referencing type defaultDecimalRange2"
      },
      "plainDecimalRangeRequiredNotNullable": {
        "jx:type": "reference",
        "type": "defaultDecimalRange2",
        "nullable": false,
        "doc": "Required, not-nullable property referencing type defaultDecimalRange2"
      },
      "plainDecimalRangeOptionalNotNullable": {
        "jx:type": "reference",
        "type": "cachedPlainDecimal",
        "use": "optional",
        "nullable": false,
        "doc": "Optional, not-nullable property referencing type cachedPlainDecimal"
      }
    }
  },
  "objObj": {
    "jx:type": "object",
    "doc": "Object of objects",
    "properties": {
      "objOptional": {
        "jx:type": "reference",
        "type": "objBool",
        "use": "optional",
        "doc": "Optional reference to objBool",
        "bindings": [{
          "lang": "java",
          "field": "obj1"
        }]
      },
      "objOptionalNotNullable": {
        "jx:type": "reference",
        "type": "objNum",
        "use": "optional",
        "nullable": false,
        "doc": "Optional, not-nullable reference to objNum",
        "bindings": [{
          "lang": "java",
          "field": "obj2"
        }]
      },
      "objExtends1": {
        "jx:type": "object",
        "extends": "objObj",
        "use": "optional",
        "doc": "Nested definition of optional object extending objObj",
        "bindings": [{
          "lang": "java",
          "field": "obj3"
        }],
        "properties": {
          "objExtends2": {
            "jx:type": "object",
            "extends": "objObj",
            "use": "optional",
            "doc": "Further nested definition of optional object extending objObj",
            "bindings": [{
              "lang": "java",
              "field": "objX"
            }],
            "properties": {
              "objExtends3": {
                "jx:type": "object",
                "extends": "objObj",
                "use": "optional",
                "doc": "Further more nested definition of optional object extending objObj",
                "properties": {
                  "objExtends4": {
                    "jx:type": "object",
                    "extends": "objObj",
                    "use": "optional",
                    "doc": "And yet further more nested definition of optional object extending objObj",
                    "bindings": [{
                      "lang": "java",
                      "field": "objX"
                    }],
                    "properties": {
                      "defaultDecimal": {
                        "jx:type": "reference",
                        "type": "defaultDecimal",
                        "use": "optional",
                        "doc": "Optional property named 'defaultDecimal' of type 'defaultDecimal'",
                        "bindings": [{
                          "lang": "java",
                          "field": "objX"
                        }]
                      }
                    }
                  }
                }
              }
            }
          }
        }
      },
      "objExtendsOptional": {
        "jx:type": "object",
        "extends": "objBool",
        "use": "optional",
        "doc": "Optional property of nested object definition extending objBool",
        "bindings": [{
          "lang": "java",
          "field": "obj4"
        }],
        "properties": {
          "defaultString": {
            "jx:type": "reference",
            "type": "defaultString",
            "doc": "Optional property named 'defaultString' of type 'defaultString'"
          },
          "charArray": {
            "jx:type": "reference",
            "type": "charArray",
            "doc": "Optional property named 'charArray' of type 'charArray'"
          }
        }
      },
      "objExtendsOptionalNotNullable": {
        "jx:type": "object",
        "extends": "objBool",
        "use": "optional",
        "nullable": false,
        "bindings": [{
          "lang": "java",
          "field": "obj5"
        }],
        "properties": {
          "arrayBool": {
            "jx:type": "reference",
            "type": "arrayBool",
            "doc": "Optional property named 'arrayBool' of type 'arrayBool'"
          }
        }
      }
    }
  },
  "objStr": {
    "jx:type": "object",
    "doc": "Object definition with properties of string types",
    "properties": {
      "defaultString": {
        "jx:type": "reference",
        "type": "defaultString",
        "doc": "Property referencing 'defaultString' type"
      },
      "defaultStringOptional": {
        "jx:type": "reference",
        "type": "defaultString",
        "use": "optional",
        "doc": "Optional property referencing 'defaultString' type"
      },
      "defaultStringOptionalNotNullable": {
        "jx:type": "reference",
        "type": "defaultString",
        "use": "optional",
        "nullable": false,
        "doc": "Optional, not-nullable property referencing 'defaultString' type"
      },
      "charArray": {
        "jx:type": "reference",
        "type": "charArray",
        "doc": "Property referencing 'charArray' type"
      },
      "charArrayOptional": {
        "jx:type": "reference",
        "type": "charArray",
        "use": "optional",
        "doc": "Optional property referencing 'charArray' type"
      },
      "charArrayOptionalNotNullable": {
        "jx:type": "reference",
        "type": "charArray",
        "use": "optional",
        "nullable": false,
        "doc": "Optional, not-nullable property referencing 'charArray' type"
      },
      "uuid": {
        "jx:type": "reference",
        "type": "uuid",
        "doc": "Property referencing 'uuid' type"
      },
      "uuidOptional": {
        "jx:type": "reference",
        "type": "uuid",
        "use": "optional",
        "doc": "Optional property referencing 'uuid' type"
      },
      "uuidOptionalNotNullable": {
        "jx:type": "reference",
        "type": "uuid",
        "use": "optional",
        "nullable": false,
        "doc": "Optional, not-nullable property referencing 'uuid' type"
      },
      "url": {
        "jx:type": "reference",
        "type": "url",
        "doc": "Property referencing 'url' type"
      },
      "urlOptional": {
        "jx:type": "reference",
        "type": "url",
        "use": "optional",
        "doc": "Optional property referencing 'url' type"
      },
      "urlOptionalNotNullable": {
        "jx:type": "reference",
        "type": "url",
        "use": "optional",
        "nullable": false,
        "doc": "Optional, not-nullable property referencing 'url' type"
      },
      "StringBigDecimal": {
        "jx:type": "reference",
        "type": "StringBigDecimal",
        "doc": "Property referencing 'StringBigDecimal' type"
      },
      "StringBigDecimalOptional": {
        "jx:type": "reference",
        "type": "StringBigDecimal",
        "use": "optional",
        "doc": "Optional property referencing 'StringBigDecimal' type"
      },
      "StringBigDecimalOptionalNotNullable": {
        "jx:type": "reference",
        "type": "StringBigDecimal",
        "use": "optional",
        "nullable": false,
        "doc": "Optional, not-nullable property referencing 'StringBigDecimal' type"
      },
      "nonEmptyString": {
        "jx:type": "reference",
        "type": "nonEmptyString",
        "doc": "Property referencing 'nonEmptyString' type"
      },
      "nonEmptyStringOptional": {
        "jx:type": "reference",
        "type": "nonEmptyString",
        "use": "optional",
        "doc": "Optional property referencing 'nonEmptyString' type"
      },
      "nonEmptyStringOptionalNotNullable": {
        "jx:type": "reference",
        "type": "nonEmptyString",
        "use": "optional",
        "nullable": false,
        "doc": "Optional, not-nullable property referencing 'nonEmptyString' type"
      }
    }
  }
}
```

#### <b>6.5</b> `bindings.jsdx`

```xml
<schema
  doc="Schema focusing on bindings"
  xmlns="http://www.jsonx.org/schema-0.4.xsd"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://www.jsonx.org/schema-0.4.xsd http://www.jsonx.org/schema.xsd">

  <boolean name="StringBoolean">
    <binding lang="java" type="java.lang.String"/>
  </boolean>

  <number name="short" scale="0" range="[-32768,32767]">
    <binding lang="java" type="short"/>
  </number>
  <number name="StringDecimal">
    <binding lang="java" type="java.lang.StringBuilder" decode="java.lang.StringBuilder.&lt;init&gt;"/>
  </number>

  <string name="uuid">
    <binding lang="java" type="java.util.UUID" decode="org.libj.lang.Strings.toUuidOrNull"/>
  </string>

  <array name="arrayReferences">
    <reference type="StringBoolean"/>
    <reference type="short" nullable="false"/>
    <reference type="StringDecimal"/>
    <reference type="uuid"/>
  </array>

  <array name="arrayDirect">
    <boolean>
      <binding lang="java" type="java.lang.String"/>
    </boolean>
    <number scale="0" nullable="false">
      <binding lang="java" type="short"/>
    </number>
    <number>
      <binding lang="java" type="java.lang.StringBuilder" decode="java.lang.StringBuilder.&lt;init&gt;"/>
    </number>
    <string>
      <binding lang="java" type="java.util.UUID" decode="org.libj.lang.Strings.toUuidOrNull"/>
    </string>
  </array>

  <object name="objRefs">
    <property name="arrayDirect" xsi:type="reference" type="arrayDirect">
      <binding lang="java" field="objRefArrayDirect"/>
    </property>
    <property name="arrayReferences" xsi:type="reference" type="arrayReferences">
      <binding lang="java" field="objRefArrayReferences"/>
    </property>
    <property name="StringBoolean" xsi:type="reference" type="StringBoolean">
      <binding lang="java" field="objRefStringBoolean"/>
    </property>
    <property name="short" xsi:type="reference" type="short" nullable="false">
      <binding lang="java" field="objRefShortPrimitive"/>
    </property>
    <property name="StringDecimal" xsi:type="reference" type="StringDecimal">
      <binding lang="java" field="objRefStringDecimal"/>
    </property>
    <property name="uuid" xsi:type="reference" type="uuid">
      <binding lang="java" field="objRefUuid"/>
    </property>
    <property name="object" xsi:type="reference" type="objRefs">
      <binding lang="java" field="objRefObject"/>
    </property>
  </object>

  <object name="objDir">
    <property name="arrayDirect" xsi:type="array">
      <boolean>
        <binding lang="java" type="java.lang.String"/>
      </boolean>
      <number scale="0" nullable="false">
        <binding lang="java" type="short"/>
      </number>
      <number>
        <binding lang="java" type="java.lang.StringBuilder" decode="java.lang.StringBuilder.&lt;init&gt;"/>
      </number>
      <string>
        <binding lang="java" type="java.util.UUID" decode="org.libj.lang.Strings.toUuidOrNull"/>
      </string>
      <binding lang="java" field="objDirArrayDirect"/>
    </property>
    <property name="arrayReferences" xsi:type="array">
      <reference type="arrayDirect"/>
      <reference type="arrayReferences"/>
      <reference type="StringBoolean"/>
      <reference type="short" nullable="false"/>
      <reference type="StringDecimal"/>
      <reference type="uuid"/>
      <binding lang="java" field="objDirArrayReferences"/>
    </property>
    <property name="StringBoolean" xsi:type="boolean">
      <binding lang="java" type="java.lang.String" field="objDirStringBoolean"/>
    </property>
    <property name="short" xsi:type="number" scale="0" nullable="false">
      <binding lang="java" type="short" field="objDirShortPrimitive"/>
    </property>
    <property name="StringDecimal" xsi:type="number">
      <binding lang="java" type="java.lang.StringBuilder" decode="java.lang.StringBuilder.&lt;init&gt;" field="objDirStringDecimal"/>
    </property>
    <property name="uuid" xsi:type="string">
      <binding lang="java" type="java.util.UUID" decode="org.libj.lang.Strings.toUuidOrNull" field="objDirUuid"/>
    </property>
    <property name="object" xsi:type="object" extends="objDir">
      <binding lang="java" field="objDirObject"/>
    </property>
  </object>

</schema>
```

#### <b>6.6</b> `bindings.jsd`

```json
{
  "doc": "Schema focusing on bindings",
  "jx:ns": "http://www.jsonx.org/schema-0.4.jsd",
  "jx:schemaLocation": "http://www.jsonx.org/schema-0.4.jsd http://www.jsonx.org/schema-0.4.jsd",
  "StringBoolean": {
    "jx:type": "boolean",
    "bindings": [{
      "lang": "java",
      "type": "java.lang.String"
    }]
  },
  "short": {
    "jx:type": "number",
    "scale": 0,
    "range": "[-32768,32767]",
    "bindings": [{
      "lang": "java",
      "type": "short"
    }]
  },
  "StringDecimal": {
    "jx:type": "number",
    "bindings": [{
      "lang": "java",
      "type": "java.lang.StringBuilder",
      "decode": "java.lang.StringBuilder.<init>"
    }]
  },
  "uuid": {
    "jx:type": "string",
    "bindings": [{
      "lang": "java",
      "type": "java.util.UUID",
      "decode": "org.libj.lang.Strings.toUuidOrNull"
    }]
  },
  "arrayReferences": {
    "jx:type": "array",
    "elements": [{
      "jx:type": "reference",
      "type": "StringBoolean"
    }, {
      "jx:type": "reference",
      "type": "short",
      "nullable": false
    }, {
      "jx:type": "reference",
      "type": "StringDecimal"
    }, {
      "jx:type": "reference",
      "type": "uuid"
    }]
  },
  "arrayDirect": {
    "jx:type": "array",
    "elements": [{
      "jx:type": "boolean",
      "bindings": [{
        "lang": "java",
        "type": "java.lang.String"
      }]
    }, {
      "jx:type": "number",
      "scale": 0,
      "nullable": false,
      "bindings": [{
        "lang": "java",
        "type": "short"
      }]
    }, {
      "jx:type": "number",
      "bindings": [{
        "lang": "java",
        "type": "java.lang.StringBuilder",
        "decode": "java.lang.StringBuilder.<init>"
      }]
    }, {
      "jx:type": "string",
      "bindings": [{
        "lang": "java",
        "type": "java.util.UUID",
        "decode": "org.libj.lang.Strings.toUuidOrNull"
      }]
    }]
  },
  "objRefs": {
    "jx:type": "object",
    "properties": {
      "arrayDirect": {
        "jx:type": "reference",
        "type": "arrayDirect",
        "bindings": [{
          "lang": "java",
          "field": "objRefArrayDirect"
        }]
      },
      "arrayReferences": {
        "jx:type": "reference",
        "type": "arrayReferences",
        "bindings": [{
          "lang": "java",
          "field": "objRefArrayReferences"
        }]
      },
      "StringBoolean": {
        "jx:type": "reference",
        "type": "StringBoolean",
        "bindings": [{
          "lang": "java",
          "field": "objRefStringBoolean"
        }]
      },
      "short": {
        "jx:type": "reference",
        "type": "short",
        "nullable": false,
        "bindings": [{
          "lang": "java",
          "field": "objRefShortPrimitive"
        }]
      },
      "StringDecimal": {
        "jx:type": "reference",
        "type": "StringDecimal",
        "bindings": [{
          "lang": "java",
          "field": "objRefStringDecimal"
        }]
      },
      "uuid": {
        "jx:type": "reference",
        "type": "uuid",
        "bindings": [{
          "lang": "java",
          "field": "objRefUuid"
        }]
      },
      "object": {
        "jx:type": "reference",
        "type": "objRefs",
        "bindings": [{
          "lang": "java",
          "field": "objRefObject"
        }]
      }
    }
  },
  "objDir": {
    "jx:type": "object",
    "properties": {
      "arrayDirect": {
        "jx:type": "array",
        "bindings": [{
          "lang": "java",
          "field": "objDirArrayDirect"
        }],
        "elements": [{
          "jx:type": "boolean",
          "bindings": [{
            "lang": "java",
            "type": "java.lang.String"
          }]
        }, {
          "jx:type": "number",
          "scale": 0,
          "nullable": false,
          "bindings": [{
            "lang": "java",
            "type": "short"
          }]
        }, {
          "jx:type": "number",
          "bindings": [{
            "lang": "java",
            "type": "java.lang.StringBuilder",
            "decode": "java.lang.StringBuilder.<init>"
          }]
        }, {
          "jx:type": "string",
          "bindings": [{
            "lang": "java",
            "type": "java.util.UUID",
            "decode": "org.libj.lang.Strings.toUuidOrNull"
          }]
        }]
      },
      "arrayReferences": {
        "jx:type": "array",
        "bindings": [{
          "lang": "java",
          "field": "objDirArrayReferences"
        }],
        "elements": [{
          "jx:type": "reference",
          "type": "arrayDirect"
        }, {
          "jx:type": "reference",
          "type": "arrayReferences"
        }, {
          "jx:type": "reference",
          "type": "StringBoolean"
        }, {
          "jx:type": "reference",
          "type": "short",
          "nullable": false
        }, {
          "jx:type": "reference",
          "type": "StringDecimal"
        }, {
          "jx:type": "reference",
          "type": "uuid"
        }]
      },
      "StringBoolean": {
        "jx:type": "boolean",
        "bindings": [{
          "lang": "java",
          "type": "java.lang.String",
          "field": "objDirStringBoolean"
        }]
      },
      "short": {
        "jx:type": "number",
        "scale": 0,
        "nullable": false,
        "bindings": [{
          "lang": "java",
          "type": "short",
          "field": "objDirShortPrimitive"
        }]
      },
      "StringDecimal": {
        "jx:type": "number",
        "bindings": [{
          "lang": "java",
          "type": "java.lang.StringBuilder",
          "field": "objDirStringDecimal",
          "decode": "java.lang.StringBuilder.<init>"
        }]
      },
      "uuid": {
        "jx:type": "string",
        "bindings": [{
          "lang": "java",
          "type": "java.util.UUID",
          "field": "objDirUuid",
          "decode": "org.libj.lang.Strings.toUuidOrNull"
        }]
      },
      "object": {
        "jx:type": "object",
        "extends": "objDir",
        "bindings": [{
          "lang": "java",
          "field": "objDirObject"
        }]
      }
    }
  }
}
```

## <b>7</b> <ins>Contributing</ins>

Pull requests are welcome. For major changes, please [open an issue](../../../issues) first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## <b>8</b> <ins>Special Thanks</ins>

[![Java Profiler](https://www.ej-technologies.com/images/product_banners/jprofiler_small.png)](https://www.ej-technologies.com/products/jprofiler/overview.html)
<br><sub>_Special thanks to [EJ Technologies](https://www.ej-technologies.com/) for providing their award winning Java Profiler ([JProfiler](https://www.ej-technologies.com/products/jprofiler/overview.html)) for development of the JSONx Framework._</sub>

## <b>9</b> <ins>License</ins>

This project is licensed under the MIT License - see the [LICENSE.txt](LICENSE.txt) file for details.

[#schema]: #41-schema-document
[#constraint-types]: #42-constraint-types
[#boolean]: #421-boolean
[#number]: #422-number
[#number-scale]: #4221-numberscale
[#number-range]: #4222-numberrange
[#string]: #423-string
[#string-pattern]: #4231-stringpattern
[#object]: #424-object
[#object-properties]: #4241-objectproperties
[#property-names]: #4242-property-names
[#object-abstract]: #4243-objectabstract
[#object-extends]: #4244-objectextends
[#object-type-declarations]: #42441-type-declarations
[#object-object-properties]: #42442-object-properties
[#array]: #425-array
[#array-array-elements]: #4251-arrayelements
[#array-iterate]: #4252-arrayminiterate-and-arraymaxiterate
[#reference]: #426-reference
[#reference-type]: #4261-referencetype
[#reference-object-properties]: #42611-object-properties
[#reference-array-elements]: #42612-array-elements
[#any]: #427-any
[#any-types]: #4271-anytypes
[#any-object-properties]: #42711-object-properties
[#any-array-elements]: #42712-array-elements
[#type-declarations]: #43-type-declarations
[#object-properties]: #44-object-properties
[#array-elements]: #45-array-elements
[#bindings]: #46-language-specific-bindings
[#type-bindings]: #461-type-bindings
[#field-bindings]: #462-field-bindings
[#typefield-bindings]: #463-typefield-bindings

[ecma262]: http://www.ecma-international.org/publications/standards/Ecma-262.htm
[interval-notation]: https://en.wikipedia.org/wiki/Interval_(mathematics)#Classification_of_intervals
[oxygenxml]: https://www.oxygenxml.com/xml_editor/download_oxygenxml_editor.html
[rfc2119]: https://www.ietf.org/rfc/rfc2119.txt
[rfc4627]: https://www.ietf.org/rfc/rfc4627.txt
[rfc7159]: https://www.ietf.org/rfc/rfc7159.txt
[xmlschema]: http://www.w3.org/2001/XMLSchema