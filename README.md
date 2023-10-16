docker compose -f docker-compose.yml -f multi_drone.yml run dev bash
source /catkin_ws/devel/setup.bash


rosrun dr_onboard_autonomy state_machine.py _uav_name:=drone0 _mqtt_host:=mqtt _local_mqtt_host:=mqtt_local __ns:=uav0

rosrun dr_onboard_autonomy state_machine.py _uav_name:=drone1 _mqtt_host:=mqtt _local_mqtt_host:=mqtt_local __ns:=uav1

rosrun dr_onboard_autonomy state_machine.py _uav_name:=drone2 _mqtt_host:=mqtt _local_mqtt_host:=mqtt_local __ns:=uav2


cat Takeoff-West-NoLease.json | mosquitto_pub -h mqtt -t 'drone/drone0/mission-spec' -s
cat Takeoff-B-Midway-NoLease.json | mosquitto_pub -h mqtt -t 'drone/drone1/mission-spec' -s
cat Takeoff-C-East-NoLease.json | mosquitto_pub -h mqtt -t 'drone/drone2/mission-spec' -s
