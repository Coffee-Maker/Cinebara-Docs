# Sessions

A session holds a loaded instance of a [Stage](stages.md) and may be networked. Fundamentally, a session exists to provide access to a Stage.

A session can contain many trees that serve different purposes. 
One specific tree that the session holds is the Stage, which is the primary tree you interact with.

Any node created for a session is remembered so that when the session closes, all of its resources can be cleaned up. This means that if a node ever falls into Limbo, it is still remembered by the session.

!!!warning 
Networking is not yet implemented
!!!

# The Master
The master of a session is the user that serves as the source of truth for network events and replication order. All reliable packets are sent through the master and redistributed to other users. 

Users may establish direct connections with eachother for unreliable data streams. This is useful for decreasing latency as much as possible to make acting with someone more natural/realtime.

In the event that the master is lost, perhaps due to a crash, a user is chosen to assume the role of master.

!!!question
- How do you create a session?
- Can a session host multiple stages?
- Is this where Entities are collaboratively edited?
- How do we choose a new master when the old one is lost?
!!!

# Limbo

A node that is not inside of a session's trees is considered to be in "Limbo". A node may be intentionally placed in Limbo to temporarily hide it and potentially bring it back. This concept is used for Entities, where disconnecting the tree of an entity and the stage is an important concept for protecting the content of the entity.
