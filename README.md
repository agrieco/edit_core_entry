# edit_core_entry
Rename Zwave nodes in Home Assistance in a very hacky way.

Don't use this unless you are both crazy and have a clue about Home Assistant's internals.

'''
This hack is to replace friendly names and node name for zwave
devices in Home Assistant.  It hopefully addresses the basic problem of
renaming all nodes associated with a zwave device- in a very hacky way.

IT COULD BREAK YOUR Home Assistant Install.  Your responsibility.
If you don't understand the problem this is solving, stop here.

Requires python3

At a high level- here is the logic to follow to use this:
-backup core.entity_registry
-find the zwave node number of the node you want to rename_node
-edit this file in the 'CHANGE ME' section below to indicate the node number
  and the entity name (no spaces) and new (friendly) name
-run this code from the .storage location in homeassistant
  eg: `python3 edit_core_entry.py`
-lots of crap will spew to the screen.  you will see 'Old Entry' and 'New Entry'
  and can compare what has changed
-it will create a new file- core.entity_registry.new
-check the .new file over
-stop HASS
-replace core.entity_registry with core.entity_registry.new
-start HASS
-cross fingers
'''
