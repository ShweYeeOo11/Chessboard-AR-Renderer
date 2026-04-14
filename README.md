# Chessboard-AR-Renderer

## 1. Description
This program estimates the camera's real-time pose (position and orientation) using a calibrated camera and renders 3D AR objects (Cube and Pyramid) on a chessboard. 

## 2. Main Features
* **Camera Pose Estimation:** Calculates rotation and translation vectors using `cv2.solvePnP` and chessboard corners.
* **AR Visualization:** Renders a 3D Cube and a 3D Pyramid with solid shading and lighting effects.
* **Result Recording:** Automatically processes the input video and saves the AR-enhanced result as an MP4 file.

## 3. Technical Implementation

### 1. Camera Pose Estimation
The system identifies 2D chessboard corners using `cv2.findChessboardCorners`. These points are correlated with 3D world coordinates. The camera's rotation and translation vectors are then estimated using the Perspective-n-Point (PnP) algorithm via `cv2.solvePnP`.

### 2. 3D Object Construction
* **Sky Blue Cube:** Defined by 8 vertices and 6 polygonal faces. Each face is filled using `cv2.fillPoly` with varying shades of blue to simulate lighting.
* **Pink Pyramid:** Defined by a square base and an apex point. The triangular walls are rendered with gradient pink tones.

## 4. How to Use
1. Place your calibrated camera result file `calibration_result.npz` in the project folder.
2. Run the script: `python Camera_pose_AR.py`.
3. The output will be saved as `output_result.mp4`.

## 4. Demo Results

Below is the demonstration of the AR system. The 3D objects are rendered dynamically on the chessboard as the camera pose changes.

![AR Demo](ar_demo.gif)
