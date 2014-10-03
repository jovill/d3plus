### <a name="cluster" href="#cluster">d3plus.network.cluster( *edges* , *options* )</a>

Community detection algorithm (graph clustering/partitioning) based on the paper: *Finding community structure in very large networks, A Clauset, MEJ Newman, C Moore - Physical review E, 2004*

Returns an *Array* of communities, where each community is an *Array* of node ids belonging to that community.

Passed *edges*, a list of edge objects, and *options*, a dictionary of options with the following attributes:

#### distance
Accepts the following values:
* undefined; every edge has default distance of 1
* constant; every edge has the same distance
* string; the name of the attribute in edge that describes the distance of that edge
* array; each value corresponds to the distance of the respective edge in the edges array
* function; given edge, returns the distance

#### nodeid
Accepts the following values:
* undefined; then we assume that each node obtained by getting the endpoints of an edge is a string/number describing the id of the node
* string; the name of the attribute in node that describes the id of the node.
* function; given the node, returns the id.

#### startpoint
Accepts the following values:
* undefined; it is assumed that edge.source points to the source node of the edge
* string; the name of the attribute in edge pointing to the source node of the edge
* function; given an edge returns the source node of that edge

#### endpoint
Accepts the following values:
* undefined; it is assumed that edge.target points to the target of the edge
* string; the name of the attribute in edge pointing to the target of the edge
* function; given an edge returns the target node of that edge

#### nodes
If defined, the input is assumed to be normalized and nodes is assumed to be a dictionary that maps node id to the outedges of the node.


### <a name="distances" href="#distances">d3plus.network.distances( *Array* , *callback* )</a>

Returns an *Array* listing all of the pixel distances between the X/Y positions of each node. If the nodes in the *Array* passed to the function do not have "x" and "y" keys, you may pass a *callback* function to the utility that should return the node's X and Y coordinates as an *Array* ([x,y]).


### <a name="normalize" href="#normalize">d3plus.network.normalize( *edges* , *options* )</a>

Normalizes the graph input and checks if it is valid.

### <a name="shortestPath" href="#shortestPath">d3plus.network.shortestPath( *edges* , *source* , *options* )</a>

Finds the shortest paths between two nodes in a graph. Returns the top K shortest paths from the source to the given target, or the top K closest nodes to the source.

*edges* is a list of edge objects and *source* can be either a pointer to the source node/id or a string denoting the id of the source node.

*options* is a dictionary of options with the following attributes:

#### target
Accepts the following values:
* undefined; then the algorithm returns the closest nodes to the source
* pointer to the target node or its id
* string denoting the id of the target node

#### directed
Specifies whether the graph is directed. Default is `false`.

#### distance
Accepts the following values:
* undefined; every edge has default distance of 1
* constant; every edge has the same distance
* string; the name of the atrribute in edge that describes the distance of that edge
* array; each value corresponds to the distance of the respective edge in the edges array
* function; given edge, returns the distance

#### nodeid
Accepts the following values:
* undefined; then we assume that each node obtained by getting the endpoints of an edge is a string/number describing the id of the node
* string; the name of the attribute in node that describes the id of the node.
* function; given the node, returns the id.

#### startpoint
Accepts the following values:
* undefined; it is assumed that edge.source points to the source of the edge
* string; the name of the attribute in edge pointing to the source of the edge
* function; given an edge returns the source node of that edge

#### endpoint
Accepts the following values:
* undefined; it is assumed that edge.target points to the target of the edge
* string; the name of the attribute in edge pointing to the target of the edge
* function; given an edge returns the target node of that edge

#### K
Returns the top K results (defaults to 1). Depending on the target, it means:
* if target is specified, returns the top K shortest paths to the given target
* if target is undefined, returns the top K closest nodes to the given source

#### nodes
If defined, the input is assumed to be normalized and nodes is assumed to be a dictionary that maps node id to the outedges of the node.

### <a name="subgraph" href="#subgraph">d3plus.network.subgraph( *edges* , *source* , *options* )</a>

Returns a graph object composed of nodes of distance K away from the source node and the links between them.

*edges* is a list of edge objects and *source* can be either a pointer to the source node/id or a string denoting the id of the source node.

*options* is a dictionary of options with the following attributes:

#### K
Returns the subgraph of nodes that are at most distance K from the source. Default is 1.

#### directed
Whether the graph is directed. Default is false.

#### distance
Accepts the following values:
* undefined; every edge has default distance of 1
* constant; every edge has the same distance
* string; the name of the atrribute in edge that describes the distance of that edge
* array; each value corresponds to the distance of the respective edge in the edges array
* function; given edge, returns the distance

#### nodeid
Accepts the following values:
* undefined; then we assume that each node obtained by getting the endpoints of an edge is a string/number describing the id of the node
* string; the name of the attribute in node that describes the id of the node.
* function; given the node, returns the id.

#### startpoint
Accepts the following values:
* undefined; it is assumed that edge.source points to the source of the edge
* string; the name of the attribute in edge pointing to the source of the edge
* function; given an edge returns the source node of that edge

#### endpoint
Accepts the following values:
* undefined; it is assumed that edge.target points to the target of the edge
* string; the name of the attribute in edge pointing to the target of the edge
* function; given an edge returns the target node of that edge

#### nodes
If defined, the input is assumed to be normalized and nodes is assumed to be a dictionary that maps node id to the outedges of the node.
