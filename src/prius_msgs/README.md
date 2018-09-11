# prius usual msg

## cmd.msg
   float64 gasPedal   # range from -1 to 1
   float64 brakePedal # range from -1 to 1 
   float64 handBrake  # range from -1 to 1
   float64 handWheel  # range from -7.85 to 7.85 (in radians) from right to left defined in ChongPriusPlugin.cc , handwheel, the handwheel angle
                      # max_Steer = 0.6458, wheel, the tire angle
                      # steeringRatio is tire/handwheel

## imu.msg
   geometry_msgs/Quaternion orientation
   geometry_msgs/Vector3 angular_velocity
   geometry_msgs/Vector3 linear_acceleration

## gps.msg
   float64 lat
   float64 lon
   float64 altitude
   float64 velocity_east
   float64 velocity_north
   float64 velocity_up

## status.msg
   float64 handWheelAngle
   float64 flSteeringAngle
   float64 frSteeringAngle
   float64 chassisVelocity
