
# V1.2 Update
Fixes:
- Landscape mesh getting distance culled

## Landscape mesh getting distance culled
The first thing to do is locate the `SM_Landscape` Static Mesh. Right click it, go to `Scripted Asset Actions`, `Convert To Prop`, and pick either of the materials. Or alternatively `Asset Actions`, `Create Blueprint Using This...`. You can also just create a new blueprint and add the Static Mesh in here. Make sure it's the root static mesh. Then, enable never distance cull on the static mesh (not the prop, the static mesh)
![convert_prop](images/convert_prop.png)
![distance_cull](images/distance_cull.png)

Then, there will be a few changes in the code. Search for the `live_event_manager_component` in Verse. Change the following:
![code_change_1](images/code_change_1.png)<br>

Scroll down a bit to the `StartEvent` and `EndEvent` functions, and change what is described in the image
![code_change_2](images/code_change_2.png)

Build Verse code, and locate the `live_event_manager_component` inside of the `EP_Game` instance. Place the prop you made down on the map, and update the reference to this new prop.
