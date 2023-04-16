# github.com/syncthing/syncthing

Alternative to Google Drive.

Run the following bash script to sync directory `/media/tungdt/WindowsData/syncthing`.
If the directory is on a different disk partition to Linux file system:
should mount on boot the sync directory's partition (edit `/etc/fstab` or use GUI `gnome-disk-utility`).

The scripts were created from [README-Docker.md](README-Docker.md).

````bash
docker run -dit --restart=always --network=host \
    -v /media/tungdt/WindowsData/syncthing:/var/syncthing \
    -e STGUIADDRESS=127.0.0.1:8384 \
    --name syncthing syncthing/syncthing:1.23.3

# -p 8384:8384 -p 22000:22000/tcp -p 22000:22000/udp -p 21027:21027/udp 
````

GUI and API listening on [127.0.0.1:8384](http://127.0.0.1:8384/)

Go to the GUI, __ignore__ "Default Folder" called `Sync`,
click button `Add Folder`, set ` Folder ID` to the name of folder that we need to sync.
