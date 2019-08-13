# audio-volume
A ROS package for tracking and changing audio volume level via a ROS node `/volume` which interfaces with `amixer`

The audio control to use with amixer defaults to 'Master' and can be set with the rosparam `/volume/control`.
The latched topic `/volume/percent` contains the current percentage audio volume.
The topic `/volume/percentChange` can be published to, changing the volume level by the given percentage, e.g. `-100` to mute audio, or `50` to increase the audio volume by 50% (up to a maximum of 100% of course).
