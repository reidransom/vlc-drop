# VLC Drop.app

This is an OS X applescript droplet for opening multiple simultaneous instances of VLC.

[Download](http://media.reidransom.com/vlc-drop/VLC%20Drop.app.zip)

## Taken from

<http://wiki.videolan.org/How_to_play_multiple_instances_of_VLC>

On the Mac, running multiple instances of VLC is not supported out of the box.

As a workaround, you can create a Droplet that behaves as expected. Paste the code below into a new AppleScript Editor script and save it as an application. Launch the app to get a separate instance of VLC, or drop one or more files onto it.

    on run
        do shell script "open -n /Applications/VLC.app"
    end run

    on open theFiles
        repeat with theFile in theFiles
            do shell script "open -na /Applications/VLC.app " & quote & (POSIX path of theFile) & quote
        end repeat
    end open
