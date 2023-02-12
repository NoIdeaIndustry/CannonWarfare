<div align="center">

# Cannon Warfare
</div>

**Cannon Warfare is a scientific project made within two weeks based on projectiles real time trajectory simulations.** <br/>
**This project displays 2D cannonball's trajectory depending on many variables with many statistics shown.**<br/>

## Preview
<img src="Showcase/idle.gif" style="width:800px;"/>

<img src="Showcase/shooting.gif" style="width:800px;"/>

## Features

- Real-time simulated cannonballs with:
    - a position
    - a velocity
    - an acceleration
    - display of trajectory
    - a precise timer to get the exact air time
    - bouncing simulation applied upon hitting the ground (see ```CannonBall.cpp > ApplyBouncingLogic()```)
    - drag applied at each frame to acceleration using the following formula: <br>
        <img src="Showcase/drag.png"/> <br>
        See [this link](https://www.physagreg.fr/mecanique-12-chute-frottements.php) for more info. <br>
        See ```CannonBall.cpp > ComputeDrag()```.

- Cannonball trajectory prediction with near-perfect accuracy (see ```Cannon.cpp > UpdateTrajectory()```)
    - Without drag, this is done instantly by solving the cannonball's movement equation to get its landing position and velocity, then the trajectory is drawn as a bezier curve.
    - With drag, the cannonball's movement equation becomes very hard to solve without iteration. Our solutions were either to use euler's method, or to simulate a cannonball and save its position at regular intervals. We went for the second one since both use iteration and euler's method would grant similar results in similar time frames so it felt like overkill.

- The cannonball's muzzle velocity is computed using the following formula: <br>
    <img src="Showcase/muzzleVelocity.png"/> <br>
    See <a href="https://www.arc.id.au/CannonBallistics.html">this link</a> for more info. <br>
    See ```Cannon.cpp > ComputeMuzzleVelocity()```.

- Cannon recoil is applied using the following formula: <br>
    <img src="Showcase/recoilVelocity.png"> <br>
    See [this link](https://www.omnicalculator.com/physics/recoil-energy) for more info. <br>
    See ```Cannon.cpp > ApplyRecoil()```.

- Cannonball collisions are applied using the following formula: <br>
    <img src="Showcase/collision.png"> <br>
    See ```CannonBall.cpp > CheckCollisions()```.

- Tweakable variables:
    - Powder charge
    - Barrel length
    - Projectile radius
    - Projectile mass
    - Cannon height
    - Cannon rotation

- Toggleable parameters:
    - Apply recoil
    - Apply drag
    - Apply collisions
    - Show predicted trajectory
    - Show predicted measurements
    - Show cannonball trajectories
    
    # Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.<br/>
Please make sure to update tests as appropriate.<br/>
