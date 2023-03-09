# aubo_caps   API总览：

本文将详细介绍各类API的功能，读者可以通过浏览本文对`aubo_scope API`系统有个整体把握，在`aubo_caps`开发过程中能更好的使用这些API。

## **域API**

**系统API**

1. **系统API** (systemApi)

   > - `getmajorVersion()`: 获取软件的主要版本。
   >
   > - ` getMinVersion()`: 获取软件的最小版本。
   >
   > - `getBugfixVersion()`: 获取软件的bug修复版本 。
   >
   > - `getBuildNumber()`: 获取软件的内部版本号。
   >
   > - `getLocale()`: 获取本地语言。
   >
   > - `getlocale for Programming Language()`: 获取系统设置语言。
   >
   > - `getUnitType()`: 获取系统当前的单位类型。
   >
   > - `getSerialNumber()`: 获取机器人的序列号。
   >
   > - `isRealRobot()`: 如果控制的是真实物理机器人返回true，如果是模拟的返回false
   >
   > 获取最大位置的关节弧度。
   >
   > - `getJointMaxPositions()`: 获取关节最大位置。
   > - `getJointMinPositions()`: 获取关节最小位置。
   > - `getJointDefaultVelocity()`: 获取关节默认速度。
   > - `getJointDefaultAcceleration()`: 获取关节默认的加速度。
   > - `getJointMaxVelocity()`: 获取关节最大速度。
   > - `getJointMaxAcceleration()`: 获取关节最大加速度。
   > - `getTcpDefaultVelocity()`: 获取tcp的默认速度。
   > - `getTcpDefaultAcceleration()`: 获取tcp的默认加速度。
   > - `getTcpMaxVelocity()`: 获取tcp的最大速度。
   > - `getTcpMaxAcceleration()`: 获取tcp的最大加速度。
   > - `getTcpMaxDistance()`: 获取Tcp的最远距离。
   > - `getMaxPayloadMass()`: 获取最大有效载荷的质量。
   > - `getMaxPayloadDistance()`: 获取最大有效载荷的距离。
   > - `getHomeDefaultPosition()`: 获取home默认位置。
   > - `getHomePackagePosition()`: 获取home paceage位置。
   > - `getRobotDhParams()`:获取机器人Dh参数（连杆）。
   > - `getMaxPower()`: 获取最大力。
   > - `getMinPower()`: 获取最小力。
   > - `getMaxMomentum()`: 获取最大动量。
   > - `getMinMomentum()`: 获取最小动量。
   > - `getMaxStoppingTime()`: 获取最大的stop时间。
   > - `getMinStoppingTime()`: 获取最小的stop时间。
   > - `getMaxStoppingDistance()`: 获取最大的stop 距离。
   > - `getMinStoppingDistance()`: 获取最小的stop距离。
   > - `getMaxToolForce()`: 获取工具的最大力。
   > - `getMinToolForce()`: 获取工具的最小力。
   > - `getMaxElbowSpeed()`: 获取最大的肘部速度。
   > - `getMaxElbowForce()`: 获取最大的肘部力量。
   > - `getMinElbowForce()`: 获取最小的肘部力量。
   > - `getStandardDigitalInputConfigure()`: 获取标准的数字输入配置。
   > - `getToolDigitalInputConfigure()`: 获取Tool的数字输入配置。
   > - `getConfigureableDigitalInputConfigure()`: 获取configureable的数字输入配置。
   > - `getStandardDigitaloutputConfigure()`: 获取标准的数字输出配置。
   > - `getToolDigitaloutputConfigure()`: 获取Tool的数字输出配置。
   > - `getConfigureableDigitaloutputConfigure()`: 获取configureable的数字输出配置。
   > - `getStandardAnalogoutputConfigure()`: 获取标准的模拟输出配置。
   > - `getToolAnalogoutputConfigure()`: 获取Tool的模拟输出配置。
   > - `getStandardAnaloginputConfigure()`: 获取标准的模拟输入配置。
   > - `getToolAnaloginputConfigure()`: 获取Tool的模拟输入配置。
   > - `getStaticSafetyInputConfigure()`: 获取安全系统配置的输入值。
   > - `getStaticSafetyoutputConfigure()`: 获取安全系统配置的输出值。
   > - `getStaticLinkInputConfigure()`:获取Link输入配置。
   > - `getStaticLinkOutputConfigure()`:获取Link输出配置。

2. **应用程序API**(applicationApi)

   > - `getIoModel()`: 获取机器人IO数据。
   > - `getFeatureModel()`: 获取机器人环境坐标系配置信息。
   > - `getTcpModel()`: 获取机器人工具中心点的所有配置。
   > - `getPayloadModel()`: 获取机器人末端执行器的有效负载配置信息。
   > - `getVariableModel()`: 获取所有的程序变量和表达式信息。
   > - `getValueFactory()`: 创建复杂的变量以及表达式。
   > - `getDeviceManager()`: 提供设备管理器接口，访问所有已注册的设备。

3. **用户界面API**(userInterfaceApi)

   > `getUserInteraction()`: 提供请求输入功能的接口，这些接口如下所示：
   >
   > ```
   > getUserDefinedRobotPosition():  要求用户去定义机器人位姿,并返回该位姿
   > 
   > getRobotThumb(): 获取机器人缩略图；
   > 
   > getKeyboardInputFactory()：创建各类键盘
   > 
   > requestUserToMoveJoint(): 根据用户要求位姿去移动关节
   > ```

## **安装API**

安装API 是对应用程序API的扩展，因此首先它具有应用程序API 的所有功能，其次扩展的API功能如下：

> - `getFunctionModel()`: 为`aubo_scopet`提供脚本函数。
> - `getTcpContributionModel()`: 创建、配置、获取、更新TCP。
> - `getFeatureContributionModel()`: 创建、配置、获取、更新Feature。
> - `getPayloadContributionModel()`: 创建、配置、获取、更新Payload。

## **程序API**

`Program API`是服务于程序域中的程序节点，而程序节点可能需要获取有关机器人的系统信息（例如序列号，软件版本）这涉及到`System API`的访问，因此`Program API`中提供了对`System API`访问的接口`getSystemApi()`程序节点还可能需要与用户交互的功能，这涉及到`UserInterface API`的访问，因此`Program API`中提供了对`UserInterface API`访问的接口`getUserInterfaceApi()`。而`Program API`还提供了仅在程序域中才有意义的API,这些API功能如下：

> `getProgramModel()`：在这个接口中有以下功能可使用。
>
> ```
> getProgramNodeFactory();   //创建各类程序节点（包括已经注册的插件提供的程序节点）
> getTreeNode(ProgramNodeContribution *root); //在程序树中添加、删除、移动子节点
> ```
>
> `getWaypointModel()`：创建、配置路点信息。
>
> `getUndoRedoManager()`: 记录程序节点可撤销更改。

