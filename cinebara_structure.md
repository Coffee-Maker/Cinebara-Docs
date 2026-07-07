# Entities

An entity is some separate tree that does not exist in a Stage's tree but is referenced by some node within the Stage's tree. The node that sits in the Stage is called an Entity Instance and exposes a dynamic set of configurable properties that allow data to be shared between the Stage and the Entity.

Events like ticks or inputs being received by an Entity Instance are propagated to their referenced Entity root.

# Ghosts

A ghost is a tree in a session that represents a user connected to that session. A user acting via a ghost can interact with the Stage with limited access.

# Process order

Events like "Actions" and "Ticks" need to be distributed to the nodes of a session. This is done one tree at a time, and for each tree you broadcast depth first.

```
function broadcast_to(node, event_to_run)
    for each child of node
        broadcast_to(child)
    event_to_run.execute
```

This can also be thought of as "ascending the tree", though this phrase can be confusing as trees are usually depicted upside-down. You ascend from the root to the leaf nodes, but you descend down the tree as depicted in a GUI.

First, all ghost trees are processed in order of session age descending. Older ghosts are processed first. Then the stage is processed.

Some events may bypass certain trees for security or sensibility reasons. For example, your personal inputs are sent to your personal ghost and then to the stage. They are never propagated to other user's ghosts.