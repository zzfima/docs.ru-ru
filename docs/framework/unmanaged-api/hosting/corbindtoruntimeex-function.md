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
ms.openlocfilehash: 3520af5f55f43183920dce7fbd24b70359c023a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176504"
---
# <a name="corbindtoruntimeex-function"></a>Функция CorBindToRuntimeEx
Позволяет неуправляемым хостам загружать время выполнения общего языка (CLR) в процесс. [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) и `CorBindToRuntimeEx` функции выполняют ту `CorBindToRuntimeEx` же операцию, но функция позволяет установить флаги, чтобы указать поведение CLR.  
  
 Эта функция была унесена в системе .NET 4.  
  
 Эта функция выполняет набор параметров, которые позволяют хосту сделать следующее:  
  
- Укажите версию времени выполнения, которая будет загружена.  
  
- Укажите, следует ли загрузить сборку сервера или рабочей станции.  
  
- Контролируйте, осуществляется ли параллельный сбор мусора или непараллельный сбор мусора.  
  
> [!NOTE]
> Параллельный сбор мусора не поддерживается в приложениях под управлением эмулятора WOW64 x86 на 64-битных системах, реализуемых в архитектуре Intel Itanium (ранее именуемой IA-64). Для получения дополнительной информации об использовании WOW64 на 64-битных системах Windows [см.](/windows/desktop/WinProg64/running-32-bit-applications)  
  
- Контролируйте, загружаются ли сборки как нейтральные домены.  
  
- Получите указатель интерфейса на [ICorRuntimeHost,](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) который можно использовать для настройки экземпляра CLR до его запуска.  
  
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
 (в) Строка, описывающая версию CLR, которая вы хотите загрузить.  
  
 Номер версии в рамочном варианте .NET состоит из четырех частей, разделенных периодами: *major.minor.build.revision*. Строка прошла `pwszVersion` так, как должна начаться с символа "v", за которым следуют первые три части номера версии (например, "v1.0.1529").  
  
 Некоторые версии CLR установлены с программным заявлением, которое определяет совместимость с предыдущими версиями CLR. По умолчанию shim запуска `pwszVersion` оценивается в соответствии с политическими заявлениями и загружает последнюю версию времени выполнения, совместимую с запрашиваемым вариантом. Хост может заставить shim пропустить оценку `pwszVersion` политики и `STARTUP_LOADER_SAFEMODE` загрузить `startupFlags` точную версию, указанную в, передавая значение для параметра, как описано ниже.  
  
 Если абонент указывает null for, `pwszVersion` `CorBindToRuntimeEx` определяет набор установленных времен выполнения, номера версий которых ниже, чем время выполнения .NET Framework 4, и загружает последнюю версию времени выполнения из этого набора. Он не будет загружать сяррамки .NET 4 или позже, и выходит из строя, если не будет установлена более ранняя версия. Обратите внимание, что прохождение нулевой не дает хосту никакого контроля над тем, какая версия времени выполнения загружается. Хотя этот подход может быть уместным в некоторых сценариях, настоятельно рекомендуется, чтобы ухост поставлял определенную версию для загрузки.  
  
 `pwszBuildFlavor`  
 (в) Строка, которая определяет, загружать ли сервер или сборку рабочей станции CLR. Допустимые значения: `svr` и `wks`. Сборка сервера оптимизирована, чтобы использовать преимущества нескольких процессоров для сбора мусора, а сборка рабочих станций оптимизирована для клиентских приложений, работающих на однопроцессорной машине.  
  
 Если `pwszBuildFlavor` установка сведена на нет, сборка рабочей станции загружается. При работе на однопроцессорной машине сборка рабочей станции всегда загружается, даже если `pwszBuildFlavor` настроена на. `svr` Однако, `pwszBuildFlavor` если `svr` установлен и одновременное вывоз мусора `startupFlags` указан (см. описание параметра), сборка сервера загружается.  
  
 `startupFlags`  
 (в) Сочетание значений [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) перечисления. Эти флаги контролируют параллельный сбор мусора, нейтральный код домена и поведение `pwszVersion` параметра. По умолчанию один домен, если флаг не установлен. Допустимы следующие значения:  
  
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
  
 Описания этих флагов смотрите [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) перечисления.  
  
 `rclsid`  
 (в) Кокласс, `CLSID` который реализует либо [iCorRuntimeHost,](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) либо интерфейс [ICLRRuntimeHost.](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) Поддерживаемые значения являются CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.  
  
 `riid`  
 (в) Запрашиваемый `IID` интерфейс `rclsid`от . Поддерживаемые значения IID_ICorRuntimeHost или IID_ICLRRuntimeHost.  
  
 `ppv`  
 (ваут) Возвращается указатель `riid`интерфейса к .  
  
## <a name="remarks"></a>Remarks  
 Если `pwszVersion` указывается версия времени выполнения, которая `CorBindToRuntimeEx` не существует, возвращает значение HRESULT CLR_E_SHIM_RUNTIMELOAD.  
  
## <a name="execution-context-and-flow-of-windows-identity"></a>Контекст выполнения и поток идентификации Windows  
 В версии 1 CLR <xref:System.Security.Principal.WindowsIdentity> объект не перетекает через асинхронные точки, такие как новые потоки, пулы потоков или обратные вызовы таймер. В версии 2.0 CLR <xref:System.Threading.ExecutionContext> объект обертывает некоторую информацию о исполняемый в настоящее время потоке и перетекает в любую асинхронную точку, но не через границы доменов приложения. Аналогичным образом, <xref:System.Security.Principal.WindowsIdentity> объект также течет через любую асинхронную точку. Таким образом, текущее олицетворение на потоке, если таковые имеется, течет тоже.  
  
 Вы можете изменить поток двумя способами:  
  
1. Изменяя <xref:System.Threading.ExecutionContext> настройки для подавления потока на основе потока <xref:System.Threading.ExecutionContext.SuppressFlow%2A> <xref:System.Security.SecurityContext.SuppressFlow%2A>(см. , и <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> методы).  
  
2. Изменяя режим по умолчанию процесса на режим <xref:System.Security.Principal.WindowsIdentity> совместимости версии 1, где объект не <xref:System.Threading.ExecutionContext> проходит через какую-либо асинхронную точку, независимо от настроек текущего потока. Как изменить режим по умолчанию зависит от того, используете ли вы управляемый исполняемый или неуправляемый интерфейс хостинга для загрузки CLR:  
  
    1. Для управляемых исполнителей необходимо установить `enabled` атрибут [ \<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) `true`элемент.  
  
    2. Для неуправляемых интерфейсов `STARTUP_LEGACY_IMPERSONATION` хостинга `startupFlags` установите флаг `CorBindToRuntimeEx` в параметре при вызове функции.  
  
     Режим совместимости версии 1 применяется ко всему процессу и ко всем доменам приложений в процессе.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Функция CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [Функция CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [Функция CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [Функция CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
