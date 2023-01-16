# 3D-scanner
Build 3D models with Revopoint Mini 3D scanner

## Preparation
1. 3D scanner
2. Laptop with RevoScan
3. 2D axis turning table

![Scan a human statue in a dark ambient condition](https://github.com/yuemeanshappy/3D-scanner/blob/main/gif/dark_env.gif)
![Scan a rose in a light ambient condition](https://github.com/yuemeanshappy/3D-scanner/blob/main/gif/light_env.gif)

## Procedure
1. Connect the 3D scanner and the turning table with a laptop
2. Light condition setting:
  - `Ambiment environment`: totally dark or general room light condition does not have significant differences
  - `Backgroud color`: black and white background both work
3. Turning Table setting:
  - `rounds`: 3 rounds
  - `angles`: 0 degree, 10 degree and -10 degree
4. 3D scanner setting
  - `scan mode`: feature (marker mode is more suitable for flat surface or simple geometric shape)
  - `color`: yes (turn RGB camera on or off both work)
  - `turning table`: yes
5. Scan setting
  - `light condition`: set auto mode in the first round scanning, and then can manually adjust the light to maximize the scanning area in the target object.
6. Start scanning!!
  - fuse cloud points
  - build mesh
  - store the 3D model

## Important tricks
**1. lose track when scanning?**
- Stop rotation and stay at the original place for a few seconds to let the scanner return to track
- But if you are using the 2D axis turning table, click "stop" button would let the truning table stop completely without turning around again. Therefore, once you stop before the end of third round, you have to 1) manually rotate the turning table or 2) ajust the angle of the scanner and then restart from the very beginning.

**2. have orange areas after fuse cloud points?**\
Orange areas means lack of enough points (enough information). There are two approaches. The ideas of them is to scan more areas based on the original points.
- The first approach is keeping the scanner at the same position, manually move the object to fill the holes, then fuse the cloud points again. (This approach works better in dark background where you can catch the object by hand hidding behind the dark cloth.) 
- The second approach is adjusing the height of the scanner slowly to make sure the scanning is on track, then rotate the turning table manually.

**3. how to fix the object on the table?"**
- Use foam and needle (but foam will be treated as one part of your 3D model if you put the foam on the turning table)
- Use tape
- Use playing dough\
Make sure the object is at the center of the turning table.

## References
1. Revopoint User Manual https://support.revopoint3d.com/hc/en-us/categories/6984257114523-MINI
2. Revopoint Forum https://forum.revopoint3d.com/c/tutorials/21
