
# godot-dockerfile
A dockerfile with 3.1.1 version of godot. Installed on Ubuntu so the editor can be displayed.

## Examples of uses

### Running the editor with your game

In the `docker-compose.yml`file.

    edit-game:
	    image : darcemontv/godot-dockerfile:latest
	    volumes:
	      - './yourgodotprojectfolder:/build/src'
	      - '/tmp/.X11-unix:/tmp/.X11-unix'
	    environment:
	      - DISPLAY=$DISPLAY
	    command: godot -e --path /build/src

### Export your game
Don't forget to add the export preset in the file `export_presets.cfg` of godot (can be done in the godot editor).
#### Example for linux export
In the `docker-compose.yml`file.

    build-game-linux:
	    image : barichello/godot-ci:3.1.1
	    volumes:
	      - './yourgodotprojectfolder:/build/src'
	      - './yourexportfolder:/build/output'
	    environment:
	      - /bin/bash
	    command: godot --export 'Linux/X11' /build/output/astralys --path /build/src
