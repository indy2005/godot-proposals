---
name: Feature / Enhancement proposal
about: 'Open a new proposal'
title: ''
labels: ''
assignees: ''

---

<!--
Please fill in *all* the questions below and don't remove any of them.
Proposals not following the template below will be closed immediately.
-->

**Describe the project you are working on:**
Re-engineering a Construct 3 2D game due to problems with performance in WebView Cordova build.

**Describe the problem or limitation you are having in your project:**
Godot could take some great ideas from Construct behaviours.  One is the ability to pin one object to another.

At the moment you have to reparent one node to the target so it appears to be pinned to it.  This causes issues that you have to solve.

These include repositioning to local space, scale issues, and rotation issues.

**Describe the feature / enhancement and how it helps to overcome the problem or limitation:**
Add a 'pin()' method, to enable one object to be pinned to another.  This is without reparenting or physics joints.

Taking the Construct idea, you could choose what you want to pin (x,y,rotation...any combination or all)


**Describe how your proposal will work, with code, pseudocode, mockups, and/or diagrams:**
nodeA.pin(nodeB, pinX=True, pinY=True, pinRotation=True)
nodeA.unpin(nodeB)


**If this enhancement will not be used often, can it be worked around with a few lines of script?:**
You reparent one node inside the other, map the coordinates to local space, adjust the scale if the new parent is scaled from 1, and map the local rotation.

Side effects occur due to brief removal from the tree.

**Is there a reason why this should be core and not an add-on in the asset library?:**
Pinning objects opens up a whole world of game mechanics (archery) etc.
