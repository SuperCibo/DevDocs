## 基础功能层
| PALib中大多组件功能为Model层，只提供功能不关心显示。要少用继承多用组合的方式在自己的业务脚本去显示、控制和扩展它 |   : 1 |   : 2 |   : 3 |   : 4 |   : 5 |
| --- | --- | --- | --- | --- | --- |
|    |    |    |    |    |    |
| 功能名称 | 游戏图例1 | 游戏图例2 | 功能/脚本路径 | 备注 | 平台 |
| 【角色背包】，可以存在多个背包，内置了默认存入和取出动画 | =DISPIMG("ID\_F469E002FAB6472B89F3FB4909143D2A",1) | =DISPIMG("ID\_3F2D818FF6354CFD871FA5A61B196A42",1) | Inventory/Game/Backpack.cs | 使用方法：挂在GameObject上即可，需要几个背包就挂几个脚本 | Unity/Cocos |
| 【血条】，支持大血量堆叠功能。如果想要传统单管血条的功能，把TotalHealth和MaxHealthOfStack设置成相同的值即可 | =DISPIMG("ID\_2EB71DB3F6804C9C967587FF3F7DC172",1) | =DISPIMG("ID\_5ECB21244A2F4FAD975B7E7C8D7B4A38",1) | Inventory/Game/HealthBar.cs | 使用方法：挂在GameObject上即可 | Unity/Cocos |
| 【进度区域】，一般用于存入相应资源进行进度展示和解锁用途 | =DISPIMG("ID\_4CC1AA0F7FCD483D989B648CC7348D5D",1) | =DISPIMG("ID\_EAC007337BF943B0B81F89A9D87FE231",1) | Inventory/Game/ProgressArea.cs | 使用方法：挂在GameObject上即可，可以配合AreaTrigger使用 | Unity/Cocos |
| 【物品堆放】，把物体整齐码放，支持存入和取出，内置了默认的存取动画 | =DISPIMG("ID\_CF9EEB90785548688E3F0D10541A7CC8",1) | =DISPIMG("ID\_8008BFF7661E4D248F9D98D0B094D4A0",1) | Inventory/Game/StockArea.cs | 使用方法：挂在GameObject上即可，可以配合AreaTrigger使用 | Unity/Cocos |
| 【指引线】灵活，高性能，只需一次drawcall | =DISPIMG("ID\_B3C496ACA1F74A949C6F806C6E2CA681",1) | =DISPIMG("ID\_DD983E79F3CC46B8B608E17D807284C1",1) | Inventory/GuideLine/GuideLine.prefab\n | 使用方法：prefab拖到场景中，设置好发射源和目的地即可 | Unity/Cocos |
| 【指引箭头】，会一直指向目标，内置了一个默认离近行为 | =DISPIMG("ID\_BAEF1E856E164F70A26FC157A389EE91",1) | =DISPIMG("ID\_255DC598348A4E298DE271A18AA806CA",1) | Inventory/Game/GuideArrow.cs | 使用方法：在自己的箭头物体上挂载此脚本设置好发射源和指向目标即可\n内置的默认离近行为：3d版本箭头会自动跳到目标上面并做动画，2d版本箭头直接消失 | Unity/Cocos |
| 【离屏指示器】，会提示屏幕外的目标，支持多个目标 | =DISPIMG("ID\_0FBEE79697AD47AD90B09F45C8A09291",1) | =DISPIMG("ID\_43AF94872451464DBFA7EE7ADC15051A",1) | Inventory/OffScreenIndcator | 使用方法：\n第一步：将UIOffScreenIndicatorController.prefab拖到画布中\n第二步：在目标物体（例如boss）挂载OffScreenTarget脚本（也可动态挂载）即可\n其他设置：\n如果不喜欢预置的指示器样式，则可以自己创建一个指示器的UI prefab，并挂载UIOffScreenIndicator脚本，并把这个prefab拖到UIOffScreenIndicatorController中pfbArrowIndicator属性中即可 | Unity/Cocos |
| 【虚拟摇杆】，拖到画布上就可以直接使用 | =DISPIMG("ID\_52C0106778EC47149127CC4430A7F0CE",1) |    | Inventory/Joystick/FloatingJoystick.prefab\nInventory/Joystick/FixedJoystick.prefab\nInventory/Joystick/DynamicJoystick.prefab\nInventory/Joystick/VariableJoystick.prefab | 使用方法：prefab拖到场景中即可 | Unity/Cocos |
|    |    |    |    |    |    |
| 【敌人生成器】 |    |    | FuncComp/EnemySpawner.cs | 一个泛型敌人生成器，移除敌人和获取全部敌人时间复杂度均为O(1)\n使用方法：在EnemySpawner.cs文件中有使用说明 | Unity/Cocos |
|    |    |    |    |    |    |
| 【路径构建器】，常用于曲线路径的构建 |    |    | 3rdParty/PathCreator | 该目录下有教学文档 | Unity |
|    |    |    |    |    |    |
| 【对象池】，支持泛型，小巧，简单、灵活、高性能、带有错误检测 |    |    | Framework/Pool/TMLPoolManager.cs\nFramework/Pool/TMLPoolAutoCreator.cs | 使用方法：打开TMLPoolManager.cs，文件里有示例，或者使用自动创建方法\n自动创建：Unity菜单栏->PALib->Pooling->Create PoolAutoCreator\ncocos版本需要自己挂载TMLPoolAutoCreator脚本到空物体上 | Unity/Cocos |
|    |    |    |    |    |    |
| 【数学类】 |    |    | Framework/TMLMath.cs | 其中包含有些实用的代数和几何函数，例如，判断点是否在扇形区域\n判断是否在视锥体内，是否在多边形内，快速距离比较…… | Unity/Cocos |
|    |    |    |    |    |    |
| 【工具类】 |    |    | Framework/TMLUtils.cs | 包含经常用到的第三类定时器，随机等诸多实用工具函数 | Unity/Cocos |
|    |    |    |    |    |    |
| 【角色控制】 |    |    | FuncComp/RigidbodyMovementController.cs\nFuncComp/Rigidbody2DMovementController.cs\nFuncComp/TransformMovementController.cs\nFuncComp/Transform2DMovementController.cs | 挂在主角上，在自己的业务脚本中把虚拟摇杆的Direction属性读出来每帧赋给此类的InputDirection属性，即可实现摇杆对角色的控制 | Unity/Cocos |
|    |    |    |    |    |    |
| 【可拖拽物体】 |    |    | FuncComp/DraggableObject.cs | 把脚本挂在有Collider组件物体上即可，就可以实现鼠标对物体的拖拽功能 | Unity/Cocos |
|    |    |    |    |    |    |
| 【自由相机】，地编同学在出包测试场景可以使用 |    |    | FuncComp/FreeFlyCamera.cs | 用于在游戏运行时对场景实现漫游功能，使用方法：挂在主相机上即可 | Unity |
|    |    |    |    |    |    |
| 【第三人称相机】 |    |    | FuncComp/ThirdPersonCamera.cs | 用于跟踪目标的第三人称相机，挂在相机上并设置好目标（一般为角色）即可 | Unity/Cocos |
|    |    |    |    |    |    |
| 【广告牌】 |    |    | FuncComp/Billboard.cs | 用于实现物体的广告牌三种模式的朝向，一般用于3D UI，例如血条，气泡图标等。挂在物体上即可 | Unity/Cocos |
|    |    |    |    |    |    |
| 【有限状态机】 |    |    | Framework/FiniteStateMachine.cs | 可以用在任何需要状态机的物体上，例如角色，敌人，NPC等等 | Unity/Cocos |
|    |    |    |    |    |    |
| 【多语言】 |    |    | Inventory/I18N | TMP文本挂I18NText.cs，图片显示挂I18NImage.cs，多语言内容在\nInspector中配置即可。如果需要运行时多语言则可以在PALib菜单栏创建PALib->I18N->Create Runtime，创建完成之后在Inspector中配置即可，注意，I18NRuntime全局只能有一个\ncocos版本需要自己挂载I18NRuntime脚本到空物体上 | Unity/Cocos |
|    |    |    |    |    |    |
| 【音频管理器】，提供集中播放与相同剪辑最大播放数量上限的功能 |    |    | Inventory/AudioManager.cs | 使用方法：Unity菜单栏->PALib->Audio->Create Audio Manager\ncocos版本需要自己挂载AudioManager脚本到空物体上 | Unity/Cocos |
|    |    |    |    |    |    |
| 【寻路】 |    |    | Inventory/PathFinding | Unity使用方法：Unity菜单栏->PALib->Create\n选中创建出来的AStarSolver，在右侧即可创建地图，创建出自己想要的\n地图后点击序列化即可。\n示例教程：Inventory/PathFinding/Example\nCocos使用方法：如果是2D项目把AStarGridBased.prefab放到画布中，如果是3D项目把AStarGridBased3D放到场景中 | Unity/Cocos |
|    |    |    |    |    |    |
| 【动态避障（RVO）】 |    |    | Inventory/RVO2 | 1、将RVOSolver.ts挂载到场景空物体上并配置好参数\n2、将RVOAgent.ts挂载到需要避障的物体上，例如僵尸，敌人等\n3、如果需要定义障碍物则在障碍物物体上挂载RVOObstacle.ts脚本并设置好障碍物参数\n4、在业务脚本中实时更新RVOAgent的velocity属性即可，表示你想要物体往哪里移动 | Cocos |
|    |    |    |    |    |    |
| 【消息广播】 |    |    | Messenger.cs | 使用方法：在脚本文件中有示例 | Unity/Cocos |
|    |    |    |    |    |    |
| 【Luna管理器】 |    |    | LunaManager.cs | 主要使用里边跳转商城方法：LunaManager.OpenStoreURL() | Unity/Cocos |
|    |    |    |    |    |    |
| 【Trigger系统】，不依赖物理引擎，可以稳定触发 |    |    | Inventory/Game/AreaTrigger.cs\nInventory/Game/AreaTriggerInteractor.cs | 推荐把AreaTriggerInteractor挂在角色身上 | Unity/Cocos |
|    |    |    |    |    |    |
| 【预制UI】 |    |    | Application/UI/\*.prefab | 包含常用的预置UI，例如虚拟摇杆引导动画。将prefab直接拖到画布中即可 | Unity/Cocos |
|    |    |    |    |    |    |
| 【任意轴排序】，主要用于sprite的按照Y轴进行先后绘制 |    |    | Inventory/2DSorting/SortingGroup.ts | 针对2d游戏覆盖层级问题所开发，把要排序的物体放在统一节点下，在父节点挂载SortingGroup.ts即可，默认按Y轴排序 | Cocos |
|    |    |    |    |    |    |
| 【DoTween】，提供了常用tween方法 |    |    | 3rdParty/DoTween.ts | 使用方法：里边都是静态方法，直接在代码中按需调用即可 | Cocos |
|    |    |    |    |    |    |
| 【打点及商店跳转】 |    |    | Inventory/PBASDKController.ts | 使用方法（2选1）：\n传统模式：将Inventory/PBA/PBASDK.prefab拖到画布中\n高性能模式：直接将PBASDKController.ts挂载到canvas上，在属性检查器中取消勾选legacy\n\n任选其一之后在属性检查器中正确配置数据，在代码中调用PBASDKController.ins的方法在自己的业务中打点即可 | Cocos |

## 应用层
| 此层罗列了PALib的应用层，均在PALib/Application文件夹中，即拿即用 |   : 1 |   : 2 |   : 3 |   : 4 |   : 5 |   : 6 |
| --- | --- | --- | --- | --- | --- | --- |
|    |    |    |    |    |    |    |
| 功能名称 | 游戏类型 | Unity | Cocos | 预览 | 备注 | 作者 |
| 开场操作指南 | darkwar |    |    |    |    | 孙亚星 |
| 带有上限功能的背包 | darkwar |    | ObjectPoolBackpack.ts |    |    | 唐明江 |
| 门 | darkwar |    |    |    |    | 唐明江 |
| 墙 | darkwar |    |    |    |    | 唐明江 |
| 子弹 | darkwar |    |    |    |    | 唐明江 |
| 掉落物 | darkwar |    |    |    |    | 唐明江 |
| 血条 | darkwar |    |    |    | 使用PALib中Healthbar和Billboard进行组合 | 唐明江 |
| 解锁区域 | darkwar |    |    |    | 使用PALib中ProgressBar进行组合 | 唐明江 |
| 伤害数字 | darkwar |    |    |    |    | 唐明江 |
| 升级进度条 | darkwar |    |    |    | 使用PALib中ProgressBar进行组合 | 唐明江 |
| 开采物-树 | darkwar |    |    |    |    | 唐明江 |
| 开采物-矿石 | darkwar |    |    |    |    | 唐明江 |
| 开采物-田地 | darkwar |    |    |    |    | 唐明江 |
| Boss僵尸 | darkwar |    | DWZombieBehavior.ts |    |    | 曲天明 |
| 有攻击目标僵尸 | darkwar |    | DWZombieBehavior.ts |    |    | 曲天明 |
| 固定线路僵尸 | darkwar |    | DWZombieBehavior.ts |    |    | 曲天明 |
| 顾客NPC | darkwar |    |    |    |    | 曲天明 |
| 战士NPC | darkwar |    |    |    |    | 曲天明 |
| 哨塔NPC | darkwar |    |    |    |    | 曲天明 |
| 跟班NPC | darkwar |    |    |    |    | 曲天明 |
| 劳工NPC（开采、搬运） | darkwar |    |    |    |    | 曲天明 |
| 主角（按攻击行为拆分） | darkwar |    |    |    |    | 曲天明 |
| 可击打物 | lastz |    |    |    |    | 刘怀隆 |
| 可击打buff | lastz |    |    |    |    | 刘怀隆 |
| 道具 | lastz |    |    |    |    | 刘怀隆 |
| 角色控制 | lastz |    |    |    |    | 刘怀隆 |
| 子弹 | lastz |    |    |    |    | 刘怀隆 |
| LastZ僵尸 | lastz |    |    |    |    | 刘怀隆 |
| 堆叠血条 | lastz |    |    |    | 使用PALib中Healthbar和Billboard进行组合 | 刘怀隆 |
