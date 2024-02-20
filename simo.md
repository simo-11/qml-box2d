# Summary of changes

## cmake

### policies in CMakeLists.txt
```
qt_policy(
	SET QTP0001 NEW
)
cmake_policy(
	SET CMP0071 NEW
)

```

### building
```
> cmake "-DCMAKE_PREFIX_PATH=C:\Qt\6.6.2\msvc2019_64" -S ..
```

# Running examples
```
C:\Users\simon\github\qml-box2d\build [master ≡]> bin\Debug\box2qml-examples.exe
qrc:/accelerometer/accelerometer.qml:3:1: module "QtSensors" is not installed
qrc:/accelerometer/accelerometer.qml:3:1: module "QtSensors" is not installed
qrc:/cannon/main.qml:4:1: module "QtMultimedia" is not installed
```
