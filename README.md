# rosbot3_description

Model files for the ROSbot3 robot.

## Tips and Tricks

When modifying the robot model it may be useful to be able to manually convert the Xacro file to URDF and from there to SDF. Assuming you are working from inside the `rosbot3_simulation` workspace, first set up the workspace and `cd` into the package's `urdf/` folder:

    ./scripts/make.sh --symlink-install
    source ./scripts/setup.bash
    cd src/rosbot3_description/urdf

Then use the commands below to generate the URDF and SDF files in sequence:

    xacro rosbot3.xacro > rosbot3.urdf
    gz sdf -p rosbot3.urdf > rosbot3.sdf
