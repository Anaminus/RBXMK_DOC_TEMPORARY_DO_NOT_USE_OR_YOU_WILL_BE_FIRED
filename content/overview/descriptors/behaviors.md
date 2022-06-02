+++
weight = 30
title = "Behaviors"
+++

{{<noimpl>}}

This page lists and describes the available [behavior
descriptors](overview/descriptors#behaviors).

Each behavior has a corresponding class and field. That is, when the combination
of class and field has no definition, that behavior is used as the default. A
behavior can be explicitly unset by setting the behavior to an empty string.

# Basic
<div class="api-list">

Behavior                             | Description
-------------------------------------|------------
`Instance.ClearAllChildren`          | Returns ClearAllChildren method.
`Instance.Clone`                     | Returns Clone method.
`Instance.Destroy`                   | Returns Destroy method.
`Instance.FindFirstAncestor`         | Returns FindFirstAncestor method.
`Instance.FindFirstAncestorOfClass`  | Returns FindFirstAncestorOfClass method.
`Instance.FindFirstAncestorWhichIsA` | Returns FindFirstAncestorWhichIsA method.
`Instance.FindFirstChild`            | Returns FindFirstChild method.
`Instance.FindFirstChildOfClass`     | Returns FindFirstChildOfClass method.
`Instance.FindFirstChildWhichIsA`    | Returns FindFirstChildWhichIsA method.
`Instance.GetChildren`               | Returns GetChildren method.
`Instance.GetDescendants`            | Returns GetDescendants method.
`Instance.GetFullName`               | Returns GetFullName method.
`Instance.IsA`                       | Returns IsA method.
`Instance.IsAncestorOf`              | Returns IsAncestorOf method.
`Instance.IsDescendantOf`            | Returns IsDescendantOf method.
`Instance.Name`                      | Property used by methods that query the name of an instance.
`Instance.Parent`                    | Property used to get or set parent instance.

</div>

# Symbols
<div class="api-list">

Behavior           | Description
-------------------|------------
`rbxmk.Desc`       | Gets or sets the inherited descriptor of the instance.
`rbxmk.IsService`  | Gets or sets whether the instance is a service.
`rbxmk.Properties` | Gets or sets all the properties of the instance at once.
`rbxmk.RawDesc`    | Gets or sets the actual descriptor of the instance.
`rbxmk.Reference`  | Gets or sets the string identifying the instance for serialization.

</div>

# Descend
<div class="api-list">

Behavior        | Description
----------------|------------
`rbxmk.Descend` | Returns Descend method.

</div>

# DataModel
<div class="api-list">

Behavior                     | Description
-----------------------------|------------
`DataModel.Metadata`         | Gets or sets root metadata for serialization.
`ServiceProvider.GetService` | Returns GetService method.

</div>

# Attributes
<div class="api-list">

Behavior                       | Description
-------------------------------|------------
`Instance.AttributesSerialize` | Property used to serialize attributes.
`Instance.GetAttribute`        | Returns GetAttribute method.
`Instance.GetAttributes`       | Returns GetAttributes method.
`Instance.SetAttribute`        | Returns SetAttribute method.
`Instance.SetAttributes`       | Returns SetAttributes method.

</div>

# Tags
<div class="api-list">

Behavior                       | Description
-------------------------------|------------
`CollectionService.AddTag`     | Returns AddTag method.
`CollectionService.GetAllTags` | Returns GetAllTags method.
`CollectionService.GetTagged`  | Returns GetTagged method.
`CollectionService.GetTags`    | Returns GetTags method.
`CollectionService.HasTag`     | Returns HasTag method.
`CollectionService.RemoveTag`  | Returns RemoveTag method.
`Instance.Tags`                | Property used to serialize tags.

</div>

# Pivots
<div class="api-list">

Behavior                        | Description
--------------------------------|------------
`Attachment.Axis`               | Property used as the local primary axis, derived from the CFrame property.
`Attachment.CFrame`             | The primary property from which other Attachment properties are derived.
`Attachment.Orientation`        | Property used as the local orientatation, derived from the CFrame property.
`Attachment.Position`           | Property used as the local position, derived from the CFrame property.
`Attachment.SecondaryAxis`      | Property used as the local secondary axis, derived from the CFrame property.
`Attachment.WorldAxis`          | Property used as the primary world axis, derived from the CFrame property.
`Attachment.WorldCFrame`        | Property used as the world CFrame property, derived from the CFrame property.
`Attachment.WorldOrientation`   | Property used as the world orientatation, derived from the CFrame property.
`Attachment.WorldPosition`      | Property used as the world position, derived from the CFrame property.
`Attachment.WorldSecondaryAxis` | Property used as the world secondary axis, derived from the CFrame property.
`BasePart.CFrame`               | The primary property from which other CFrame properties are derived.
`BasePart.Orientation`          | Property used as the orientation, derived from the CFrame property.
`BasePart.Position`             | Property used as the position, derived from the CFrame property.
`BasePart.Rotation`             | Property used as the rotation, derived from the CFrame property.
`BasePart.Size`                 | Property used to indicate the size of the BasePart.
`Model.GetBoundingBox`          | Returns GetBoundingBox method.
`Model.GetPrimaryPartCFrame`    | Returns GetPrimaryPartCFrame method.
`Model.PrimaryPart`             | Property used to indicate the primary part of a model.
`Model.SetPrimaryPartCFrame`    | Returns SetPrimaryPartCFrame method.
`Model.WorldPivot`              | Property used as the pivot of the model.
`Model.WorldPivotData`          | Property used to store the pivot of the model.
`PVInstance.GetPivot`           | Returns GetPivot method.
`PVInstance.PivotTo`            | Returns PivotTo method.

</div>
