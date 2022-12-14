# RIDER-81746 Repro
Reproduction for Rider issue https://youtrack.jetbrains.com/issue/RIDER-81746

## Instructions

* Clone this repo
* Open the root with Unity `2021.3.10f1`
* Open the C# project in Rider and navigate to the `ExampleUsage` class.
* Observe the following erroneous warning:

![Screenshot 2022-09-20 at 13 14 13](https://user-images.githubusercontent.com/963368/191166045-6c4ee098-98e8-42cc-bd65-f0f1d1e0d25b.png)

## Explanation

The project has two assemblies: 
* `First` (nullables disabled via `csc.rsp`)
* `Second` (nullables enabled via `csc.rsp`)

`ExampleUsage` in the `Second` assembly instantiates an instance of a type defined in `First`, but rider complains that `null` is passed to a non-nullable entity.

## Versions Used

* Unity 2021.3.10f1 (latest LTS)
* Rider 2022.2.3 (latest stable)
* Rider Unity package 3.0.15 (latest stable)
