# Design and Analysis of a Compliant Prosthetic Digit

B.Tech Mechanical Engineering capstone project focused on the **design and structural analysis of a compliant prosthetic finger** intended for additive manufacturing.

The project investigates replacing conventional mechanical finger joints with **flexure joints**, reducing the number of individual components and potential points of failure.

---

## Project Overview

- Designed a compliant prosthetic digit based on human finger kinematics.
- Developed the CAD model in **SolidWorks**.
- Designed the prototype for **FDM additive manufacturing using ABS**.
- Modelled the finger using compliant flexure joints.
- Studied the kinematics of the MCP, PIP and DIP joints.
- Performed structural simulations using **ANSYS**.
- Evaluated the design under axial and lateral loading.
- Considered the anisotropic material behaviour introduced by FDM manufacturing.

---

## Human Finger Anatomy

The mechanical model was developed by studying the anatomy and joint arrangement of the human finger.

<p align="center">
  <img src="img/anatomy_of_human_finger.jpeg" width="750">
</p>

---

## Kinematic Model

The finger was represented as a series of links corresponding to the proximal, middle and distal phalanges.

<p align="center">
  <img src="img/linkage_diagram.jpg" width="700">
</p>

The linkage was then simplified into a kinematic representation for analysing the motion of the finger.

<p align="center">
  <img src="img/finger_kinematic_linkage_diagram.jpeg" width="700">
</p>

The transformation between the individual links was formulated using a kinematic transformation matrix.

### Kinematic Transformation

$$
\def\U{\theta_{m}}
\def\V{\theta_{p}}
\def\W{\theta_{d}}
[T_{4}^{0}] =
\begin{bmatrix}
C_{(\U+\V+\W)} &
-S_{(\U+\V+\W)} &
L_{prp} + L_{dip} C_{(\U+\V)} + L_{dim} C_{\U}
\\
S_{(\U+\V+\W)} &
C_{(\U+\V+\W)} &
L_{dip} S_{(\U+\V)} + L_{dim} S_{\U}
\\
0 & 0 & 1
\end{bmatrix}
$$

---

## Material Model

The prototype was designed for fabrication using **FDM-printed ABS**.

Since FDM components exhibit direction-dependent mechanical properties, the material was modelled as anisotropic.

### Anisotropic Material Model

$$
\begin{bmatrix}
\epsilon_{xx} \\
\epsilon_{yy} \\
\epsilon_{zz} \\
\gamma_{xy} \\
\gamma_{yz} \\
\gamma_{zx}
\end{bmatrix}
=
\begin{bmatrix}
\frac{1}{E_x} &
-\frac{\nu_{xy}}{E_y} &
-\frac{\nu_{zx}}{E_z} &
0 & 0 & 0
\\
-\frac{\nu_{xy}}{E_x} &
\frac{1}{E_y} &
-\frac{\nu_{zy}}{E_z} &
0 & 0 & 0
\\
-\frac{\nu_{xz}}{E_x} &
-\frac{\nu_{yz}}{E_y} &
\frac{\nu_{1}}{E_z} &
0 & 0 & 0
\\
0 & 0 & 0 &
\frac{1}{2G_{yz}} &
0 & 0
\\
0 & 0 & 0 &
0 &
\frac{1}{2G_{xz}} &
0
\\
0 & 0 & 0 &
0 & 0 &
\frac{1}{2G_{xy}}
\end{bmatrix}
\begin{bmatrix}
\sigma_{xx} \\
\sigma_{yy} \\
\sigma_{zz} \\
\tau_{xy} \\
\tau_{yz} \\
\tau_{zx}
\end{bmatrix}
$$

---

## Compliant Finger Geometry

Conventional revolute joints were replaced with compliant flexure sections to create a finger that could be manufactured as a largely continuous component.

<p align="center">
  <img src="img/flexible_finger_geometry.PNG" width="750">
</p>

---

## Finite Element Model

The compliant finger was meshed and analysed using **ANSYS**.

<p align="center">
  <img src="img/flexi_finger_mesh.png" width="750">
</p>

Two primary loading conditions were investigated.

### Axial Loading

<p align="center">
  <img src="img/finger_axial_loading_fea.png" width="850">
</p>

### Lateral Loading

<p align="center">
  <img src="img/finger_lateral_loading_fea.png" width="850">
</p>

The analysis indicated that the design performs better under **axial loading**, while lateral loading presents greater limitations due to the shear behaviour of the printed structure.

---

## Tools & Methods

- SolidWorks
- ANSYS
- Finite Element Analysis
- FDM Additive Manufacturing
- Mechanical Design
- Compliant Mechanisms
- Finger Kinematics
- Anisotropic Material Modelling

---

## Project Report

The complete B.Tech capstone report containing the methodology, theoretical development, simulations and results is available here:

### [View Full Capstone Project Report](report/Capstone_Report.pdf)

---
