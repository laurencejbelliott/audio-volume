# audio-volume
A ROS package for tracking and changing audio volume level via a ROS node `/volume` which interfaces with `amixer` from [alsa-utils](https://github.com/alsa-project/alsa-utils).

To install, clone this repo into your catkin workspace, and then from the root of this workspace, enter the command `catkin build volume`. Then to run the volume node, source your workspace by running `source devel/setup.bash` in the workspace root, and lastly, enter the command `rosrun volume volume`.

The audio control to use with amixer defaults to 'Master' and can be set with the rosparam `/volume/control`.
The latched topic `/volume/percent` contains the current percentage audio volume.

The topic `/volume/percentSet` can be published to, setting the volume level at the given percentage, e.g. `0` to mute audio, or `50` to the audio volume to 50%.

The topic `/volume/percentChange` can be published to, changing the volume level by the given percentage, e.g. `-100` to mute audio, or `50` to increase the audio volume by 50% (up to a maximum of 100% of course).
