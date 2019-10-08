# MaterialComponentsDemo
Demo application demostrating the crash happening because of FAB animation. Scroll the scrollable area couple of times in order to reproduce the crash. I think crash is happening during the circular reveal on FAB. 

**Description:** Here is the Demo app https://github.com/ashraf-patel/MaterialComponentsDemo, as described in this [link to the gif](https://github.com/ashraf-patel/MaterialComponentsDemo/blob/master/gifs/30dpCorners.gif) you can reproduce the crash. 

**Expected behavior:** It should not crash.

**Source code:** 

Here is the problem, making  cornerSizeTopRight and cornerSizeBottomLeft to 30dp is causing the crash. 
![Crash](/gifs/30dpCorners.gif)
```
<style name="ShapeAppearance.Sunflower.FAB" parent="ShapeAppearance.MaterialComponents">
        <item name="cornerFamily">rounded</item>
        <item name="cornerSizeTopLeft">0dp</item>
        <item name="cornerSizeTopRight">30dp</item>
        <item name="cornerSizeBottomRight">0dp</item>
        <item name="cornerSizeBottomLeft">30dp</item>
</style>
```
Below code works ![Crash](/gifs/0dpCorners.gif)
```
<style name="ShapeAppearance.Sunflower.FAB" parent="ShapeAppearance.MaterialComponents">
        <item name="cornerFamily">rounded</item>
        <item name="cornerSizeTopLeft">0dp</item>
        <item name="cornerSizeTopRight">0dp</item>
        <item name="cornerSizeBottomRight">0dp</item>
        <item name="cornerSizeBottomLeft">0dp</item>
</style>
``` 
https://github.com/ashraf-patel/MaterialComponentsDemo is the Demo app.

**Android API version:** OS: 8.0

**Material Library version:** 1.1.0-beta01

**Device:** Device: Pixel 2 XL Emulator

**StackOverflow:** https://stackoverflow.com/questions/58225921/shapeappearance-in-material-component-floatingactionbutton-causes-a-crash

**Issue in original repository:** https://github.com/android/sunflower/issues/519
