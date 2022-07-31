# LUtils
Blueprint library Plugin for Unreal Engine 5+, for debug prints, vectors and loops.

# Requirements
- UnrealEngine 5+

# Main methods

- LInfo, LDebug, LSuccess, LWarn, LError, each will print with different colors and durations, you can filter which levels to output on a per blueprint basis:

![Prints](/Resources/Prints.png?raw=true)


- LDrawDebugVectorOnActor, LDrawDebugVectorOnPlayer, will let you draw a vector on an actor, with optional offset, in worldspace or not:

![Prints](/Resources/LDrawDebugVector.png?raw=true)


- LForLoopWithDelay, LForLoopWithDelayAndWait, LForLoopSequential, LForEachLoopSequential, will let you have delays/latent nodes inside for loops:

![Prints](/Resources/LForLoopSequential.png?raw=true)

# Installation
- Download: click on Code, Download Zip.
- On your UnrealEngine project folder, create a folder **Plugins** if none is present.
- Open the downloaded ZIP file and extract **LUtils-main** inside **Plugins** and rename the copied folder to **LUtils**.
- Open your project in UnrealEngine and go into **Edit** then **Plugins**.
- On the Plugins window, search for **LUtils** and enable it.

# GameInstance
To use the executions timers (to show the elapsed time between a start and a stop node) and to be able to disable all prints (except Errors prints), you need to use the provided **BP_LDebugGameInstance**, you can either use it as base GameInstance, or reparent it to your own GameInstance. Then define your desired GameInstance in **Projet Settings**.

# Implementing BPI_LDebug
By default all levels can be printed, if you want to be able to limit the levels a specific Blueprint can print, you need to implement the interface **BPI_LDebug**
- Go into your blueprint asset
- Click on **Class Settings**
- Seek the **Interface / Implemented** interfaces part on the Details tab, and add the **BPI_LDebug**
- A new function will be added to your blueprint: **GetDebugMask**
  - You need to create a node **Make Bitmask** and set the type of enum to **ELDebugLevel** on the Details tab
  - You can click on **no flags** and check every levels that you want your blueprint to print
  ![Alt text](Resources/BPI-GetDebugMask.png?raw=true "Optional Title")

# Example
You can look at the file **BP_ExampleLDebug**

### If you don's see the plugin inside the Content Browser, you need to click on **Settings** top right of the Content Browser, then check **Show Plugin Content** ###
