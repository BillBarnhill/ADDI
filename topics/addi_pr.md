ADDI Assertions and Probability
================================

Every assertion in ADDI has a probability, a metric between zero and one inclusive that
describes the asserters confidence in the truth of the assertion. A probability of one
indicates the asserter is certain of the truth of the assertion.  This is the default
probability for any assertion where a probability is not explicitly asserted.

The dollar segment $pr is reserved for indicating probability.  It can be used as a
predicate within an assertion whose subject , or embedded in 

Asserting a Probability
-------------------------------
 
The easiest way to assert the probability of an assertion is to embed it in
the assertion.  This is done by appending a probability cross-reference. A probability
cross-reference has the ABNF form:

xref-start = "("
xref-end = ")"
reserved-gcs = "$"
subseg-delim = "*"
pr-word = reserved-gcs "pr"
pr-xref = xref-start pr-word subseg-delim pr-value xref-end
pr-value = pr-value-max / pr-value-min / pr-value-between
pr-value-max = "1"
pr-value-min = "0"
pr-value-between = "0." 1*digit
digit = %x30-41


An example where we assert a 50% confidence that Bob is a Man is:
=bill.barnhill(=bob)($pr*0.5)/$a/+man

You can also assert a probability using a separate statement, with the statement
as a subject.  For example the above probability can also be asserted with the
statement:
=bill.barnhill((=bob/$a/+man))/$pr/0.5

The probability of a context can also be asserted. This can only be done by a separate statement,
not by embedding. This probability indicates
the total overall probability that the resource(s) described by the context are
described accurately by the assertions with that context as the subject and asserted
by that asserter.  If the probability for a context is asserted explicitly then
the probabilities of the individual assertions must combine to the asserted probability.

For example, assume we have the following statements:
=alice(=bobby)/$pr/0.25
=alice(=bobby)($pr*0.5)/$a/+man
=alice(=bobby)/$a/+programmer

If we were using the Open World Assumption we could not derive any new assertions from
this.  However, ADDI uses the Closed World Assumption, so we can assume that =bobby is described 
completely by the given statements from the point of view of =alice. As a result we know that
=alice believes the probability of =bobyb being a programmer is 50% (0.5), because
0.5 * 0.5 = 0.25.

If not asserted explicitly then the probability for a context can be calculated
based on the probability of individual assertions with that context as subject, by multiplying
the probabilities of the given assertions (using 1.0 for unasserted probabilties).


