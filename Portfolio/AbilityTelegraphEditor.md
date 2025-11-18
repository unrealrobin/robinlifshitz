# Runtime Ability Telegraph Editor

## Goals
1. Increase Encounter Iteration Speed.
2. Provide productivity tools to Game Designers.
3. No-code Ability Telegraph Editing at Runtime.


## Why this works
1. This system provides Game Designers an easy way to quickly run the game in editor and edit any telegraphed abilities data.
2. Game Designers don't need to code anything at all, they simply iterate by adjusting exposed data on the widget.
3. When the Game Designer approves the data, they populate a Data Table with a new Row with the new data and its ready for Prod or more iteration.


## In Game Screenshots

![Gameplay Screenshot](./Images\PHM_RATE.jpg)

- Works in networked environments so multiple designers can iterate together.
- Ties in cleanly with the popular Gameplay Ability System.
- Light weight and uses already available data.

![Gameplay Screenshot](./Images\RATE_Widget.png)

- Any Data Point can be exposed to or hidden from the widget.
- Widget is easily editable and is made of multiple smaller widgets per data type.


## Code Map
<!-- blank line above! -->

| Class                                 | Role                                                              | Key Methods                                                                                                 | GitHub                                                                                                                                                                                                                                                       |
|---------------------------------------|-------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `UCombatComponent` (Actor Component)  | Manages ability Cooldowns and Resources                           | `HandlePrimaryAbility()`, `HandleSecondaryAbility()`, `ValidateWeaponAbility()`, `GenerateAbilityContext()` | [H](https://github.com/unrealrobin/timbermvp/blob/main/Source/timbermvp/Public/Components/Combat/CombatComponent.h) - [CPP](https://github.com/unrealrobin/timbermvp/blob/main/Source/timbermvp/Private/Components/Combat/CombatComponent.cpp)               |
| `UWeaponAbilityBase` (Ability UObject) | Defines the abilities Logic.                                      | `Execute()`, `HandleCleanup()`                                                                              | [H](https://github.com/unrealrobin/timbermvp/blob/main/Source/timbermvp/Public/Weapons/Abilities/WeaponAbilityBase.h) - [CPP](https://github.com/unrealrobin/timbermvp/blob/main/Source/timbermvp/Private/Weapons/Abilities/WeaponAbilityBase.cpp)           |
| `UBasicSlash` (Melee Primary Ability) | The primary ability for a melee weapon. This ability has a Combo. | `Execute()`, `ResetComboData()`                                                                             | [H](https://github.com/unrealrobin/timbermvp/blob/main/Source/timbermvp/Public/Weapons/Abilities/MeleeWeapon/BasicSlash.h) - [CPP](https://github.com/unrealrobin/timbermvp/blob/main/Source/timbermvp/Private/Weapons/Abilities/MeleeWeapon/BasicSlash.cpp) |

---