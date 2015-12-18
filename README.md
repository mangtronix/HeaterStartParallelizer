# HeaterStartParallelizer
Cura plugin to start your bed and extruder heater in parallel. The extruder will start heating when the bed temperature reaches a specified offset from the target bed temperature. This allows for a timing so that both extruder and bed reaches their target temperatures at roughly the same time instead of the default behavior of waiting for the bed to reach temperature before starting the extruder heating.

Usage
==========
Specify a temperature offset from the target bed temperature that will start the extruder heater. You'll want to experiment and find an offset so that both will reach printing temps at about the same time (like the example image below) with your typical print temperatures. If the target bed temp is 65C and the offset is set to 10C, then the extruder heater will start heating at 55C.

![](https://raw.githubusercontent.com/mosh1/HeaterStartParallelizer/master/Example.jpg)
Installation
==========
Add to Cura as a plugin:

1. Open Cura
2. Go to the Plugins tab
3. Click on "Open plugin location"
4. Drag HeaterStartParallelizer.py into plugin location (or copy to ~/.cura/plugins for OSX)
5. Restart Cura

Use with Simplify3D:

1. Open Simplify3D
2. Click Processes -> Edit Process Settings
3. Click Show Advanced (if not already showing)
4. Go to Scripts
5. Enter the following into Post Processing -> Additional terminal commands for post processing
```python {script path}/HeaterStartParallelizer.py "[output_filepath]" {temperature offset}```

  For example, on my system (OSX) with a 15 degree temperature offset:

  ```python /Users/mangtronix/Dropbox/src/HeaterStartParallelizer/HeaterStartParallelizer.py "[output_filepath]" 15```

