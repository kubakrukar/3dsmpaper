# Descriptions of individual columns from the file interrater-JakubAhmed-Exp1_building-2Dand3D.xlsx

## relation.code
Spatial relation being evaluated. 

First letter is for axis (X/Y/Z)
The last two letters stand for the landmarks/objects between which the relation is being evaluated, specifically their first letter in German. So HP means "shark-path".

* P: Path
* N: Rhino (Nashorn)
* A: Car (Auto)
* K: Cat (Katze)
* H: Shark (Hai)
* B: Trees (Bäume)
* S: Sheep (Schaf)


All axes refer to the viewing direction when standing in front of the building and the line of sight is perpendicular to the entrance (i.e. looking at the entrance to the VR model of the building).

## relation.short
Short description of the spatial relation - useful for evaluating the drawings.

## relation.long.desc
Longer description of how to evaluate the spatial relation.

## visibility
Is the given spatial relation visible in the sketch map?

## correctness
If visible, is it correct or not? (if not visible than NA)

Spatial relations of relation.type = "generic.relations" have visibility set to NA and we only evaluate their correctness.

Spatial relation "Perspective" is a classification of the type of the sketch map from this list: https://en.m.wikipedia.org/wiki/Multiview_orthographic_projection#Section

Values of 0,1,NA are given here.

1 --> True

0 --> False

NA --> can't be judged

If it's generic.relations type, the correctness is the only metric to be judged. therefore the visibility = NA
If it's object-object.relations, or object-path.relations type, and if it is not visible (= 0), and therefore we can't judge correctness, the value of the correctness should be = NA


The spatial relation in X direction is visible if one can see that one of the objects is more to the left, right, or at the same location relativly to when standing in front of the building with the line of sight is perpendicular to the entrance door.

The spatial relation in Y direction is visible if one can see that one object is more in the front, back, or at the same position relatively to when standing in front of the building with the line of sight is perpendicular to the entrance door.

The spatial relation in Z direction is visible if one can see that one object is higher or lower, or same height relativly to when standing in front of the building and the line of sight is perpendicular to the entrance door.

If an object is described as being left, right, front, back, higher, lower to another object, this means that there is no overlap between their bounding boxes. Overlap indicates that the two objects are in the same position.

The visibility is considered NA if the two objects are not in the same drawing; for example, in a top-down perspective where each floor is drawn separately, comparisons between objects from different drawings in the X and Y dimension are not applicable. Z dimension might be visible if such floors are labelled.