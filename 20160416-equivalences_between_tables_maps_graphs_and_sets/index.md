# Equivalences between Tables, Maps, Graphs, and Sets

By _tables_, I mean the common spreadsheet or relational database
conception of data in rectangular grids of rows and columns.

```
| property_a  | property_b  |
|-------------|-------------|
| value_a_one | value_b_one |
| value_a_two | value_b_two |
```

By _maps_, I mean data represented with [map][] data structures. Maps
are also known as associative arrays or dictionaries. In JavaScript
they're called objects, and JavaScript Object Notation ([JSON][]) is a
common format for this type of data.

[map]: https://en.wikipedia.org/wiki/Associative_array
[JSON]: https://en.wikipedia.org/wiki/JSON

```
[{property_a: value_a_one, property_b: value_b_one},
 {property_a: value_a_two, property_b: value_b_two}]
```

By _graphs_, I mean nodes and edges. [RDF][], for example, labels both
nodes and edges. This can be represented with _triples_ of the form
`subject, predicate, object`, where `subject` and `object` are nodes,
and `predicate` is an edge.

[RDF]: https://www.w3.org/RDF/

```
id_one, property_a, value_a_one
id_one, property_b, value_b_one
id_two, property_a, value_a_two
id_two, property_b, value_b_two
```

A visual for this _triple graph_ shows two connected components.

![graph of triple data](triple_graph.png)

Graphs can also have unlabeled edges, in which case one representation
is _doubles_ of the form `subject, object`.

```
id_one, id_a_one
id_a_one, property_a
id_a_one, value_a_one
id_one, id_b_one
id_b_one, property_b
id_b_one, value_b_one
id_two, id_a_two
id_a_two, property_a
id_a_two, value_a_two
id_two, id_b_two
id_b_two, property_b
id_b_two, value_b_two
```

A visual for one connected component of this _double graph_ shows how
the additional identity nodes expand the representation.

![graph of double data](double_graph.png)

In this formulation, with non-identity nodes always leaf nodes, double
graphs are equivalent to [sets][].

[sets]: https://en.wikipedia.org/wiki/Set_(abstract_data_type)

```
[{{property_a, value_a_one}, {property_b, value_b_one}},
 {{property_a, value_a_two}, {property_b, value_b_two}}]
```

---

Longer discussion here.

... Many common ways of organizing data differ only in which
identities they make explicit. ...

In double graph form, there is nothing to distinguish properties from
values.

Something about lists as values / the flexibility of more data types
in some languages...

---

For all the graphs here, I'm not considering duplicate edges.

I made the graph diagrams with [draw.io](https://www.draw.io/).