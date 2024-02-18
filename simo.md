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

