---
layout: docs
title: AnimatedFloat Documentation
---
#### [.](./../../../../../../../../index) > [app](./../../../../../../../index) > [src](./../../../../../../index) > [main](./../../../../../index) > [java](./../../../../index) > [james](./../../../index) > [alarmio](./../../index) > [utils](./../index) > [anim](./index) > **AnimatedFloat.java**

# [AnimatedValue<Float>](https://github.com/fennifith/Alarmio/blob/master/app/src/main/java/james/alarmio/utils/anim/AnimatedFloat.java#L4)

**Type:** `public` `class` `AnimatedFloat` `extends`

The AnimatedFloat class animates a float, to a granularity of 
0.1f. That is, if the difference between the target and current 
value is less than 0.1, it will be ignored and the animation will 
be regarded as complete. 












## [nextVal](https://github.com/fennifith/Alarmio/blob/master/app/src/main/java/james/alarmio/utils/anim/AnimatedFloat.java#L16)

**Type:** `@Override` `public` `Float`

Get the next value about to be drawn, without setting 
the current value to it. 





|Parameter Name|Description|
|-----|-----|
|start|The time at which the animation started, in milliseconds.|
|duration|The duration, in milliseconds, that the animation should take.|


**Returned Value:**  The next value.  








