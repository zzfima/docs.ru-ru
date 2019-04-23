---
title: Устаревшие функции размещения CLR
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa84ca0defd173563817673aad183a8b64226d41
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135815"
---
# <a name="deprecated-clr-hosting-functions"></a>Устаревшие функции размещения CLR
В этом разделе описываются неуправляемые глобальные статистические функции, используемые в более ранних версиях API размещения.  
  
 За исключением функций инфраструктуры (`_Cor*` функции), которые используются только платформой .NET Framework, эти функции стали нерекомендуемыми в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="activation-functions"></a>Функции активации  
 [Функция ClrCreateManagedInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 Не рекомендуется. Создает экземпляра указанного управляемого типа.  
  
 [Функция CoInitializeCor](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 Является устаревшей. Чтобы инициализировать общеязыковой среды выполнения (CLR), используйте [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) или [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).  
  
 [Функция CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 Не рекомендуется. Гарантирует, что ядро выполнения среды CLR загружается в процесс. Используйте [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) метод вместо этого.  
  
 [Функция CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 Не рекомендуется. Загружает общеязыковой среды выполнения (CLR) в процесс, используя сведения, хранящиеся в XML-файл.  
  
 [Функция CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 Не рекомендуется. Позволяет неуправляемым основным приложениям загружать среду CLR в процесс.  
  
 [Функция CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 Не рекомендуется. Загружает среду CLR в процесс, используя сведения о версии, которая фактически считывается из файла XML.  
  
 [Функция CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 Не рекомендуется. Позволяет неуправляемым основным приложениям загружать среду CLR в процесс и задавать флаги для определения поведения этой СРЕДЫ.  
  
 [Функция CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 Не рекомендуется. Позволяет основным приложениям загружать в процесс заданную версию среды CLR.  
  
 [Функция GetCORRequiredVersion](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 Не рекомендуется. Получает требуется номер версии среды CLR.  
  
 [Функция GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 Не рекомендуется. Возвращает каталог установки загруженной в процесс среды CLR.  
  
 [Функция GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 Не рекомендуется. Получает адрес заданной функции, экспортируемой из последней установленной версии среды CLR.  
  
 [Функция GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 Не рекомендуется. Возвращает сведения о версии и каталоге о среды CLR, запрашиваемой приложением.  
  
## <a name="clr-version-functions"></a>Функции версии CLR  
 В этом разделе функции возвращают версия среды CLR; они не будут активировать среды CLR.  
  
 [Функция GetCORVersion](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 Не рекомендуется. Возвращает номер версии среды CLR, на котором выполняется в текущем процессе.  
  
 [Функция GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 Не рекомендуется. Возвращает сведения о версии среды CLR из указанного файла, используя указанный буфер.  
  
 [Функция GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 Не рекомендуется. Получает номер версии среды CLR, запрашиваемой указанным приложением. Если эта версия не установлена, Получает самую последнюю версию, установленную перед запрашиваемой.  
  
 [Функция GetRequestedRuntimeVersionForCLSID](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 Не рекомендуется. Получает соответствующие сведения о версии среды CLR для класса с заданным идентификатором CLSID.  
  
 [Функция GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 Не рекомендуется. Получает номер версии среды CLR, связанный с указанным дескриптором процесса.  
  
 [Функция LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 Не рекомендуется. Позволяет основному приложению определить, какие версии среды CLR, которая будет использоваться в процессе до явной инициализации среды CLR.  
  
## <a name="hosting-functions"></a>Функции размещения  
 [Функция CallFunctionShim](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 Не рекомендуется. Вызывает функцию, которая имеет указанные имя и параметры в указанной библиотеке.  
  
 [Функция CoEEShutDownCOM](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 Не рекомендуется. Выгружает сборку COM из процесса.  
  
 [Функция CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 Не рекомендуется. Завершает работу текущего неуправляемого процесса.  
  
 [Функция CorLaunchApplication](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 Не рекомендуется. Запускает приложение по указанному сетевому пути, используя заданные манифесты и другие данные приложения.  
  
 [Функция CorMarkThreadInThreadPool](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 Не рекомендуется. Помечает текущий выполняемый поток пула потоков для выполнения управляемого кода. Начиная с .NET Framework версии 2.0, эта функция не оказывает влияния. Он не является обязательным и может быть удалена из кода.  
  
 [Функция CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 Является устаревшей. Среда CLR не может быть выгружена из процесса.  
  
 [Функция CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 Является устаревшей.  
  
 [Функция CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 Не рекомендуется. Создает [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) объекта на основе указанной версии данных.  
  
 [Функция CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 Не рекомендуется. Создает [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) объекта.  
  
 [Функция DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 Не рекомендуется. Уничтожает [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) объекта.  
  
 [Указатель функции FExecuteInAppDomainCallback](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которую среда CLR вызывает для выполнения управляемого кода.  
  
 [Указатель функции FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которую среда CLR вызывает для уведомления узла, инициализация либо началась или уже завершена.  
  
 [Функция GetCLRIdentityManager](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 Не рекомендуется. Получает указатель на интерфейс, который позволяет среде CLR для управления удостоверениями.  
  
 [Функция LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 Не рекомендуется. Загружает указанную версию DLL платформы .NET Framework.  
  
 [Функция LoadStringRC](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 Не рекомендуется. Преобразовывает значение HRESULT в сообщение об ошибке с помощью языка и региональных параметров по умолчанию текущего потока.  
  
 [Функция LoadStringRCEx](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 Не рекомендуется. Преобразовывает значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.  
  
 [Указатель функции LPOVERLAPPED_COMPLETION_ROUTINE](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая уведомляет основное приложение перекрывающегося (то есть асинхронный) завершения ввода-вывода на устройство.  
  
 [Указатель функции LPTHREAD_START_ROUTINE](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая уведомляет основное приложение, который запущен поток для выполнения.  
  
 [Функция RunDll32ShimW](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 Не рекомендуется. Выполняет указанную команду.  
  
 [Указатель функции WAITORTIMERCALLBACK](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая уведомляет основное приложение, что дескриптор ожидания либо был получает сигнал, либо истекло время ожидания.  
  
## <a name="infrastructure-functions"></a>Функции инфраструктуры  
 Функции в этом разделе предназначены для использования в платформе .NET Framework.  
  
 [Функция _CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 Инициализирует среду CLR, размещает управляемую точку входа в заголовке среды CLR сборки DLL и начинает выполнение.  
  
 [Функция _CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 Инициализирует среду CLR, размещает управляемую точку входа в заголовке среды CLR исполняемой сборки и начинает выполнение.  
  
 [Функция _CorExeMain2](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 Выполняет точку входа в указанном коде отображения памяти. Эта функция вызывается загрузчиком операционной системы.  
  
 [Функция _CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 Уведомляет загрузчик о выгрузке образов управляемого модуля.  
  
 [Функция _CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 Проверяет образы управляемого модуля и уведомляет загрузчик операционной системы, после они были загружены.  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции размещения платформы .NET Framework 4](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md)
