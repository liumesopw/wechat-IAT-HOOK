# wechat-IAT-HOOK
个人微信号接口,获取微信号接口,个人微信号查询器,微信号查手机号接口,微信号状态查询接口,微信号调查个人信息,个人微信号接口 官方文档
      7. 3. 5 IAT HOOK 介绍在前面的内容中提到这样一个问题，IMAGE_IMPORT_DESCRIPTORGE_THUNK_DATA 结构体，第一个为导入名字表（INT),第二个为导入地址表（IAT).两个结构体在磁盘文件中时是没有差别的，但是当PE文件被装载内存后，FirstThunk字段指向的IMAGE_THUNK_DATA的值会被 Windows进行填充。该值为一个RVA,该RVA加上映像基址后，虚拟地址就保存了真正的导入函数的入口地址。在这个描述中知道，要对IAT进行HOOK大概有3个步骤，第一步是获得要HOOK 函数的地址，第二步是找到该函数所保存的IAT中的地址，最后一步是把IAT中的地址修改为HOOK函数的地址。这样就完成了IAT HOOK.也许这样的描述不是很清楚，下面就来举例说明。比如要在IAT中HOOK系统模块 kernel32.dll中的ReadFile(函数，第一步是获得ReadFile()函数的地址，第二步是找到ReadFile()所保存的IAT地址，最后一步是把IAT中的ReadFile0函数的地址修改为HOOK函数的地址。这样是不是就明白了？下面通过一个实例来介绍IATHOOK的具体过程和步骤。中有两个IMA
      ![image](https://user-images.githubusercontent.com/96330669/196107002-bfcc2132-c6ef-4955-b547-0e330d8f7f3f.png)
上次对Explorer.exe 进程的CreateProcessW()函数进行了 Inline Hook,的CreateFileWO函数进行IAT HOOK.对CreateFileWO函数进行HOOK后主要是管控记事本要打开的文件是否允许被打开，下面一步一步地来完成代码。先建立一个DLL文件，然后定义好 DLL 文件的主函数，ProcessIATO函数，在DLL被进程加载的时候，让DLL文件去调用HookNotePadProcestIATD函数。代码如下：BOOL APIENTRY D11Main ( HANDLE hModule,DWORD ul reason_for_call,LPVOID 1pReserved这次对记事本进程并定义一个HookNotePad
）
switch ( ul_reason_for_call )
7. 3. 6 IAT HOOK 实例上次对 Explorer.exe进程的CreateProcessWO函数进行了的CreateFileWO函数进行IAT HOOK.对CreateFileWO函数进行HOOK后主要是管控记事本要打开的文件是否允许被打开，下面一步一步地来完成代码。先建立一个DLL 文件，然后定义好DLL 文件的主函数，并定义一个HookNotepadProcessIATO函数，在DLL被进程加载的时候，让DLL 文件去调用HookNotePadProcesslATO函数。代码如下：BOOL APIENTRY D11Main (HANDLE hModule,DWORD ul_reason_for_call,LPVOID 1pReserved）Inline Hook,这次对记事本进程
switch (ul_reason_for_call)
 个人微信
目前已经实现了很多有趣的功能，运行稳定，比如：发各种消息，
接收各种消息，群管，下载文件，加好友，检测僵尸粉，朋友圈等等功能，
可提供接口，方便各种语言二次开发，欢迎技术交流，Q：2645542961
，请勿用于商业用途。

![cd50023e8432f4da526b26abaf3bcd3](https://user-images.githubusercontent.com/96330669/196107140-4f5f9d5e-658d-4c4d-b742-7c83077f613a.jpg)


企业微信：
目前已经实现了大部分功能，运行稳定，比如：发各种消息，
接收各种消息，外部群内部群管理，下载文件，加好友等等功能，
可提供接口，方便各种语言二次开发，欢迎技术交流。

