+++
weight = 1
title = "PhysicalProperties"
description = "The physical properties of an object."
categories = ["API", "Type"]
+++

The **PhysicalProperties** type represents the physical properties of an
object.

# Overview

----

<div class="api-list one two">

| Item | Kind | Description |
| --- | --- | --- |
| [new](#new) | Constructor | Returns properties with density, friction, and elasticity. no content for topic "Types/PhysicalProperties:Constructors/new/Weights/Summary" |
| [Density](#density) | Property | The mass per unit volume. |
| [Elasticity](#elasticity) | Property | How much energy is retained after a collision. |
| [ElasticityWeight](#elasticityweight) | Property | The ratio baised towards the object for elasticity calculations. |
| [Friction](#friction) | Property | The force that opposes lateral motion. |
| [FrictionWeight](#frictionweight) | Property | The ratio baised towards the object for friction calculations. |

</div>

# Constructors

----

## new

 `PhysicalProperties.new(density: float, friction: float, elasticity: float): PhysicalProperties`

The **new** constructor returns a new PhysicalProperties value.
*density* sets the Density field, *friction* sets the Friction field,
and *elasticity* sets the Elasticity field.

 `PhysicalProperties.new(density: float, friction: float, elasticity: float, frictionWeight: float, elasticityWeight: float): PhysicalProperties`

The **new** constructor returns a new PhysicalProperties value.
*density* sets the Density field, *friction* sets the Friction field,
*elasticity* sets the Elasticity field, *frictionWeight* sets the
FrictionWeight field, and *elasticityWeight* sets the ElasticityWeight
field.

# Properties

----

## Density

 `PhysicalProperties.Density: float [readonly]`

The **Density** field returns the mass for unit volume of the object.

## Elasticity

 `PhysicalProperties.Elasticity: float [readonly]`

The **Elasticity** field returns how much energy is retained after a
collision. A value of 1 means the same energy is retained.

## ElasticityWeight

 `PhysicalProperties.ElasticityWeight: float [readonly]`

The **ElasticityWeight** field returns how much the ratio of an elasticity
calculation is baised towards the object during a collision.

## Friction

 `PhysicalProperties.Friction: float [readonly]`

The **Friction** field returns how much force is used to oppose lateral
motion between two contacting surfaces.

## FrictionWeight

 `PhysicalProperties.FrictionWeight: float [readonly]`

The **FrictionWeight** field returns how much the ratio of a friction
calculation is baised towards the object during a collision.