# Redrawing modes #

| dirty \ clear | **HAF.CLEAR\_ALL** | **HAF.CLEAR\_NONE** | **HAF.CLEAR\_ACTORS** |
|:--------------|:-------------------|:--------------------|:----------------------|
| **HAF.DIRTY\_ALL** | _Clear whole layer; draw all actors_ <br /> Too many actors to compute their bounding boxes (particle simulation) | _Do not clear anything; draw all actors_ <br /> Sprite covering the whole layer (background) | _Clear bounding boxes of all actors, then draw them all_ <br /> When clearing the whole area is expensive (large canvas, few actors) |
| **HAF.DIRTY\_CHANGED** | _Clear whole layer; draw only actors who changed_ <br /> Many actors are out of viewport (beings/items currently not visible) | _Do not clear anything; draw only actors who changed_ <br /> Static non-transparent actors | _Clear union of changed bounding boxes, then draw those actors_ <br /> When redrawing an actor is expensive |