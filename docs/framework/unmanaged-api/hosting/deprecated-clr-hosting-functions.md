---
title: Устаревшие функции размещения CLR
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 62773ce526b1f21c57ab85a106708589fcf92f6f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138276"
---
# <a name="deprecated-clr-hosting-functions"></a>Устаревшие функции размещения CLR
В этом разделе описаны неуправляемые глобальные статические функции, которые использовались в предыдущих версиях API размещения.  
  
 За исключением функций инфраструктуры (`_Cor*` функций), которые используются только .NET Framework, эти функции являются устаревшими в .NET Framework 4.  
  
## <a name="activation-functions"></a>Функции активации  
 [Функция ClrCreateManagedInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 Не рекомендуется. Создает экземпляр указанного управляемого типа.  
  
 [Функция CoInitializeCor](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 Является устаревшей. Чтобы инициализировать среду CLR, используйте либо [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) , либо [корбиндтокуррентрунтиме](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).  
  
 [Функция CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 Не рекомендуется. Гарантирует, что подсистема выполнения среды CLR загружается в процесс. Используйте вместо этого метод [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) .  
  
 [Функция CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 Не рекомендуется. Загружает среду CLR в процесс с использованием сведений о версии, хранящихся в XML-файле.  
  
 [Функция CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 Не рекомендуется. Позволяет неуправляемым узлам загружать среду CLR в процесс.  
  
 [Функция CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 Не рекомендуется. Загружает среду CLR в процесс с использованием сведений о версии, считываемых из XML-файла.  
  
 [Функция CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 Не рекомендуется. Позволяет неуправляемым узлам загружать среду CLR в процесс и устанавливать флаги для указания поведения среды CLR.  
  
 [Функция CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 Не рекомендуется. Позволяет узлам загружать указанную версию среды CLR в процесс.  
  
 [Функция GetCORRequiredVersion](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 Не рекомендуется. Возвращает требуемый номер версии среды CLR.  
  
 [Функция GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 Не рекомендуется. Возвращает каталог установки CLR, который загружается в процесс.  
  
 [Функция GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 Не рекомендуется. Возвращает адрес указанной функции, которая экспортируется из последней установленной версии среды CLR.  
  
 [Функция GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 Не рекомендуется. Возвращает сведения о версии и каталоге о среде CLR, запрошенной приложением.  
  
## <a name="clr-version-functions"></a>Функции версий среды CLR  
 Функции в этом разделе возвращают версию среды CLR. они не активируют среду CLR.  
  
 [Функция GetCORVersion](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 Не рекомендуется. Возвращает номер версии среды CLR, которая выполняется в текущем процессе.  
  
 [Функция GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 Не рекомендуется. Возвращает сведения о версии среды CLR указанного файла, используя указанный буфер.  
  
 [Функция GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 Не рекомендуется. Возвращает номер версии среды CLR, запрошенной указанным приложением. Если эта версия не установлена, возвращает последнюю версию, установленную до запрошенной версии.  
  
 [Функция GetRequestedRuntimeVersionForCLSID](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 Не рекомендуется. Возвращает соответствующую информацию о версии среды CLR для класса с указанным идентификатором CLSID.  
  
 [Функция GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 Не рекомендуется. Возвращает номер версии среды CLR, связанной с указанным обработчиком процесса.  
  
 [Функция LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 Не рекомендуется. Позволяет узлу определить версию среды CLR, которая будет использоваться в процессе перед явной инициализацией среды CLR.  
  
## <a name="hosting-functions"></a>Функции размещения  
 [Функция CallFunctionShim](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 Не рекомендуется. Вызывает функцию с указанным именем и параметрами в указанной библиотеке.  
  
 [Функция CoEEShutDownCOM](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 Не рекомендуется. Выгружает сборку COM из процесса.  
  
 [Функция CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 Не рекомендуется. Завершает текущий неуправляемый процесс.  
  
 [Функция CorLaunchApplication](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 Не рекомендуется. Запускает приложение по указанному сетевому пути, используя указанные манифесты и другие данные приложения.  
  
 [Функция CorMarkThreadInThreadPool](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 Не рекомендуется. Помечает выполняющийся в данный момент поток пула потоков для выполнения управляемого кода. Начиная с версии .NET Framework 2,0 эта функция не действует. Он не является обязательным и может быть удален из кода.  
  
 [Функция CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 Является устаревшей. Среду CLR нельзя выгрузить из процесса.  
  
 [Функция CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 Является устаревшей.  
  
 [Функция CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 Не рекомендуется. Создает объект [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) на основе указанных сведений о версии.  
  
 [Функция CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 Не рекомендуется. Создает объект [ицеефилежен](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) .  
  
 [Функция DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 Не рекомендуется. Уничтожает объект [ицеефилежен](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) .  
  
 [Указатель функции FExecuteInAppDomainCallback](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которую CLR вызывает для выполнения управляемого кода.  
  
 [Указатель функции FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая вызывается средой CLR для уведомления узла о том, что инициализация запущена или завершена.  
  
 [Функция GetCLRIdentityManager](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 Не рекомендуется. Возвращает указатель на интерфейс, который позволяет среде CLR управлять удостоверениями.  
  
 [Функция LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 Не рекомендуется. Загружает указанную версию .NET Framework DLL.  
  
 [Функция LoadStringRC](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 Не рекомендуется. Преобразует значение HRESULT в сообщение об ошибке с помощью языка и региональных параметров по умолчанию текущего потока.  
  
 [Функция LoadStringRCEx](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 Не рекомендуется. Преобразует значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.  
  
 [Указатель функции LPOVERLAPPED_COMPLETION_ROUTINE](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая уведомляет узел при завершении перекрытия (асинхронного) ввода-вывода на устройство.  
  
 [Указатель функции LPTHREAD_START_ROUTINE](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая уведомляет узел о начале выполнения потока.  
  
 [Функция RunDll32ShimW](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 Не рекомендуется. Выполняет указанную команду.  
  
 [Указатель функции WAITORTIMERCALLBACK](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая уведомляет узел о том, что дескриптор ожидания имеет сигнал или время ожидания истекло.  
  
## <a name="infrastructure-functions"></a>Функции инфраструктуры  
 Функции в этом разделе предназначены для использования только .NET Framework.  
  
 [Функция _CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 Инициализирует среду CLR, находит управляемую точку входа в заголовке CLR сборки DLL и начинает выполнение.  
  
 [Функция _CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 Инициализирует среду CLR, находит управляемую точку входа в заголовке CLR исполняемой сборки и начинает выполнение.  
  
 [Функция _CorExeMain2](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 Выполняет точку входа в указанном коде, сопоставленном с памятью. Эта функция вызывается загрузчиком операционной системы.  
  
 [Функция _CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 Уведомляет загрузчик об выгрузке образов управляемого модуля.  
  
 [Функция _CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 Проверяет образы управляемого модуля и уведомляет загрузчик операционной системы после их загрузки.  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции размещения платформы .NET Framework 4](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md)
