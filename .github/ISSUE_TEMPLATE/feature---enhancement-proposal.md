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
I am working on a 2D Android game I initially completed development of in Construct 3, only to encounter issues with Cordova and WebView in the .apk file.  
I am now redeveloping in Godot. 


**Describe the problem or limitation you are having in your project:**
I wish to make an object follow multiple FollowPath2D nodes, and have encountered all sorts of issues, which I now realise are due to reparenting a node from one path to another.
When the node leaves the scene tree briefly, this kills all the tweens - and probably other things I haven't noticed yet.


**Describe the feature / enhancement and how it helps to overcome the problem or limitation:**
It would be great to provide a way of reparenting nodes, without them leaving the scene tree.  Or if they do have to leave the scene tree, to provide an option to constitute processing while out of the tree.

**Describe how your proposal will work, with code, pseudocode, mockups, and/or diagrams:**
Provide a reparent() method for nodes, which maintains consistency of internal states and running processes, unlike removeChild().

nodeA.reparent($NewParent)

**If this enhancement will not be used often, can it be worked around with a few lines of script?:**
I have no idea how you can reparent an object without impacting tweens etc.  At the moment I have to add an _enter_tree() method which resumes the tweens.  

My concern is, it probably isn't just tweens which are impacted by removal from the tree, and it does cause difficult bugs to fix.

**Is there a reason why this should be core and not an add-on in the asset library?:**
Not that I have found.
