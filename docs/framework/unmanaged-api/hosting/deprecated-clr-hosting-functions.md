---
title: "Устаревшие функции размещения CLR"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 985425ad44003f5971b21f107fad322f2123f6ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="deprecated-clr-hosting-functions"></a>Устаревшие функции размещения CLR
В этом разделе описываются неуправляемые глобальные статические функции, которые используются в более ранних версиях API размещения.  
  
 За исключением функций инфраструктуры (`_Cor*` функции), которые используются только платформой .NET Framework, эти функции являются устаревшими в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="activation-functions"></a>Активация функции  
 [Функция ClrCreateManagedInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 Не рекомендуется. Создает экземпляр указанного управляемого типа.  
  
 [Функция CoInitializeCor](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 Является устаревшей. Чтобы инициализировать общеязыковой среды выполнения (CLR), используйте [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) или [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).  
  
 [Функция CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 Не рекомендуется. Обеспечивает загрузку ядро выполнения среды CLR в процесс. Используйте [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) метод вместо него.  
  
 [Функция CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 Не рекомендуется. Загружает общеязыковой среды выполнения (CLR) в процесс, используя сведения, хранящиеся в XML-файл.  
  
 [Функция CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 Не рекомендуется. Позволяет неуправляемым узлам загрузить среду CLR в процесс.  
  
 [Функция CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 Не рекомендуется. Загружает среду CLR в процесс, используя сведения о версии, считываемые из файла XML.  
  
 [Функция CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 Не рекомендуется. Позволяет неуправляемым узлам загрузить среду CLR в процессе и можно задавать флаги для задания поведения среды CLR.  
  
 [Функция CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 Не рекомендуется. Позволяет поставщикам услуг размещения для загрузки заданной версии среды CLR в процесс.  
  
 [Функция GetCORRequiredVersion](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 Не рекомендуется. Получает необходимые номер версии среды CLR.  
  
 [Функция GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 Не рекомендуется. Возвращает каталог установки среды CLR, которая загружается в процесс.  
  
 [Функция GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 Не рекомендуется. Получает адрес указанной функции, экспортированные из последней установленной версии среды CLR.  
  
 [Функция GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 Не рекомендуется. Получает сведения о версии и каталоге о среде CLR, запрошенный приложением.  
  
## <a name="clr-version-functions"></a>Версия функции CLR  
 В этом разделе возвращают версию среды CLR; они не активировать среды CLR.  
  
 [Функция GetCORVersion](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 Не рекомендуется. Возвращает номер версии среды CLR, которая выполняется в текущем процессе.  
  
 [Функция GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 Не рекомендуется. Возвращает сведения о версии среды CLR для указанного файла, используя указанный буфер.  
  
 [Функция GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 Не рекомендуется. Получает номер версии среды CLR, запрашиваемой указанным приложением. Если эта версия не установлена, Получает самую последнюю версию, установленную перед запрошенной версии.  
  
 [Функция GetRequestedRuntimeVersionForCLSID](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 Не рекомендуется. Возвращает соответствующие сведения о версии среды CLR для класса с заданным идентификатором CLSID.  
  
 [Функция GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 Не рекомендуется. Получает номер версии среды CLR, связанный с заданным дескриптором процесса.  
  
 [Функция LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 Не рекомендуется. Предоставляет узлу возможность определить, какие версии среды CLR, которая будет использоваться в процессе до явной инициализации среды CLR.  
  
## <a name="hosting-functions"></a>Функции размещения  
 [Функция CallFunctionShim](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 Не рекомендуется. Выполняется вызов функции с указанным именем и параметрами в указанной библиотеке.  
  
 [Функция CoEEShutDownCOM](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 Не рекомендуется. Выгружает сборку COM из процесса.  
  
 [Функция CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 Не рекомендуется. Завершает работу текущего неуправляемого процесса.  
  
 [Функция CorLaunchApplication](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 Не рекомендуется. Запускает приложение по указанному сетевому пути, используя заданные манифесты и другие данные приложения.  
  
 [Функция CorMarkThreadInThreadPool](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 Не рекомендуется. Помечает текущий выполняемый поток из пула потоков для выполнения управляемого кода. Начиная с .NET Framework версии 2.0, эта функция не делает ничего. Он не является обязательным и может быть удален из кода.  
  
 [Функция CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 Является устаревшей. Среда CLR не может быть выгружен из процесса.  
  
 [Функция CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 Является устаревшей.  
  
 [Функция CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 Не рекомендуется. Создает [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) объекта на основе указанной версии данных.  
  
 [Функция CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 Не рекомендуется. Создает [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) объекта.  
  
 [Функция DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 Не рекомендуется. Уничтожает [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) объекта.  
  
 [Указатель функции FExecuteInAppDomainCallback](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которую среда CLR вызывает на выполнение управляемого кода.  
  
 [Указатель функции FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая вызывается средой CLR для уведомления узла инициализации либо начала или завершения.  
  
 [Функция GetCLRIdentityManager](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 Не рекомендуется. Возвращает указатель на интерфейс, который позволяет среде CLR для управления удостоверениями.  
  
 [Функция LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 Не рекомендуется. Загружает заданную версию библиотеки DLL, .NET Framework.  
  
 [Функция LoadStringRC](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 Не рекомендуется. Преобразовывает значение HRESULT в сообщение об ошибке с помощью языка и региональных параметров по умолчанию текущего потока.  
  
 [Функция LoadStringRCEx](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 Не рекомендуется. Преобразовывает значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.  
  
 [Указатель функции LPOVERLAPPED_COMPLETION_ROUTINE](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая уведомляет основное приложение перекрывающегося (то есть асинхронные) завершения ввода-вывода на устройстве.  
  
 [Указатель функции LPTHREAD_START_ROUTINE](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая уведомляет основное приложение начала выполнения потока.  
  
 [Функция RunDll32ShimW](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 Не рекомендуется. Выполняет указанную команду.  
  
 [Указатель функции WAITORTIMERCALLBACK](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая уведомляет узел, что дескриптор ожидания был сигнал или истекло время ожидания.  
  
## <a name="infrastructure-functions"></a>Функции инфраструктуры  
 Функции, в этом разделе предназначены для использования только в .NET Framework.  
  
 [Функция _CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 Инициализирует среду CLR, размещает управляемую точку входа в заголовке среды CLR сборки DLL и начинает выполнение.  
  
 [Функция _CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 Инициализирует среду CLR, размещает управляемую точку входа в заголовке среды CLR исполняемой сборки и начинает выполнение.  
  
 [Функция _CorExeMain2](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 Выполняет точка входа в заданный код, размещенный в памяти. Эта функция вызывается загрузчиком операционной системы.  
  
 [Функция _CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 Уведомляет загрузчика при выгрузке образов управляемых модулей.  
  
 [Функция _CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 Проверяет образы управляемого модуля и уведомляет загрузчик операционной системы после их загрузки.  
  
## <a name="see-also"></a>См. также  
 [Глобальные статические функции размещения платформы .NET Framework 4](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md) 
