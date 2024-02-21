# Summary of changes to use with Qt 6.6

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

## sources
 - box2dplugin.h - commented Q_OBJECT away as it caused unsatisfied symbol error on link
 - cannon/main.qml - remove versio from import QtMultimedia

# Running examples
```
C:\Users\simon\github\qml-box2d\build [master ≡]> bin\Debug\box2qml-examples.exe
```
