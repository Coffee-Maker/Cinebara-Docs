# Nodes

A Node is a thing which may have other Nodes as children. A Node's parent is the singular Node that it is a child of. A Node can not have more than one parent, but it may have no parent at all.

# Trees {#trees}
A Node with no parent is considered the root of its tree. A tree is all Nodes descendant of a root Node and the root itself. A Node's relationships (its parent & children) are always transparent, as in, they are always readable.

There are many types of Nodes, all of which have their own specific purpose. As a general rule, a Node should have at most one purpose.

A few example nodes:

=== Node
The simplest type of Node. It has no special behaviour.
===

=== Camera
Draws the scene from the perspective of the Node.
===

=== Transform 3D
Translates this node and all of its descendants by the specified offset position, rotation, and scale.
The transformations defined in the node are accumulated onto the transformations defined in any parent Node3Ds.
===