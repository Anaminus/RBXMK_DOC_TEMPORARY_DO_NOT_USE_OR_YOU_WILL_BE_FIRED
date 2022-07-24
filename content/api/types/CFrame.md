+++
weight = 1
title = "CFrame"
description = "A position and rotation."
categories = ["API", "Type"]
+++

The **CFrame** type is a matrix representing a combined position and
orientation.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [Angles](#angles) | Constructor | Returns a CFrame composed from angles. |
| [fromAxisAngle](#fromaxisangle) | Constructor | Returns a CFrame composed from an axis and angle. |
| [fromEulerAnglesXYZ](#fromeuleranglesxyz) | Constructor | Returns a CFrame composed from Euler angles. |
| [fromEulerAnglesYXZ](#fromeuleranglesyxz) | Constructor | Returns a CFrame composed from Euler angles ordered Y, X, Z. |
| [fromMatrix](#frommatrix) | Constructor | Returns a CFrame from a matrix. |
| [fromOrientation](#fromorientation) | Constructor | Returns a CFrame composed from orientations. |
| [lookAt](#lookat) | Constructor | Returns a CFrame that points towards a location. |
| [new](#new) | Constructor | Returns the default CFrame. Returns a CFrame with a position. Returns a CFrame pointing towards a location while tilted upward. Returns a CFrame with a position from coordinates. Returns a CFrame from a quaternion. Returns a CFrame from raw components. |
| [LookVector](#lookvector) | Property | The forward direction. |
| [P](#p) | Property | The position of the CFrame. |
| [Position](#position) | Property | The position of the CFrame. |
| [RightVector](#rightvector) | Property | The right direction. |
| [UpVector](#upvector) | Property | The up direction. |
| [X](#x) | Property | The X component of the Position. |
| [XVector](#xvector) | Property | The first row of the rotation matrix. |
| [Y](#y) | Property | The Y component of the Position. |
| [YVector](#yvector) | Property | The second row of the rotation matrix. |
| [Z](#z) | Property | The Z component of the Position. |
| [ZVector](#zvector) | Property | The third row of the rotation matrix. |
| [GetComponents](#getcomponents) | Method | Returns the raw components. |
| [Inverse](#inverse) | Method | Returns the inverse CFrame. |
| [Lerp](#lerp) | Method | Linearly interpolates between two CFrames. |
| [PointToObjectSpace](#pointtoobjectspace) | Method | Transforms a Vector3 to local space. |
| [PointToWorldSpace](#pointtoworldspace) | Method | Transforms a Vector3 to world space. |
| [ToAxisAngle](#toaxisangle) | Method | Returns the orientation as an axis and angle. |
| [ToEulerAnglesXYZ](#toeuleranglesxyz) | Method | Returns the orientation as Euler angles. |
| [ToEulerAnglesYXZ](#toeuleranglesyxz) | Method | Returns the orientation as Euler angles order Y, X, Z. |
| [ToObjectSpace](#toobjectspace) | Method | Transforms to local space. |
| [ToOrientation](#toorientation) | Method | Returns the orientation. |
| [ToWorldSpace](#toworldspace) | Method | Transforms to world space. |
| [VectorToObjectSpace](#vectortoobjectspace) | Method | Returns a Vector3 rotated to local space. |
| [VectorToWorldSpace](#vectortoworldspace) | Method | Returns a Vector3 rotated to world space. |
| [\_\_add](#__add) | Operator | Translates by adding. |
| [\_\_eq](#__eq) | Operator | Returns whether two CFrame values are equal. |
| [\_\_mul](#__mul) | Operator | Composes two CFrames. Transforms to world space. |
| [\_\_sub](#__sub) | Operator | Translates by subtracting. |

</div>

# Constructors

----

## Angles

 `CFrame.Angles(rx: float, ry: float, rz: float): CFrame`

The **Angles** constructor returns a CFrame located at the origin,
oriented according to the angles ( *rx*, *ry*, *rz*), in radians.
Rotations are ordered Z, Y, X.

## fromAxisAngle

 `CFrame.fromAxisAngle(axis: Vector3, rotation: float): CFrame`

The **fromAxisAngle** constructor returns a CFrame located at the origin,
rotated *rotation* radians around *axis*.

## fromEulerAnglesXYZ

 `CFrame.fromEulerAnglesXYZ(rx: float, ry: float, rz: float): CFrame`

The **fromEulerAnglesXYZ** constructor returns a CFrame located at the
origin, oriented according to the angles ( *rx*, *ry*, *rz*), in
radians. Rotations are ordered Z, Y, X.

## fromEulerAnglesYXZ

 `CFrame.fromEulerAnglesYXZ(rx: float, ry: float, rz: float): CFrame`

The **fromEulerAnglesYXZ** constructor returns a CFrame located at the
origin, oriented according to the angles ( *rx*, *ry*, *rz*), in
radians. Rotations are ordered Y, X, Z.

## fromMatrix

 `CFrame.fromMatrix(position: Vector3, vx: Vector3, vy: Vector3, vz: Vector3): CFrame`

The **fromMatrix** constructor returns a CFrame located at
*position*, rotated according to the following rotation matrix:

```
[vx.X, vy.X, vz.X]
[vx.Y, vy.Y, vz.Y]
[vx.Z, vy.Z, vz.Z]

```

If *vz* is the zero vector, then *vz* is calculated as the unit of
the cross product of vx and vy.

## fromOrientation

 `CFrame.fromOrientation(rx: float, ry: float, rz: float): CFrame`

The **fromOrientation** constructor returns a CFrame located at the
origin, oriented according to the angles ( *rx*, *ry*, *rz*), in
radians. Rotations are ordered Y, X, Z.

## lookAt

 `CFrame.lookAt(position: Vector3, lookAt: Vector3, up: Vector3? = Vector3.new(0, 1, 0)): CFrame`

The **lookAt** constructor returns a CFrame located at *position*,
facing towards *lookAt*, with the local upward direction determined by
*up*.

## new

 `CFrame.new(): CFrame`

The **new** constructor returns a CFrame with the default orientation
located at the origin.

 `CFrame.new(position: Vector3): CFrame`

The **new** constructor returns a CFrame with the default orientation
located at *position*.

 `CFrame.new(position: Vector3, lookAt: Vector3): CFrame`

The **new** constructor returns a CFrame located at *position*,
facing towards *lookAt*. The local upward direction is (0, 1, 0).

 `CFrame.new(x: float, y: float, z: float): CFrame`

The **new** constructor returns a CFrame located at ( *x*, *y*,
*z*), with the default orientation.

 `CFrame.new(x: float, y: float, z: float, qx: float, qy: float, qz: float, qw: float): CFrame`

The **new** constructor returns a CFrame located at ( *x*, *y*,
*z*), oriented according to the quaternion ( *qx*, *qy*,
*qz*, *qw*).

 `CFrame.new(x: float, y: float, z: float, r00: float, r01: float, r02: float, r10: float, r11: float, r12: float, r20: float, r21: float, r22: float): CFrame`

The **new** constructor returns a CFrame located at ( *x*, *y*,
*z*), oriented according to the following rotation matrix:

```
[r00, r01, r02]
[r10, r11, r12]
[r20, r21, r22]

```

# Properties

----

## LookVector

 `CFrame.LookVector: Vector3 [readonly]`

The **LookVector** field returns the forward-direction, or the negation of
the third column of the rotation matrix.

## P

 `CFrame.P: Vector3 [readonly]`

The **P** field returns the position of the CFrame.

## Position

 `CFrame.Position: Vector3 [readonly]`

The **Position** field returns the position of the CFrame.

## RightVector

 `CFrame.RightVector: Vector3 [readonly]`

The **RightVector** field returns the right-direction, or first column of
the rotation matrix.

## UpVector

 `CFrame.UpVector: Vector3 [readonly]`

The **UpVector** field returns the up-direction, or second column of the
rotation matrix.

## X

 `CFrame.X: float [readonly]`

The **X** field returns the X component of the Position.

## XVector

 `CFrame.XVector: Vector3 [readonly]`

The **XVector** field returns the first row of the rotation matrix.

## Y

 `CFrame.Y: float [readonly]`

The **Y** field returns the Y component of the Position.

## YVector

 `CFrame.YVector: Vector3 [readonly]`

The **YVector** field returns the second row of the rotation matrix.

## Z

 `CFrame.Z: float [readonly]`

The **Z** field returns the Z component of the Position.

## ZVector

 `CFrame.ZVector: Vector3 [readonly]`

The **ZVector** field returns the third row of the rotation matrix.

# Methods

----

## GetComponents

 `CFrame:GetComponents(): (x: float, y: float, z: float, r00: float, r01: float, r02: float, r10: float, r11: float, r12: float, r20: float, r21: float, r22: float)`

The **GetComponents** method returns the components of the CFrame's
position and rotation matrix.

## Inverse

 `CFrame:Inverse(): CFrame`

The **Inverse** method returns the inverse of the CFrame.

## Lerp

 `CFrame:Lerp(goal: CFrame, alpha: float): CFrame`

The **Lerp** method returns a CFrame linearly interpolated from the CFrame
to *goal* according to *alpha*, which has an interval of \[0, 1\].

## PointToObjectSpace

 `CFrame:PointToObjectSpace(v: Vector3): Vector3`

The **PointToObjectSpace** method returns a Vector3 transformed from world
to local space of the CFrame.

## PointToWorldSpace

 `CFrame:PointToWorldSpace(v: Vector3): Vector3`

The **PointToWorldSpace** method returns a Vector3 transformed from local
to world space of the CFrame.

## ToAxisAngle

 `CFrame:ToAxisAngle(): (axis: Vector3, rotation: float)`

The **ToAxisAngle** method returns the orientation of the CFrame as an
angle, in radians, rotated around an axis.

## ToEulerAnglesXYZ

 `CFrame:ToEulerAnglesXYZ(): (rx: float, ry: float, rz: float)`

The **ToEulerAnglesXYZ** method returns the approximate angles of the
CFrame's orientation, in radians, if ordered Z, Y, X.

## ToEulerAnglesYXZ

 `CFrame:ToEulerAnglesYXZ(): (rx: float, ry: float, rz: float)`

The **ToEulerAnglesYXZ** method returns the approximate angles of the
CFrame's orientation, in radians, if ordered Y, X, Z.

## ToObjectSpace

 `CFrame:ToObjectSpace(cf: CFrame): CFrame`

The **ToObjectSpace** method returns the CFrame transformed from world to
local space of *cf*.

## ToOrientation

 `CFrame:ToOrientation(): (rx: float, ry: float, rz: float)`

The **ToOrientation** method returns the approximate angles of the
CFrame's orientation, in radians, if ordered Y, X, Z.

## ToWorldSpace

 `CFrame:ToWorldSpace(cf: CFrame): CFrame`

The **ToWorldSpace** method returns the CFrame transformed from local to
world space of *cf*.

## VectorToObjectSpace

 `CFrame:VectorToObjectSpace(v: Vector3): Vector3`

The **VectorToObjectSpace** method returns a Vector3 rotated from world to
local space of the CFrame.

## VectorToWorldSpace

 `CFrame:VectorToWorldSpace(v: Vector3): Vector3`

The **VectorToWorldSpace** method returns a Vector3 rotated from local to
world space of the CFrame.

# Operators

----

## \_\_add

 `CFrame + Vector3 -> CFrame`

The **add** operator returns the CFrame translated in world space by the
operand.

## \_\_eq

 `CFrame == CFrame`

The **equal** operator returns true if both operands are CFrame, and each
corresponding component is equal.

## \_\_mul

 `CFrame * CFrame -> CFrame`

The **mul** operator returns the composition of two CFrames.

 `CFrame * Vector3 -> Vector3`

The **mul** operator returns the operand transformed from local to world
space of the CFrame.

## \_\_sub

 `CFrame - Vector3 -> CFrame`

The **sub** operator returns the CFrame translated in world space by the
negation of the operand.