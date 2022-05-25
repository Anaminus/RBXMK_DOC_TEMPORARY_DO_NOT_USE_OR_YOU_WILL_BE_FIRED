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
Behavior                             | Class    | Field                                                                     | Description
-------------------------------------|----------|---------------------------------------------------------------------------|------------
`Instance.ClearAllChildren`          | Instance | [ClearAllChildren](api/types/Instance#ClearAllChildren)                   | Returns ClearAllChildren method.
`Instance.Clone`                     | Instance | [Clone](api/types/Instance#Clone)                                         | Returns Clone method.
`Instance.Destroy`                   | Instance | [Destroy](api/types/Instance#Destroy)                                     | Returns Destroy method.
`Instance.FindFirstAncestor`         | Instance | [FindFirstAncestor](api/types/Instance#FindFirstAncestor)                 | Returns FindFirstAncestor method.
`Instance.FindFirstAncestorOfClass`  | Instance | [FindFirstAncestorOfClass](api/types/Instance#FindFirstAncestorOfClass)   | Returns FindFirstAncestorOfClass method.
`Instance.FindFirstAncestorWhichIsA` | Instance | [FindFirstAncestorWhichIsA](api/types/Instance#FindFirstAncestorWhichIsA) | Returns FindFirstAncestorWhichIsA method.
`Instance.FindFirstChild`            | Instance | [FindFirstChild](api/types/Instance#FindFirstChild)                       | Returns FindFirstChild method.
`Instance.FindFirstChildOfClass`     | Instance | [FindFirstChildOfClass](api/types/Instance#FindFirstChildOfClass)         | Returns FindFirstChildOfClass method.
`Instance.FindFirstChildWhichIsA`    | Instance | [FindFirstChildWhichIsA](api/types/Instance#FindFirstChildWhichIsA)       | Returns FindFirstChildWhichIsA method.
`Instance.GetChildren`               | Instance | [GetChildren](api/types/Instance#GetChildren)                             | Returns GetChildren method.
`Instance.GetDescendants`            | Instance | [GetDescendants](api/types/Instance#GetDescendants)                       | Returns GetDescendants method.
`Instance.GetFullName`               | Instance | [GetFullName](api/types/Instance#GetFullName)                             | Returns GetFullName method.
`Instance.IsA`                       | Instance | [IsA](api/types/Instance#IsA)                                             | Returns IsA method.
`Instance.IsAncestorOf`              | Instance | [IsAncestorOf](api/types/Instance#IsAncestorOf)                           | Returns IsAncestorOf method.
`Instance.IsDescendantOf`            | Instance | [IsDescendantOf](api/types/Instance#IsDescendantOf)                       | Returns IsDescendantOf method.
`Instance.Name`                      | Instance | [Name](api/types/Instance#Name)                                           | Property used by methods that query the name of an instance.
`Instance.Parent`                    | Instance | [Parent](api/types/Instance#Parent)                                       | Property used to get or set parent instance.

# Symbols
Behavior           | Class    | Field          | Description
-------------------|----------|----------------|------------
`rbxmk.Desc`       | Instance | sym.Desc       | Gets or sets the inherited descriptor of the instance.
`rbxmk.IsService`  | Instance | sym.IsService  | Gets or sets whether the instance is a service.
`rbxmk.Properties` | Instance | sym.Properties | Gets or sets all the properties of the instance at once.
`rbxmk.RawDesc`    | Instance | sym.RawDesc    | Gets or sets the actual descriptor of the instance.
`rbxmk.Reference`  | Instance | sym.Reference  | Gets or sets the string identifying the instance for serialization.

# Descend
Behavior        | Class    | Field   | Description
----------------|----------|---------|------------
`rbxmk.Descend` | Instance | Descend | Returns Descend method.

# DataModel
Behavior                     | Class     | Field        | Description
-----------------------------|-----------|--------------|------------
`DataModel.Metadata`         | DataModel | sym.Metadata | Gets or sets root metadata for serialization.
`ServiceProvider.GetService` | DataModel | GetService   | Returns GetService method.

# Attributes
Behavior                       | Class    | Field               | Description
-------------------------------|----------|---------------------|------------
`Instance.AttributesSerialize` | Instance | AttributesSerialize | Property used to serialize attributes.
`Instance.GetAttribute`        | Instance | GetAttribute        | Returns GetAttribute method.
`Instance.GetAttributes`       | Instance | GetAttributes       | Returns GetAttributes method.
`Instance.SetAttribute`        | Instance | SetAttribute        | Returns SetAttribute method.
`Instance.SetAttributes`       | Instance | SetAttributes       | Returns SetAttributes method.

# Tags
Behavior                       | Class             | Field      | Description
-------------------------------|-------------------|------------|------------
`CollectionService.AddTag`     | CollectionService | AddTag     | Returns AddTag method.
`CollectionService.GetAllTags` | CollectionService | GetAllTags | Returns GetAllTags method.
`CollectionService.GetTagged`  | CollectionService | GetTagged  | Returns GetTagged method.
`CollectionService.GetTags`    | CollectionService | GetTags    | Returns GetTags method.
`CollectionService.HasTag`     | CollectionService | HasTag     | Returns HasTag method.
`CollectionService.RemoveTag`  | CollectionService | RemoveTag  | Returns RemoveTag method.
`Instance.Tags`                | Instance          | Tags       | Property used to serialize tags.

# Pivots
Behavior                        | Class      | Field                  | Description
--------------------------------|------------|------------------------|------------
`Attachment.Axis`               | Attachment | Axis                   |
`Attachment.CFrame`             | Attachment | CFrame                 | The primary property from which other Attachment properties are derived.
`Attachment.Orientation`        | Attachment | Orientation            |
`Attachment.Position`           | Attachment | Position               |
`Attachment.SecondaryAxis`      | Attachment | SecondaryAxis          |
`Attachment.WorldAxis`          | Attachment | WorldAxis              |
`Attachment.WorldCFrame`        | Attachment | WorldCFrame            |
`Attachment.WorldOrientation`   | Attachment | WorldOrientation       |
`Attachment.WorldPosition`      | Attachment | WorldPosition          |
`Attachment.WorldSecondaryAxis` | Attachment | WorldSecondaryAxis     |
`BasePart.CFrame`               | BasePart   | CFrame                 |
`BasePart.Orientation`          | BasePart   | Orientation            |
`BasePart.Position`             | BasePart   | Position               |
`BasePart.Rotation`             | BasePart   | Rotation               |
`BasePart.Size`                 | BasePart   | Size                   |
`Bone.Transform`                | Bone       | Transform              |
`Bone.TransformedCFrame`        | Bone       | TransformedCFrame      |
`Bone.TransformedWorldCFrame`   | Bone       | TransformedWorldCFrame |
`Model.GetBoundingBox`          | Model      | GetBoundingBox         | Returns GetBoundingBox method.
`Model.GetPrimaryPartCFrame`    | Model      | GetPrimaryPartCFrame   | Returns GetPrimaryPartCFrame method.
`Model.PrimaryPart`             | Model      | PrimaryPart            |
`Model.SetPrimaryPartCFrame`    | Model      | SetPrimaryPartCFrame   | Returns SetPrimaryPartCFrame method.
`Model.WorldPivot`              | Model      | WorldPivot             |
`Model.WorldPivotData`          | Model      | WorldPivotData         |
`PVInstance.GetPivot`           | PVInstance | GetPivot               | Returns GetPivot method.
`PVInstance.PivotTo`            | PVInstance | PivotTo                | Returns PivotTo method.
