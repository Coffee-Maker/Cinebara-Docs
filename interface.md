# Interface

!!!warning
UI is not yet implemented
!!!

The UI of Cinebara is built from the same system as in-world UI. The structure is something like this:

```
main window
    menu
        menus
        viewport (referencing the local ghost camera of the loaded session)
    loaded session

local ghost
    camera

stage
```

Since Cinebara has dockable windows and potentially multiple loaded sessions, this structure is dynamic and may change based on user configuration and context.