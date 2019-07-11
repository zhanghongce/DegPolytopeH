# DegPolytopeH

Finding H-representation of a (possibly degenerate) polytope given vertices

# What's the difference from QHull or Cdd or PPL?

DegPolytopeH uses convex hull algorithm from QHull/Cdd/PPL internally, but additionally, it takes care of the case of degenerate polytopes. QHull will stop and report error on degenerate polytopes, whereas Cdd/PPL will give an over-approximation of the exact H-representation. (If the exact polytope is not required, QHull has the J option to slightly  shift the points to makes it non-degenerate)

# How it works?

When you have a degenerate polytope, you can project it to a low dimension space where it becomes full-dimensional, and then QHull/Cdd/PPL can handle the rest.

The projection matrix is found by SVD.
