.. _extra-headers:

==============
Extra Headers
==============

The extra headers are encoded in the JSON Data Interchange Standard as
defined by `ECMA-404 <https://www.ecma-international.org/publications-and-standards/standards/ecma-404/>`_.
All extra headers are optional as far as the format is concerned.

Extra headers must follow these rules:

- All extra headers are contained in an anonymous (unnamed) object
- All entries are key-value pairs where values can be any valid JSON type
- The key value of “FDSN” in the root object is reserved for values defined by the FDSN

----------------------------
Validation
----------------------------

Extra headers are specified and documented in `JSON Schema <http://json-schema.org/>`_.

----------------------------
FDSN Reserved Headers
----------------------------

The key named **"FDSN"** with value of an JSON object in the root
container of the extra headers is reserved for definition by the FDSN.
The documentation and schema of these headers are specified in JSON
Schema here:

https://iris-edu.github.io/miniSEED3/extra-headers/ExtraHeaders-FDSN.schema.json

(location subject to change)

When not present, the boolean values in the FDSN reserved headers
should be considered to be `false` unless otherwise documented.  Such
values do not need to be included when the value is `false`.



See :ref:`example-fdsn-extra-headers` for an example of FDSN extra headers.

----------------------------------------------------------
Guidelines for Extension
----------------------------------------------------------

Network operators, manufacturers, data centers, users and other
agencies may wish to define their own extra headers.  The following
guidelines should be considered, in particular for data that is
expected to reside in a public repository:

- All headers defined by a group or agency should be contained in a
  JSON object that is the value of a key in the root container with a
  clearly identifiable name, i.e. at the same level as **“FDSN”**.

- Creation of a JSON Schema document describing the field(s) is
  strongly recommended.  The schema should be submitted to the FDSN to
  be made publically available.

- Headers that would be generally useful should be submitted to the
  FDSN for consideration of being added to the reserved headers for
  general definition and use.

Multiple JSON Schema documents are easily combined for use in
validating extra headers that may contain headers defined in multiple
schema documents.
