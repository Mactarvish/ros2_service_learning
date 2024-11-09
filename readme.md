首先编译ros2消息，然后使用消息构建服务


```
colcon build  --event-handlers console_direct+  --packages-select add_two_ints_srv
source install/setup.zsh
colcon build  --event-handlers console_direct+  --packages-select add_two_ints_node
```

调用服务

`ros2 service call /add_two_ints add_two_ints_srv/srv/AddTwoInts "{a: 5, b: 7}"`