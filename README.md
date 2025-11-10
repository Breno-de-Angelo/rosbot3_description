# rosbot3_description

Model files for the ROSbot3 robot.

## Model description

The robot description is based on the [official manual](https://husarion.com/manuals/rosbot/). Some values were not provided in the schematics. For those situations, external materials were consulted when possible, but if no source was available, then it was picked a reasonable value.

The description is split into two parts:

- [base.xacro](./urdf/base.xacro) defines the `chassis` and `wheels` of the robot.
- [sensors.xacro](./urdf/sensors.xacro) defines the robot sensors placed on the top surface (`camera` and `lidar`).

The file [rosbot3.xacro](./urdf/rosbot3.xacro) is used to aggregate both definitions and used as the final robot description.

## Tips and Tricks

When modifying the robot model it may be useful to be able to manually convert the Xacro file to URDF and from there to SDF. Assuming you are working from inside the `rosbot3_simulation` workspace, first set up the workspace and `cd` into the package's `urdf/` folder:

    ./scripts/make.sh --symlink-install
    source ./scripts/setup.bash
    cd src/rosbot3_description/urdf

Then use the commands below to generate the URDF and SDF files in sequence:

    xacro rosbot3.xacro > rosbot3.urdf
    gz sdf -p rosbot3.urdf > rosbot3.sdf
