# tuw_shape_array
## shape_server_node
### Parameters
* __json__: 
  * json filename with the shape_array to open
* __frame_id__: 
  * can be used to replace the frame id
  * default: *false*
* __pub_interval__: 
  * publishing interval in seconds. If 0 or less, the graph is published once. [sec]
  * default: *10.0*
### Publisher
* __shapes__
  * Shapes from the json file
  * Type: *tuw_object_msgs::msg::ShapeArray*
### Subscriber
* __get__
  * Returns the shape_array on request
  * Type: *tuw_object_msgs::srv::GetShapeArray*
* __publish__
  * Request to publish the shape_array
  * Type: *std_srvs::srv::Trigger*

## Demo
RViz
```
ros2 run rviz2 rviz2 -d ./ws01/src/tuw_shape_array/config/cave.rviz
ros2 run tuw_shape_array shape_server_node --ros-args -p pub_interval:=1 -r shapes:=shape_server/cave -r get:=shape_server/get -r publish:=shape_server/publish -p json:=./ws01/src/tuw_shape_array/config/cave.json
```

<div align="center">
<img src="res/rviz_shape_array.png" alt="shape array msgs with lines" width="400px" /><br>
<table style="width:400px;"><td>
tuw_shape_array_msg visualized with the tuw_rviz plugins in RViz2
</td></table> 
</div>