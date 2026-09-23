# Changelog

All changes affecting the node behaviour are tracked here.

## Unreleased

- Added a `publish_interval_ms` launch argument to `launch/camera.launch.py` —
  minimum interval between consecutive image publications in milliseconds
  (0 = publish every frame). Usage:
  `ros2 launch camera_ros camera.launch.py publish_interval_ms:=100`.

- Added the dynamic parameter `publish_interval_ms` — minimum interval between
  consecutive image publications on `~/image_raw` and `~/image_raw/compressed`
  in milliseconds (0 = publish every frame). Frames arriving earlier than the
  configured interval are discarded: images are not prepared or published and
  the buffer is returned to the camera (src/CameraNode.cpp).