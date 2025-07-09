# BOT3
A Vex V5RC 2025-2026 Pushback robot

![Pros](https://pros.cs.purdue.edu/_static/img/pros-tux.png){width=50}

written in PROS-4 C++

## Project layout
```
/
┣━ /firmware              # Pros Firmware
┣━ /Include               # Header Files
┃   ┣━ auton.hpp          #
┃   ┣━ autonSelector.hpp  #
┃   ┣━ globals.hpp        #
┃   ┣━ pid.hpp            #
┃   ┗━ tlem.hpp           #
┣━ /src                   # C++ code
┃   ┣━ auton.cpp          # Autonomous Sequences
┃   ┣━ autonSelector.cpp  # Autonomous Selector
┃   ┣━ globals.cpp        # Shared data
┃   ┣━ main.cpp           # Main code
┃   ┣━ pid.cpp            # PID controller
┃   ┗━ tlem.cpp           # Telemetry and debugging functions
┣━ .gitignore             # Git Ignore
┗━ Other misc files for pros
```
### External Libs
- [LemLib](https://lemlib.readthedocs.io/en/stable/download.html)
- [Maelstrom](https://github.com/Lunar-Eclipse255/maelstrom)

### Code
#### Globals Namespace
|      Public      |             var             |   Port   |             use             |
|:----------------:| --------------------------- | -------- | --------------------------- |
| :material-check: | `master`                    | 21*      | primary controller          |
|                  | `horizontal_encoder`        | H?       | Odometry Tracking Wheel     |
| :material-check: | `imu`                       | 14       | Odometry                    |
| :material-check: | `left_motor_group`          | 2,3,16   | Left Drive Motors           |
| :material-check: | `right_motor_group`         | 11,12,13 | Right Drive Motors          |
|                  | `horizontal_tracking_wheel` | H?       | Odometry Tracking Wheel     |
|                  | `drivetrain`                |          | Drivetrain                  |
|                  | `sensors`                   |          | Odometry                    |
|                  | `lateral_controller`        |          | Drivetrain PID              |
|                  | `angular_controller`        |          | Drivetrain PID              |
| :material-check: | `chassis`                   |          | Chassis                     |
| :material-check: | `startPose`                 |          | Autonomous default position |
| :material-check: | `intake`                    | 4,5      | Intake Motors               |
| :material-check: | `hood`                      | 5        | Hood Motor                  |

!!! bug "Ports Used multiple times"
    fix hood/intake ports

#### Main Code
|       Func       |             use             |
| ---------------- | --------------------------- |
| `initialize`     | init screens and logging    |
| `autonomous`     | starts selected autonomous  |
| `opcontrol`      | Driver Control              |