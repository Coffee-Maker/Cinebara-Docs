# Stages

A Stage holds the content of a [Session](sessions.md) and is also the thing you conceptually save (when closing a session) and load (when starting a session). Stages can be edited and performed on entirely within Cinebara.

A Stage always has at least one [Node](nodes.md) in it which serves as the root of the Stage's [tree](nodes.md#trees).

# Scenes

!!!warning
Scenes are not yet implemented
!!!

A scene is some configuration of a stage. Elements can be added that themselves are not a part of the stage and changes can be made to the stage that are non-destructive All changes, such as deleting nodes, repositioning a prop, or changing the time of day, can be reverted. Changes made to the original stage are not immediately merged into scenes.

!!!question
Should scenes be like branches of the stage? As in, source control... Scenes could derive other scenes. Infact, a stage should maybe be branchable in general. This concept could be extended to entities, quite like Unity's prefab variants. I think it should. - Kufi
!!!

# Snapshots

!!!warning
Snapshots are not yet implemented
!!!

A snapshot allows a scene to be saved up to a certain point such that the performance after that point can be recaptured for alternative takes. Like splitting timelines!
