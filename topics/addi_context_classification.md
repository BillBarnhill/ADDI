Context classification
=======================

For meaningful reasoning an upper ontology is needed.  For many scenarios
the looser lattice approach of John F. Sowa works well.  For other scenarios
a more strict approach is needed, for these the Basic Formal Ontology (BFO)
of Barry Smith can work better.

As a result there is a mechanism to specify that a context uses a specific
ontology, with a meta link assertion using the predicate $uses.  If there is
no $uses assertion asserted then the context uses the ontology used by the parent
context. If there is no parent context and there is no $uses assertion then
the KR ontology is used.

Using the context of =bob as asserted by =alice as our example, the following
explicitly asserts that it uses Sowa's lattices approach:
=alice(=bob)$|$_/$uses/+ont+kr

If Barry Smith's BFO is preferred then the following would be used:
=alice(=bob)$|$_/$uses/+ont+bfo

$uses can also be used to assert use of other lower level domain ontologies.