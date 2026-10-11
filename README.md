## Feifan Huang

MSc Human and Biological Robotics, Imperial College London (2026).
BEng Mechatronic Engineering, China Agricultural University.

I work on robot motion control and embodied AI. What I try to get right is making
a claim checkable: a null control behind every success criterion, seeds held apart
for tuning, for model selection and for reporting, and the failures written down
next to the results rather than left out of them. Three of the four repositories
below contain a finding that is unflattering to the method I was building, which
is the point.

### Projects

**[mine-quadruped-nav](https://github.com/Bright-H123/mine-quadruped-nav)** —
ROS 2 Humble and Isaac Sim. An ANYmal reinforcement-learning locomotion policy
driving a real physics articulation from velocity commands to joint torques, with
Nav2, SLAM Toolbox and RTAB-Map on assembled DARPA SubT courses. Includes the
work of finding that a headline tracking error I had reported, 1.829 times the
commanded speed, was an artefact of my own measurement loop rather than the
checkpoint: `World.step(render=True)` advances physics by `rendering_dt`, so the
true elapsed simulation time was 7/4 of what the probe assumed. Corrected, the
policy tracks 1:1 and never needed calibration, and the same error had been
genuinely degrading the gait.

**[greenhouse-nav](https://github.com/Bright-H123/greenhouse-nav)** —
D* Lite with three local controllers compared on identical seeds: Regulated Pure
Pursuit, a CasADi nonlinear MPC, and TD3 both under the global plan and end to
end. D* + MPC finished 400 of 400 episodes; TD3 is 15 to 25% faster when it
succeeds and less reliable in every single condition. The density sweep in the
first version did not measure density at all, which the results gave away, and
the README explains why and what replaced it.

**[vla-occlusion](https://github.com/Bright-H123/vla-occlusion)** —
A MuJoCo benchmark asking whether a language-conditioned manipulation policy
actually uses the instruction, and whether it survives losing sight of the target.
Scripted expert 100/100, three null controls at 0/50, and an occluder measured to
change 93.8% of the frame and take every object's pixel count to zero. No policy
result is reported yet, because the baseline is still undertrained and a policy
that cannot do the task cannot be asked whether it reads the instruction.

**[ml-from-scratch](https://github.com/Bright-H123/ml-from-scratch)** —
Every algorithm from Andrew Ng's Machine Learning Specialization implemented in
NumPy and checked against scikit-learn or a closed-form result, 112 tests. No
TensorFlow; the neural-network weeks are NumPy.

### Also

Real-time control over CAN at 1 kHz, Simulink with Embedded Coder onto real-time
targets, ros2_control, KDL and OMPL, IMU attitude estimation, and multi-channel
signal synchronisation with automated quality control. Python and C++ on Linux.

Open to robotics and embodied-AI engineering roles, available immediately.
