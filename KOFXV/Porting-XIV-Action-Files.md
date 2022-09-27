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


Go to the export section of the uassetgui window and expand the nodes.


Go to the "Extra Data" section and press import at the top of the hex data.


In the open file dialog change the file type to any and navigate to your edited old game file and select it.


Press View -> Recalculate Nodes or Shift+F5.  If the export type has a (0) next to the name, you're done.  Go to File -> Save and pak the file.


If the export has a (1), this is the data buffer size.  Check the new size of the Extra Data after recalculating nodes, subtract 4, and enter that number inside of this property.