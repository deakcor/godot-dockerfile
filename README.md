
# godot-dockerfile
A dockerfile with 3.1.1 version of godot. Installed on Ubuntu so the editor can be displayed.

## Example of uses

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
