# ros2_wheeltec_n100_imu

ROS2 driver pkg for wheeltec N100 IMU module.


### install
```
mkdir -p /ros2_ws/src
cd /ros2_ws/src
git clone git@github.com:RoverRobotics-forks/serial-ros2.git #install ros2_serail
git clone git@github.com:NDHANA94/ros2_wheeltec_n100_imu.git

```
### run

* defaut run:
default serial port: `/dev/ttyACM0`
default serial baudrate: `921600`
```
ros2 run wheeltecN100_imu imu_node 
```

* run with custom params:
```
ros2 run wheeltecN100_imu imu_node --ros-args -p serial_port:="/dev/ttyACM0" -p serial_baud:=921600
```

    | parmeter | data type | default value |
    | --- | --- | --- |
    | debug | bool | false |
    |serial_port | string |  "/dev/ttyACM0" |
    |serial_baud | int | 921600 |
    |serial_timeout | int | 20 |
    | device_type |int | 1 |
    | frist_sn | bool | false |
    | imu_topic | string | "imu" |
    | imu_frame imu | string | "imu" |
    | mag_pose_2d_topic | string |"magnetic_pose_2d" |
    | imu_trueEast_topic | string | "imu_trueEast"|
    | mag_topic | string | "magnetic_field" |
    | yaw_offset | double | -2.094 |
    | mag_offset_x | double | 0.0 |
    | mag_offset_y | double | 0.0 |
    | mag_offset_z | double | 0.0 |
    | imu_mag_covVec | vector<double> | {0.01, 0.01, 0.01}|
    | imu_gyro_covVec | vector<double> |  {0.01, 0.01, 0.01} |
    | imu_accel_covVec | vector<double> |  {0.05, 0.05, 0.05} |

-----------------------------------------------------------------------------------

The code is based on [ROS1 fdilink imu driver](https://github.com/sbgisen/fdilink_ahrs)
