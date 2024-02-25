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
qml-box2d\build> cmake "-DCMAKE_PREFIX_PATH=C:\Qt\6.6.2\msvc2019_64" -S ..
```

## sources
 - box2dplugin.h - commented Q_OBJECT away as it caused unsatisfied symbol error on link
 - cannon/main.qml - remove versio from import QtMultimedia

# Running examples

Add correct Qt bin dir to path
```
$env:Path+=';c:\qt\6.6.2\msvc2019_64\bin'
```

## On command line
```
C:\Users\simon\github\qml-box2d\build [master ≡]> bin\Debug\box2qml-examples.exe
```
## In visual studio

```
qml-box2d\build> start qmlbox2d.sln
```
  - set box2qml-examples as startup project
  - set Debugging/Working Directory to $(SolutionDir)
  - sample stacktrace
```
	qmlbox2d.dll!b2RevoluteJoint::SolveVelocityConstraints(const b2SolverData & data) Line 185	C++
 	qmlbox2d.dll!b2Island::Solve(b2Profile * profile, const b2TimeStep & step, const b2Vec2 & gravity, bool allowSleep) Line 265	C++
 	qmlbox2d.dll!b2World::Solve(const b2TimeStep & step) Line 532	C++
 	qmlbox2d.dll!b2World::Step(float dt, int velocityIterations, int positionIterations) Line 939	C++
 	qmlbox2d.dll!Box2DWorld::step() Line 304	C++
 	qmlbox2d.dll!StepDriver::updateCurrentTime(int __formal) Line 51	C++
 	Qt6Cored.dll!QAbstractAnimation::setCurrentTime(int msecs) Line 1341	C++
 	Qt6Cored.dll!QAnimationTimer::updateAnimationsTime(__int64 delta) Line 576	C++
 	Qt6Cored.dll!QUnifiedTimer::updateAnimationTimers() Line 289	C++
 	Qt6Cored.dll!QAnimationDriver::advanceAnimation() Line 756	C++
 	Qt6Quickd.dll!QSGDefaultAnimationDriver::advance() Line 214	C++
 	Qt6Quickd.dll!QSGThreadedRenderLoop::polishAndSync(QSGThreadedRenderLoop::Window * w, bool inExpose) Line 1641	C++
 	Qt6Quickd.dll!QSGThreadedRenderLoop::handleUpdateRequest(QQuickWindow * window) Line 1376	C++
 	Qt6Quickd.dll!QQuickWindow::event(QEvent * event) Line 1545	C++
 	Qt6Widgetsd.dll!QApplicationPrivate::notify_helper(QObject * receiver, QEvent * e) Line 3296	C++
 	Qt6Widgetsd.dll!QApplication::notify(QObject * receiver, QEvent * e) Line 3247	C++
 	Qt6Cored.dll!QCoreApplication::notifyInternal2(QObject * receiver, QEvent * event) Line 1121	C++
 	Qt6Cored.dll!QCoreApplication::sendEvent(QObject * receiver, QEvent * event) Line 1540	C++
 	Qt6Guid.dll!QPlatformWindow::deliverUpdateRequest() Line 784	C++
 	Qt6Guid.dll!QPlatformWindow::windowEvent(QEvent * event) Line 455	C++
 	qwindowsd.dll!QWindowsWindow::windowEvent(QEvent * event) Line 2702	C++
 	Qt6Guid.dll!QGuiApplicationPrivate::sendQWindowEventToQPlatformWindow(QWindow * window, QEvent * event) Line 2055	C++
 	Qt6Widgetsd.dll!QApplication::notify(QObject * receiver, QEvent * e) Line 2598	C++
 	Qt6Cored.dll!QCoreApplication::notifyInternal2(QObject * receiver, QEvent * event) Line 1121	C++
 	Qt6Cored.dll!QCoreApplication::sendEvent(QObject * receiver, QEvent * event) Line 1540	C++
 	Qt6Cored.dll!QEventDispatcherWin32Private::sendTimerEvent(int timerId) Line 404	C++
 	Qt6Cored.dll!QEventDispatcherWin32::event(QEvent * e) Line 886	C++
 	Qt6Widgetsd.dll!QApplicationPrivate::notify_helper(QObject * receiver, QEvent * e) Line 3296	C++
 	Qt6Widgetsd.dll!QApplication::notify(QObject * receiver, QEvent * e) Line 3247	C++
 	Qt6Cored.dll!QCoreApplication::notifyInternal2(QObject * receiver, QEvent * event) Line 1121	C++
 	Qt6Cored.dll!QCoreApplication::sendEvent(QObject * receiver, QEvent * event) Line 1540	C++
 	Qt6Cored.dll!QCoreApplicationPrivate::sendPostedEvents(QObject * receiver, int event_type, QThreadData * data) Line 1901	C++
 	Qt6Cored.dll!QEventDispatcherWin32::sendPostedEvents() Line 901	C++
 	Qt6Guid.dll!QWindowsGuiEventDispatcher::sendPostedEvents() Line 44	C++
 	Qt6Cored.dll!QEventDispatcherWin32::processEvents(QFlags<enum QEventLoop::ProcessEventsFlag> flags) Line 471	C++
 	Qt6Guid.dll!QWindowsGuiEventDispatcher::processEvents(QFlags<enum QEventLoop::ProcessEventsFlag> flags) Line 36	C++
 	Qt6Cored.dll!QEventLoop::processEvents(QFlags<enum QEventLoop::ProcessEventsFlag> flags) Line 101	C++
 	Qt6Cored.dll!QEventLoop::exec(QFlags<enum QEventLoop::ProcessEventsFlag> flags) Line 182	C++
 	Qt6Cored.dll!QCoreApplication::exec() Line 1442	C++
 	Qt6Guid.dll!QGuiApplication::exec() Line 1926	C++
 	Qt6Widgetsd.dll!QApplication::exec() Line 2575	C++
 	box2qml-examples.exe!main(int argc, char * * argv) Line 18	C++
```



