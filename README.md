# Pattern Recognition with Sequence Variables

C++ implementation of dependency-based decomposition and tree pattern matching with sequence variables.

The algorithm preprocesses a pattern by grouping dependent sequence-variable occurrences into **blocks** and **bundles**. Independent sibling bundles can then be matched separately, in any order or in parallel.

## Variables

The parser supports three types of variables:

```text
~x   exactly one term
`x   one or more terms
_x   zero or more terms
```

For example:

```text
Pattern:
f(_x,g(~a,`y),_x,h(`y,~a),_z,k(~b),_z)

Subject:
f(p,q,g(r,s,t),p,q,h(s,t,r),u,v,k(w),u,v)
```

produces:

```text
_x{p,q}
~a{r}
`y{s,t}
_z{u,v}
~b{w}
```
