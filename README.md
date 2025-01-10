# Expo Camera Initialization Race Condition

This repository demonstrates a common error when using the Expo Camera API: attempting to access camera features before the API is fully initialized.  This can result in unexpected behavior or crashes. The solution involves properly handling the asynchronous nature of the camera's initialization.

## Problem

The Expo Camera API is asynchronous; it takes time to initialize before it's ready for use.  If you try to access camera features (e.g., taking a picture, changing camera type) immediately after mounting the component, you may encounter errors because the camera isn't yet initialized.

## Solution

The solution is to ensure your code waits for the camera to fully initialize before interacting with it. This can be achieved by using the `status` prop of the Camera component and only executing camera-related actions once the status indicates readiness (`ready`).

## How to reproduce

1. Clone this repo.
2. Run `npm install`.
3. Run `expo start`.
4. Observe the console for errors (in `cameraBug.js`).
5. Uncomment the solution in `cameraSolution.js` to see the corrected behavior.
