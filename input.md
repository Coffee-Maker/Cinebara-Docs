# Input

Raw inputs are transformed into Actions via a series of Action Generators. An Action Generator can be though of as a keybind, something that turns a raw input concept (Like pressing the W key) into an Action with a purpose (Like "move forward").

At the start of a frame, raw inputs are turned into a list of actions. The actions are processed through the session following the process order defined above. Nodes can then listen for a certain Action and read it before optionally consuming it (implying other nodes should not use it again).

# Ownership
!!!warning
Action ownership is not yet implemented
!!!

Some nodes may intend to use inputs from a specific user while ignoring inputs from other users. For this, Actions have an owner which can be used as a filter by Nodes.
