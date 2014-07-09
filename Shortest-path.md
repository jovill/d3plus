#### <a href="#">d3plus.network.shortestPath( *edges*, *source*, *options* )</a>
Finds the shortest paths in the graph.

__edges__; A list of edge objects

__source__; Specifies the source node. It can be a:
 - pointer to the source node or its id
 - string denoting the id of the source node

__options__; A dictionary of optional parameters. Here are the supported keys:

| Key | Description | Accepted Value(s) | Default Value |
|---|---|---|---|
target | If it is an object, it should point to the target node. <br/> If string, it should be the id of the target node. If undefined, the algorithm returns the closest nodes to the source. | string, object | undefined
directed | Specifies whether the graph is directed. | boolean | false
distance | If a number, every edge has the same distance. <br/> If string, the name of the attribute in edge that describes the distance of that edge. <br/> If array, each value corresponds to the distance of the respective edge in the edges array. <br/> If function, given the edge, it should return the distance. | number, string, array, function | 1

    # nodeid; it can be:
      # undefined; then we assume that each node obtained by getting the endpoints of an edge is a string/number describing the id of the node
      # string; the name of the attribute in node that describes the id of the node.
      # function; given the node, returns the id.

    # startpoint; it can be:
      # undefined; it is assumed that edge.source points to the source of the edge
      # string; the name of the attribute in edge pointing to the source of the edge
      # function; given an edge returns the source node of that edge

    # endpoint; it can be:
      # undefined; it is assumed that edge.target points to the target of the edge
      # string; the name of the attribute in edge pointing to the target of the edge
      # function; given an edge returns the target node of that edge

    # K; returns the top K results (defaults to 1). Depending on the target, it means:
      # if target is specified, returns the top K shortest paths to the given target
      # if target is undefined, returns the top K closest nodes to the given source

    # nodes; if defined, the input is assumed to be normalized and nodes is assumed to be a dictionary
    # that maps node id to the outedges of the node