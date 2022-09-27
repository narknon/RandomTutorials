# How to port KOF XIV and other old entry moveset files to XV:

## Resources needed:

UModel or FModel to extract the uassets: https://www.gildor.org/en/projects/umodel; https://fmodel.app/

Latest UAssetGUI: https://github.com/atenfyr/UAssetGUI/releases

A Hex Editor like HxD or 010: https://mh-nexus.de/en/hxd/; https://www.sweetscape.com/010editor/

UnrealPak or Similar: http://fluffyquack.com/tools/unrealpak.rar

That's it.


## Steps

Extract the character's action files from XV, e.g., in KOFXV\Content\GameContent\Character\000KYO\Action

Open the uasset for the file you wish to port with uassetgui.  Open the equivalent file from the old game in the hex editor.  Add 4 null bytes to the start of the old game file and save.

```00 00 00 00```

![image](https://user-images.githubusercontent.com/73571427/192653772-946260d1-994a-4220-8385-898cd7be714d.png)



Go to the export section of the uassetgui window and expand the nodes.

![image](https://user-images.githubusercontent.com/73571427/192653799-d0abf4a8-1a36-4ab1-8a2d-afbc7c50fe92.png)



Go to the "Extra Data" section and press import at the top of the hex data.

![image](https://user-images.githubusercontent.com/73571427/192653838-ce775728-40a3-4f56-b8f0-11a0c8c06971.png)


In the open file dialog change the file type to any and navigate to your edited old game file and select it.

![image](https://user-images.githubusercontent.com/73571427/192653877-e24275cd-769e-4279-b05a-6ddb4a4056a9.png)


Press View -> Recalculate Nodes or Shift+F5.  

![image](https://user-images.githubusercontent.com/73571427/192653894-8354424b-9aa5-49c2-94f0-70dfabbc62f3.png)

If the export type has a (0) next to the name, you're done.  Go to File -> Save and pak the file.

![image](https://user-images.githubusercontent.com/73571427/192653922-b1bd3063-c4cf-47a8-949b-b6362111c04d.png)


If the export has a (1), this is the data buffer size.  Check the new size of the Extra Data after recalculating nodes, subtract 4, and enter that number inside of this property.

![image](https://user-images.githubusercontent.com/73571427/192654010-49868931-a587-4bc3-a768-54092034bb0c.png)

Afterwards, save and pak.

