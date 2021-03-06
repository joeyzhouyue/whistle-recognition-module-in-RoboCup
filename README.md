# whistle-recognition-module-in-RoboCup
C++ code for some part of the whistle recognition module in RoboCup Nao robot.

The video of a testing result can be found under this link at YouTube: https://youtu.be/Tuf5Kt_FAFE

In this whistle recognition module, a cross-correlation between the reference signal and the sound signal is continuously being recorded. Then the cross-correlation is divided by the auto-correlation of the reference signal, which gives a percentage number. This value can be understood as a similarity index or correspondence index, which indicates how similar the recorded signal and the reference signal are. If this value exceeds some predefined value, called threshold, the robot(s) consider the recorded signal as a whistle. Then the robot status will be changed from SET to PLAY. However, the whistle_detection module can only be activated at the state "SET". In the config. file, you can tune the threshold value at your will. As a reference, we had the threshold value around 4% during the tournament in Eindhoven 2016. 

The behavior module is also slightly adapted, so that the robot gets penalized when it considers a noise from environment as a whistle and begins to PLAY. This robot is set then to PENALIZED. After some time (usually 15 seconds), the penalized robot will be set to PLAY to play normally as other robots. The modified behavior module is not included in this repository.


