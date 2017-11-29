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
ms.openlocfilehash: 9530fecb4f2ca6f59d165e49c282320966fd2fa8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="deprecated-clr-hosting-functions"></a>Устаревшие функции размещения CLR
В этом разделе описываются неуправляемые глобальные статические функции, которые используются в более ранних версиях API размещения.  
  
 За исключением функций инфраструктуры (`_Cor*` функции), которые используются только платформой .NET Framework, эти функции являются устаревшими в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="activation-functions"></a>Активация функции  
 [ClrCreateManagedInstance-функция](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 Не рекомендуется. Создает экземпляр указанного управляемого типа.  
  
 [Coinitializecor-функция](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 Является устаревшей. Чтобы инициализировать общеязыковой среды выполнения (CLR), используйте [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) или [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).  
  
 [Coinitializeee-функция](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 Не рекомендуется. Обеспечивает загрузку ядро выполнения среды CLR в процесс. Используйте [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) метод вместо него.  
  
 [Corbindtocurrentruntime-функция](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 Не рекомендуется. Загружает общеязыковой среды выполнения (CLR) в процесс, используя сведения, хранящиеся в XML-файл.  
  
 [CorBindToRuntime-функция](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 Не рекомендуется. Позволяет неуправляемым узлам загрузить среду CLR в процесс.  
  
 [CorBindToRuntimeByCfg-функция](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 Не рекомендуется. Загружает среду CLR в процесс, используя сведения о версии, считываемые из файла XML.  
  
 [CorBindToRuntimeEx-функция](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 Не рекомендуется. Позволяет неуправляемым узлам загрузить среду CLR в процессе и можно задавать флаги для задания поведения среды CLR.  
  
 [CorBindToRuntimeHost-функция](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 Не рекомендуется. Позволяет поставщикам услуг размещения для загрузки заданной версии среды CLR в процесс.  
  
 [Getcorrequiredversion-функция](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 Не рекомендуется. Получает необходимые номер версии среды CLR.  
  
 [Getcorsystemdirectory-функция](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 Не рекомендуется. Возвращает каталог установки среды CLR, которая загружается в процесс.  
  
 [Getrealprocaddress-функция](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 Не рекомендуется. Получает адрес указанной функции, экспортированные из последней установленной версии среды CLR.  
  
 [GetRequestedRuntimeInfo-функция](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 Не рекомендуется. Получает сведения о версии и каталоге о среде CLR, запрошенный приложением.  
  
## <a name="clr-version-functions"></a>Версия функции CLR  
 В этом разделе возвращают версию среды CLR; они не активировать среды CLR.  
  
 [Getcorversion-функция](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 Не рекомендуется. Возвращает номер версии среды CLR, которая выполняется в текущем процессе.  
  
 [Getfileversion-функция](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 Не рекомендуется. Возвращает сведения о версии среды CLR для указанного файла, используя указанный буфер.  
  
 [GetRequestedRuntimeVersion-функция](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 Не рекомендуется. Получает номер версии среды CLR, запрашиваемой указанным приложением. Если эта версия не установлена, Получает самую последнюю версию, установленную перед запрошенной версии.  
  
 [Getrequestedruntimeversionforclsid-функция](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 Не рекомендуется. Возвращает соответствующие сведения о версии среды CLR для класса с заданным идентификатором CLSID.  
  
 [GetVersionFromProcess-функция](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 Не рекомендуется. Получает номер версии среды CLR, связанный с заданным дескриптором процесса.  
  
 [LockClrVersion-функция](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 Не рекомендуется. Предоставляет узлу возможность определить, какие версии среды CLR, которая будет использоваться в процессе до явной инициализации среды CLR.  
  
## <a name="hosting-functions"></a>Функции размещения  
 [Callfunctionshim-функция](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 Не рекомендуется. Выполняется вызов функции с указанным именем и параметрами в указанной библиотеке.  
  
 [CoEEShutDownCOM-функция](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 Не рекомендуется. Выгружает сборку COM из процесса.  
  
 [CorExitProcess-функция](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 Не рекомендуется. Завершает работу текущего неуправляемого процесса.  
  
 [Corlaunchapplication-функция](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 Не рекомендуется. Запускает приложение по указанному сетевому пути, используя заданные манифесты и другие данные приложения.  
  
 [Cormarkthreadinthreadpool-функция](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 Не рекомендуется. Помечает текущий выполняемый поток из пула потоков для выполнения управляемого кода. Начиная с .NET Framework версии 2.0, эта функция не делает ничего. Он не является обязательным и может быть удален из кода.  
  
 [Couninitializecor-функция](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 Является устаревшей. Среда CLR не может быть выгружен из процесса.  
  
 [Couninitializeee-функция](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 Является устаревшей.  
  
 [Функция CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 Не рекомендуется. Создает [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) объекта на основе указанной версии данных.  
  
 [Createiceefilegen-функция](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 Не рекомендуется. Создает [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) объекта.  
  
 [Destroyiceefilegen-функция](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 Не рекомендуется. Уничтожает [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) объекта.  
  
 [Указатель функции FExecuteInAppDomainCallback](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которую среда CLR вызывает на выполнение управляемого кода.  
  
 [Указатель функции FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая вызывается средой CLR для уведомления узла инициализации либо начала или завершения.  
  
 [Getclridentitymanager-функция](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 Не рекомендуется. Возвращает указатель на интерфейс, который позволяет среде CLR для управления удостоверениями.  
  
 [LoadLibraryShim-функция](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 Не рекомендуется. Загружает заданную версию библиотеки DLL, .NET Framework.  
  
 [Loadstringrc-функция](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 Не рекомендуется. Преобразовывает значение HRESULT в сообщение об ошибке с помощью языка и региональных параметров по умолчанию текущего потока.  
  
 [Loadstringrcex-функция](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 Не рекомендуется. Преобразовывает значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.  
  
 [LPOVERLAPPED_COMPLETION_ROUTINE-указатель функции](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая уведомляет основное приложение перекрывающегося (то есть асинхронные) завершения ввода-вывода на устройстве.  
  
 [LPTHREAD_START_ROUTINE-указатель функции](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая уведомляет основное приложение начала выполнения потока.  
  
 [Rundll32shimw-функция](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 Не рекомендуется. Выполняет указанную команду.  
  
 [WAITORTIMERCALLBACK-указатель функции](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая уведомляет узел, что дескриптор ожидания был сигнал или истекло время ожидания.  
  
## <a name="infrastructure-functions"></a>Функции инфраструктуры  
 Функции, в этом разделе предназначены для использования только в .NET Framework.  
  
 [_CorDllMain-функция](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 Инициализирует среду CLR, размещает управляемую точку входа в заголовке среды CLR сборки DLL и начинает выполнение.  
  
 [_CorExeMain-функция](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 Инициализирует среду CLR, размещает управляемую точку входа в заголовке среды CLR исполняемой сборки и начинает выполнение.  
  
 [_Corexemain2-функция](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 Выполняет точка входа в заданный код, размещенный в памяти. Эта функция вызывается загрузчиком операционной системы.  
  
 [_CorImageUnloading-функция](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 Уведомляет загрузчика при выгрузке образов управляемых модулей.  
  
 [_CorValidateImage-функция](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 Проверяет образы управляемого модуля и уведомляет загрузчик операционной системы после их загрузки.  
  
## <a name="see-also"></a>См. также  
 [.NET framework 4 глобальные статические функции размещения](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md) 
