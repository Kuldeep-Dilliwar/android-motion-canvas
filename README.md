# How to run motion-canvas on native Termux?
## Here is how to:
```
pkg update -y && pkg upgrade -y && pkg install -y nodejs ffmpeg && npm create @motion-canvas@latest my-animation -- --template=2d && cd my-animation && npm install && sed -i "1i // Termux override\nif (require('os').platform() === 'android') {\n  module.exports = { path: '/data/data/com.termux/files/usr/bin/ffmpeg', version: 'system', url: 'https://ffmpeg.org/' };\n  return;\n}" node_modules/@ffmpeg-installer/ffmpeg/index.js && sed -i "1i // Termux override\nif (require('os').platform() === 'android') {\n  module.exports = { path: '/data/data/com.termux/files/usr/bin/ffprobe', version: 'system', url: 'https://ffmpeg.org/ffprobe.html' };\n  return;\n}" node_modules/@ffprobe-installer/ffprobe/index.js && npm start
```
