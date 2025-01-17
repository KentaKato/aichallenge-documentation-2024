# Simulator

## Overview

This page describes the specifications of the simulator used in the AI Challenge.

The simulator is based on the open-source autonomous driving simulator "[AWSIM](https://github.com/tier4/AWSIM)" developed for Autoware.

## Vehicle (Go-Kart)

The vehicle conforms to the specifications of the [EGO Vehicle](https://tier4.github.io/AWSIM/Components/Vehicle/EgoVehicle/) in AWSIM and is designed with specifications close to an actual go-kart.

![vehicle-appearance](./images/vehicle-appearance.png)

### Parameters

The following table summarizes the vehicle parameters.

| **Item**               | **Value** |
| ---------------------- | --------- |
| Vehicle Weight         | 160 kg    |
| Length                 | 200 cm    |
| Width                  | 145 cm    |
| Front Wheel Diameter   | 24 cm     |
| Front Wheel Width      | 13 cm     |
| Front Wheel Tread      | 93 cm     |
| Rear Wheel Diameter    | 24 cm     |
| Rear Wheel Width       | 18 cm     |
| Rear Wheel Tread       | 112 cm    |
| Maximum Steering Angle | 80°       |
| Maximum Acceleration   | 3.2 m/s^2 |

#### Vehicle Component

The following table summarizes the settings of the Vehicle component. For detailed information of the setting items, see [this manual](https://tier4.github.io/AWSIM/Components/Vehicle/EgoVehicle/#vehicle-script).

| **Item**                            | **Value** |
| ----------------------------------- | --------- |
| **Vehicle Settings**                |           |
| Use Inertia                         | Off       |
| **Physics Settings (experimental)** |           |
| Sleep Velocity Threshold            | 0.02      |
| Sleep Time Threshold                | 0         |
| Skidding Cancel Rate                | 0.236     |
| **Input Settings**                  |           |
| Max Steer Angle Input               | 80        |
| Max Acceleration Input              | 3.2       |

#### Rigidbody Component

The following table summarizes the settings of the Rigidbody component. For more information, see [this manual](https://tier4.github.io/AWSIM/Components/Vehicle/EgoVehicle/#rigidbody).

| **Item**     | **Value** |
| ------------ | --------- |
| Mass         | 160       |
| Drag         | 0         |
| Angular Drag | 0         |

### CoM Position

CoM (Center of Mass) is the mass center of the vehicle Rigidbody. The CoM position is set at the center of the vehicle and at the height of the wheel axles.

![side-view-of-com](./images/side-view-of-com.png)

![top-view-of-com](./images/top-view-of-com.png)

### Vehicle Collider

Vehicle collider is used to detect collision between the vehicle and other objects or checkpoints. The vehicle collider is created based on the mesh of the vehicle object.

![body-collider](./images/body-collider.png)

### Wheel Colliders

The vehicle has a total of four wheel colliders - one for each wheel, simulating the vehicle on a four-wheel model, rather than a kinematic bicycle model.

![wheel-collider](./images/wheel-collider.png)

The Wheel Collider is set as follows. For more details on wheel colliders, please refer to [this manual](https://tier4.github.io/AWSIM/Components/Vehicle/EgoVehicle/#wheels-colliders).

| **Item**              | **Value** |
| --------------------- | --------- |
| Mass                  | 1         |
| Radius                | 0.12      |
| Wheel Damping Rate    | 0.25      |
| Suspension Distance   | 0.001     |
| **Suspension Spring** |           |
| Spring (N/m)          | 35000     |
| Damper (N\*s/m)       | 3500      |
| Target Position       | 0.01      |

### Sensor Configuration

TODO
