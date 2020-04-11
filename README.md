# steamvr-room-setup-unrestricted

A modded version of the SteamVR Room Setup to remove the size limitations for a minimal play space that exist for absolutely no reason!

___

## How to install

Have you got a VR head set only to find you don't have enough room for room scale? Then this is the random dll to download from a GitHub repo for you!

Download and place ``Assembly-CSharp.dll`` in ``C:\Program Files (x86)\Steam\steamapps\common\SteamVR\tools\steamvr_room_setup\win64\steamvr_room_setup_Data\Managed`` and overwrite it.

Now, your SteamVR Room Setup will not arbitrarily complain that you can't use that $1000+ VR head set the way you want to anymore.

Enjoy! :)

____

## Alternative: Do it yourself

Don't trust me or want to know how to do it yourself if this is broken now?

Download dnSpy and open the original ``Assembly-CSharp.dll`` in ``C:\Program Files (x86)\Steam\steamapps\common\SteamVR\tools\steamvr_room_setup\win64\steamvr_room_setup_Data\Managed``.

Navigate to the ``GlobalManagerRS2D`` class like so:

![image](https://user-images.githubusercontent.com/21316711/79039052-77b83480-7bd6-11ea-8aff-c88a1fb2f2a2.png)

and find these two values ``MinPlayVolumeSizeLarger`` and ``MinPlayVolumeSizeSmaller``, right click on them and select Edit Method (this will let you edit their default values in the constructor):

![image](https://user-images.githubusercontent.com/21316711/79039080-ab935a00-7bd6-11ea-8787-53d10f2474c3.png)

Change their values to something more sane, and not incredibly annoying such as 0.01f:

![image](https://user-images.githubusercontent.com/21316711/79039086-b9e17600-7bd6-11ea-8081-969430edc7c2.png)

Hit compile, then select the module like so:

![image](https://user-images.githubusercontent.com/21316711/79039094-cb2a8280-7bd6-11ea-844a-10d9f97b9059.png)

Then save it:

![image](https://user-images.githubusercontent.com/21316711/79039101-d4b3ea80-7bd6-11ea-971a-8bb6cd5d5123.png)

Hit ``OK`` and you're done!

![image](https://user-images.githubusercontent.com/21316711/79039111-e5646080-7bd6-11ea-82dc-1cbf2387ee1e.png)

Congratulations, you just did it yourself. You can now play roomscale with a chaperone without it complaining your room is 0.1m too small to do so.

## Have fun!
