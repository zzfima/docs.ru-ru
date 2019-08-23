---
title: Функция CorBindToRuntimeEx
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeEx
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeEx
helpviewer_keywords:
- CorBindToRuntimeEx function [.NET Framework hosting]
ms.assetid: aae9fb17-5d01-41da-9773-1b5b5b642d81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88f31ae29efee9b353c2dcc679724db73da5444e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969415"
---
# <a name="corbindtoruntimeex-function"></a>Функция CorBindToRuntimeEx
Позволяет неуправляемым узлам загружать среду CLR в процесс. [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) и `CorBindToRuntimeEx` функции выполняют одну и ту же `CorBindToRuntimeEx` операцию, но функция позволяет устанавливать флаги для указания поведения среды CLR.  
  
 Эта функция является устаревшей в .NET Framework 4.  
  
 Эта функция принимает набор параметров, позволяющих узлу выполнять следующие действия:  
  
- Укажите версию среды выполнения, которая будет загружена.  
  
- Укажите, следует ли загружать сборку сервера или рабочей станции.  
  
- Управление тем, выполняется ли параллельная сборка мусора или не параллельная сборка мусора.  
  
> [!NOTE]
> Параллельная сборка мусора не поддерживается в приложениях, использующих Эмулятор WOW64 x86 в 64-разрядных системах, которые реализуют архитектуру Intel Itanium (прежнее название — IA-64). Дополнительные сведения об использовании WOW64 в 64-разрядных системах Windows см. в разделе [выполнение 32-разрядных приложений](/windows/desktop/WinProg64/running-32-bit-applications).  
  
- Определяет, загружаются ли сборки как нейтральные к домену.  
  
- Получите указатель интерфейса на [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) , который можно использовать для установки дополнительных параметров для настройки экземпляра среды CLR перед его запуском.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CorBindToRuntimeEx (  
    [in]  LPCWSTR      pwszVersion,   
    [in]  LPCWSTR      pwszBuildFlavor,   
    [in]  DWORD        startupFlags,   
    [in]  REFCLSID     rclsid,   
    [in]  REFIID       riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pwszVersion`  
 окне Строка, описывающая версию среды CLR, которую требуется загрузить.  
  
 Номер версии в .NET Framework состоит из четырех частей, разделенных точками: *основной. дополнительный. сборка. Редакция*. Строка, передаваемая `pwszVersion` как, должна начинаться с символа "v", за которым следуют первые три части номера версии (например, "v 1.0.1529").  
  
 Некоторые версии среды CLR устанавливаются с инструкцией политики, которая определяет совместимость с предыдущими версиями среды CLR. По умолчанию оболочка `pwszVersion` запуска выполняет проверку на соответствие инструкциям политики и загружает последнюю версию среды выполнения, совместимую с запрашиваемой версией. Узел может заставить оболочку пропускать вычисление политики и загружать точную версию, указанную `pwszVersion` в, передав `STARTUP_LOADER_SAFEMODE` значение для `startupFlags` параметра, как описано ниже.  
  
 Если вызывающий объект задает значение `pwszVersion`NULL `CorBindToRuntimeEx` для, определяет набор установленных сред выполнения, Номера версий которых ниже среды выполнения .NET Framework 4, и загружают последнюю версию среды выполнения из этого набора. Он не загружает .NET Framework 4 или более поздней версии и завершается ошибкой, если предыдущая версия не установлена. Обратите внимание, что передача значения NULL позволяет узлу не контролировать, какая версия среды выполнения загружена. Хотя такой подход может быть приемлемым в некоторых сценариях, настоятельно рекомендуется, чтобы узел предоставил определенную версию для загрузки.  
  
 `pwszBuildFlavor`  
 окне Строка, указывающая, загружать ли сервер или рабочую станцию сборку среды CLR. Допустимые значения: `svr` и `wks`. Сборка сервера оптимизирована для использования нескольких процессоров для сборок мусора, а сборка рабочей станции оптимизирована для клиентских приложений, работающих на однопроцессорном компьютере.  
  
 Если `pwszBuildFlavor` параметр имеет значение null, загружается сборка рабочей станции. При запуске на однопроцессорном компьютере сборка рабочей станции всегда загружается, даже если `pwszBuildFlavor` параметр имеет `svr`значение. Однако если `pwszBuildFlavor` задано `svr` значение и задана параллельная сборка мусора ( `startupFlags` см. Описание параметра), то загружается серверная сборка.  
  
 `startupFlags`  
 окне Сочетание значений перечисления [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) . Эти флаги контролируют параллельную сборку мусора, код, нейтральный к домену, `pwszVersion` и поведение параметра. Значение по умолчанию — один домен, если флаг не установлен. Допустимы следующие значения.  
  
- `STARTUP_CONCURRENT_GC`  
  
- `STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`  
  
- `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`  
  
- `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`  
  
- `STARTUP_LOADER_SAFEMODE`  
  
- `STARTUP_LEGACY_IMPERSONATION`  
  
- `STARTUP_LOADER_SETPREFERENCE`  
  
- `STARTUP_SERVER_GC`  
  
- `STARTUP_HOARD_GC_VM`  
  
- `STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`  
  
- `STARTUP_LEGACY_IMPERSONATION`  
  
- `STARTUP_DISABLE_COMMITTHREADSTACK`  
  
- `STARTUP_ALWAYSFLOW_IMPERSONATION`  
  
 Описание этих флагов см. в описании перечисления [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) .  
  
 `rclsid`  
 окне Объект `CLSID` coclass, реализующий интерфейс [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) или [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) . Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.  
  
 `riid`  
 окне Объект `IID` запрашиваемого интерфейса из `rclsid`. Поддерживаемые значения: IID_ICorRuntimeHost или IID_ICLRRuntimeHost.  
  
 `ppv`  
 заполняет Возвращаемый указатель интерфейса в `riid`.  
  
## <a name="remarks"></a>Примечания  
 Если `pwszVersion` указывает несуществующую версию среды выполнения, `CorBindToRuntimeEx` возвращает значение HRESULT, равное CLR_E_SHIM_RUNTIMELOAD.  
  
## <a name="execution-context-and-flow-of-windows-identity"></a>Контекст выполнения и поток удостоверения Windows  
 В версии 1 среды CLR <xref:System.Security.Principal.WindowsIdentity> объект не перетекает через асинхронные точки, такие как новые потоки, пулы потоков или обратные вызовы таймера. В версии 2,0 среды CLR <xref:System.Threading.ExecutionContext> объект заключает некоторые сведения о выполняемом в данный момент потоке и передает его через любую асинхронную точку, но не через границы домена приложения. Аналогичным образом <xref:System.Security.Principal.WindowsIdentity> объект также проходит через любую асинхронную точку. Таким образом, текущее олицетворение в потоке, если таковое имеется, также проходит.  
  
 Изменить последовательность можно двумя способами:  
  
1. Путем изменения <xref:System.Threading.ExecutionContext> параметров для подавления потока на основе потока ( <xref:System.Threading.ExecutionContext.SuppressFlow%2A>см. методы, <xref:System.Security.SecurityContext.SuppressFlow%2A>и <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> ).  
  
2. Изменив режим обработки по умолчанию на режим совместимости версии 1, где <xref:System.Security.Principal.WindowsIdentity> объект не пополняется по какой бы то ни было асинхронной точке, независимо <xref:System.Threading.ExecutionContext> от параметров в текущем потоке. Изменение режима по умолчанию зависит от того, используется ли управляемый исполняемый файл или неуправляемый интерфейс размещения для загрузки среды CLR:  
  
    1. Для управляемых исполняемых файлов необходимо задать `enabled` атрибуту `true` [ \<элемента > легациимперсонатионполици](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) значение.  
  
    2. Для неуправляемых интерфейсов размещения установите `STARTUP_LEGACY_IMPERSONATION` флаг `startupFlags` в параметре при вызове `CorBindToRuntimeEx` функции.  
  
     Режим совместимости версии 1 применяется ко всему процессу и всем доменам приложения в процессе.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE. h  
  
 **Библиотечная** MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [Функция CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [Функция CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [Функция CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
