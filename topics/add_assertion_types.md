Assertion Types Within a Context
===================================

There are three types of assertions in a context.

The first type are attribute assertions. These are assertions that
assert one or more literal values for a particular property of a subject.
These assertions describe the value of a property of what the subject represents. For
example, the example below asserts that that the name of Bob (the person addressed
by =bob) is Bobby. The object of an attribute assertion is always a literal.  A role (a\
n ADDI
segment beginning with a +) can be used as a predicate in attribute assertions
or link assertions, but not both.  The predicate in an assertion can
also be a dollar segment reserved predicate (e.g., $pr for probability).  Lastly,
an assertion can have a predicate using some external URN based scheme,
in which case the predicate is a cross-reference. Every attribute assertion has the
attribute assertion segment, $. , following the subject cross-reference.

Example:  =alice(=bob)$./+name/"Bobby"

The second type of assertion is a link assertion.  This assertion states a

relationship between the resource described by this context and another.
The predicate states the type of relationship.
The object in this type of assertion is a subject ARI (single segment). Every
attribute assertion can either have the link assertion segment, $_ , or not have
any assertion type segment.

Example (long form):  =alice(=bob)$_/+friend/=alice
Example (short form):  =alice(=bob)/+friend/=alice

The third type of asssertion is a meta assertion.  Link and attribute assertions
assert information about the resource represented by the context.  In contrast,
meta assertions assert information about the context itself.  Since this can include
attribute assertions and link assertions a meta assertion type segment, $| , is followe\
d
by a type segment for attribute assertion or link assertion (e.g., $|$. or $|$_).


Example (meta-attribute): The hash of the assertions by =alice about =bob is asserted b\
y
=alice(=bob)$|$./$hash/(data:;base64,Lfn/TeWc0k7Gq2x1N2sOyiXZlQjnGTkqtMtiVPKBPW6TP5kYqM\
wrLSiSTEi/j1a6zn4op5bMOi1VX9JkkTKOZQ==)

Example (meta-link): =bob is the same as =bobby (bi-directional logical equivalent betw\
een resources represented)
=alice(=bob)$|$_/$alias/=bobby
