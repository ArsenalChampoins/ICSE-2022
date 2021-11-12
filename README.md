
## *Noted: This web is to show the bugs detected by Grand anonymously. <u>Do not</u> try to find the real information of the authors of Grand!*

To demonstrate the effectiveness of Grand in finding logic bugs in Gremlin-based graph database systems, we evaluate Grand on four widely-used graph database systems, and real-world logic bugs in them.

For all GDBs, we test their latest release versions when we start this work, i.e., Neo4j 3.2.3 (with Neo4j-Gremlin 3.4.10, not the latest version), JanusGraph 0.5.3, TinkerGraph 3.4.10, and HugeGraph 0.11.2. Note that, we use the latest version of Neo4j-Gremlin, but it does not support the latest Neo4j at that time.

Table below shows logic bugs found by Grand, and you can find the test case in the issue URL to reproduce the error.

| Bug Number | GDB         | Issue URL                                                 | Description                                                  | Root Cause                      | Status    |
| :--------- | ----------- | --------------------------------------------------------- | ------------------------------------------------------------ | ------------------------------- | --------- |
| 1          | JanusGraph  | https://github.com/JanusGraph/janusgraph/issues/2751      | JanusGraph cannot deal with abnormal range queries.          | Non-robust, lack type  coercion |           |
| 2          | JanusGraph  | https://github.com/JanusGraph/janusgraph/issues/2773      | IllegalArgumentException  raised in a complex query.         | Incorrect logic implementation  | Confirmed |
| 3          | JanusGraph  | https://github.com/JanusGraph/janusgraph/discussions/2768 | Does Janusgraph support INFINITY in numeric comparisons predicate? | Lack type coercion              |           |
| 4          | JanusGraph  | https://github.com/JanusGraph/janusgraph/issues/2774      | IllegalArgumentException raised in a complex query.          | Incorrect logic implementation  | Confirmed |
| 5          | TinkerGraph | https://issues.apache.org/jira/browse/TINKERPOP-2604      | TinkerGraph could not order vertex/edge without specified property. | Lack logic implementation       | Confirmed |
| 6          | TinkerGraph | https://issues.apache.org/jira/browse/TINKERPOP-2603      | TinkerGraph sometimes could not query float values.          | Lack type coercion              | Fixed     |
| 7          | Neo4j       | https://issues.apache.org/jira/browse/TINKERPOP-2607      | Neo4j could not directly write and query double or float values. | Lack logic implementation       | Confirmed |
| 8          | Neo4j       | https://issues.apache.org/jira/browse/TINKERPOP-2606      | Neo4j could not order vertex/edge without specified property | Lack type coercion              | Fixed     |
| 9          | HugeGraph   | https://github.com/hugegraph/hugegraph/issues/1586        | Duplicate results on outside() and not(between()) API.       | Incorrect logic implementation  | Confirmed |
| 10         | HugeGraph   | https://github.com/hugegraph/hugegraph/issues/1595        | Outside() API can not process boolean value.                 | Lack logic implementation       | Confirmed |
| 11         | HugeGraph   | https://github.com/hugegraph/hugegraph/issues/1575        | HugeGraph could not process Double.Inifnity value.           | Non-robust                      | Fixed     |
| 12         | HugeGraph   | https://github.com/hugegraph/hugegraph/issues/1573        | HugeGraph could not search for String values using between() API. | Lack logic implementation       | Confirmed |
| 13         | HugeGraph   | https://github.com/hugegraph/hugegraph/issues/1582        | Incorrect result was returned when we use the indexed property to query. | Incorrect logic implementation  | Confirmed |
| 14         | HugeGraph   | https://github.com/hugegraph/hugegraph/issues/1579        | Order vertex/edge without  specified property.               | Lack logic implementation       | Confirmed |

