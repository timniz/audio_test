# audio_test

ROS2 test package for getting the data from the `/audio` topic, transcribing it into text (Estonian) and publishing it to the topic `/recognized_text` <br/>

Used with the following packages (`!make sure that you follow the guidelines for respeaker_ros at first!`): <br/>
https://github.com/SemuBot/respeaker_ros.git <br/>
https://github.com/ros-drivers/audio_common.git (ros2 branch) <br/>

On your system: <br/>
* `pip install SpeechRecognition`

In your ROS2 workspace: <br/>

* `cd /src` 
* `git clone https://github.com/SemuBot/audio_test.git`
* `git clone https://github.com/SemuBot/respeaker_ros.git`
* `git clone -b ros2 https://github.com/ros-drivers/audio_common.git`
* `cd ..`
* `rosdep install -i --from-path src --rosdistro humble -y` 
* `colcon build --packages-select audio_test respeaker_ros audio_common_msgs audio_play audio_capture` <br/>

Then, run in separate terminals (Starting with `source install/local_setup.bash` in each terminal): <br/> 

* `ros2 run respeaker_ros respeaker_node` 
* `ros2 run audio_test audio_transcriber` <br/>

