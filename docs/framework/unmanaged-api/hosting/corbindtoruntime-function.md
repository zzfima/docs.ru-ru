---
title: Функция CorBindToRuntime
ms.date: 03/30/2017
api_name:
- CorBindToRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntime
helpviewer_keywords:
- CorBindToRuntime function [.NET Framework hosting]
ms.assetid: 799740aa-46ec-4532-95da-6444565b4971
topic_type:
- apiref
ms.openlocfilehash: 9d4b8bb7d5b3da15f665849c8d18c3a10dbe600b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138312"
---
# <a name="corbindtoruntime-function"></a>Функция CorBindToRuntime
Позволяет неуправляемым узлам загружать среду CLR в процесс.  
  
 Эта функция является устаревшей в .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,   
    [in]  LPCWSTR     pwszBuildFlavor,   
    [in]  REFCLSID    rclsid,   
    [in]  REFIID      riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pwszVersion`  
 окне Строка, описывающая версию среды CLR, которую требуется загрузить.  
  
 Номер версии в .NET Framework состоит из четырех частей, разделенных точками: *основной. дополнительный. сборка. Редакция*. Строка, передаваемая как `pwszVersion`, должна начинаться с символа "v", за которым следуют первые три части номера версии (например, "v 1.0.1529").  
  
 Некоторые версии среды CLR устанавливаются с инструкцией политики, которая определяет совместимость с предыдущими версиями среды CLR. По умолчанию оболочка запуска проверяет `pwszVersion` в соответствии с инструкциями политики и загружает последнюю версию среды выполнения, совместимую с запрашиваемой версией. Узел может заставить оболочку пропускать вычисление политики и загружать точную версию, указанную в `pwszVersion`, передав значение `STARTUP_LOADER_SAFEMODE` для параметра `flags`, как описано ниже.  
  
 Если вызывающий объект указывает значение NULL для `pwszVersion`, загружается последняя версия среды выполнения. Передача значения NULL позволяет узлу не контролировать, какая версия среды выполнения загружена. Хотя такой подход может быть приемлемым в некоторых сценариях, настоятельно рекомендуется, чтобы узел предоставил определенную версию для загрузки.  
  
 `pwszBuildFlavor`  
 окне Строка, указывающая, загружать ли сервер или рабочую станцию сборку среды CLR. Допустимые значения: `svr` и `wks`. Сборка сервера оптимизирована для использования нескольких процессоров для сборок мусора, а сборка рабочей станции оптимизирована для клиентских приложений, работающих на однопроцессорном компьютере.  
  
 Если `pwszBuildFlavor` имеет значение null, загружается сборка рабочей станции. При запуске на однопроцессорном компьютере сборка рабочей станции всегда загружается, даже если `pwszBuildFlavor` имеет значение `svr`. Однако если `pwszBuildFlavor` имеет значение `svr` и задана параллельная сборка мусора (см. Описание параметра `flags`), то загружается серверная сборка.  
  
 `rclsid`  
 окне `CLSID` компонентного класса, реализующего интерфейс [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) или [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) . Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.  
  
 `riid`  
 окне `IID` запрашиваемого интерфейса из `rclsid`. Поддерживаемые значения: IID_ICorRuntimeHost или IID_ICLRRuntimeHost.  
  
 `ppv`  
 заполняет Возвращаемый указатель интерфейса на `riid`.  
  
## <a name="remarks"></a>Заметки  
 Если `pwszVersion` указывает несуществующую версию среды выполнения, `CorBindToRuntimeEx` возвращает значение HRESULT CLR_E_SHIM_RUNTIMELOAD.  
  
## <a name="execution-context-and-flow-of-windows-identity"></a>Контекст выполнения и поток удостоверения Windows  
 В версии 1 среды CLR объект <xref:System.Security.Principal.WindowsIdentity> не перетекает через асинхронные точки, такие как новые потоки, пулы потоков или обратные вызовы таймера. В версии 2,0 среды CLR объект <xref:System.Threading.ExecutionContext> заключает некоторые сведения о выполняемом в данный момент потоке и передает его через любую асинхронную точку, но не через границы домена приложения. Аналогичным образом объект <xref:System.Security.Principal.WindowsIdentity> также проходит через любую асинхронную точку. Таким образом, текущее олицетворение в потоке, если таковое имеется, также проходит.  
  
 Изменить последовательность можно двумя способами:  
  
1. Изменяя параметры <xref:System.Threading.ExecutionContext> для подавления потока на основе потока (см. методы <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>и <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A>).  
  
2. Изменив режим обработки по умолчанию на режим совместимости версии 1, где объект <xref:System.Security.Principal.WindowsIdentity> не пополняется по какой бы то ни было асинхронной точке, независимо от параметров <xref:System.Threading.ExecutionContext> в текущем потоке. Изменение режима по умолчанию зависит от того, используется ли управляемый исполняемый файл или неуправляемый интерфейс размещения для загрузки среды CLR:  
  
    1. Для управляемых исполняемых файлов необходимо задать атрибут `enabled` элемента [\<легациимперсонатионполици >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) для `true`.  
  
    2. Для неуправляемых интерфейсов размещения установите флаг `STARTUP_LEGACY_IMPERSONATION` в параметре `flags` при вызове функции `CorBindToRuntimeEx`.  
  
     Режим совместимости версии 1 применяется ко всему процессу и всем доменам приложения в процессе.  
  
## <a name="remarks"></a>Заметки  
 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) и `CorBindToRuntime` выполняют одну и ту же операцию, но функция `CorBindToRuntimeEx` позволяет устанавливать флаги для указания поведения среды CLR.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [Функция CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [Функция CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [Функция CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
