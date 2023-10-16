# random_movies

cat Takeoff-West-NoLease.json | mosquitto_pub -h mqtt -t 'drone/drone0/mission-spec' -s


cat Takeoff-B-Midway-NoLease.json | mosquitto_pub -h mqtt -t 'drone/drone1/mission-spec' -s


cat Takeoff-C-East-NoLease.json | mosquitto_pub -h mqtt -t 'drone/drone2/mission-spec' -s
