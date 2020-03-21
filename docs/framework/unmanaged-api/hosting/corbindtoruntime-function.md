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
ms.openlocfilehash: 2db9d26ef2dec150977c468b16334a7cb4b3d49c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176517"
---
# <a name="corbindtoruntime-function"></a>Функция CorBindToRuntime
Позволяет неуправляемым хостам загружать время выполнения общего языка (CLR) в процесс.  
  
 Эта функция была унесена в системе .NET 4.  
  
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
 (в) Строка, описывающая версию CLR, которая вы хотите загрузить.  
  
 Номер версии в рамочном варианте .NET состоит из четырех частей, разделенных периодами: *major.minor.build.revision*. Строка прошла `pwszVersion` так, как должна начаться с символа "v", за которым следуют первые три части номера версии (например, "v1.0.1529").  
  
 Некоторые версии CLR установлены с программным заявлением, которое определяет совместимость с предыдущими версиями CLR. По умолчанию shim запуска `pwszVersion` оценивается в соответствии с политическими заявлениями и загружает последнюю версию времени выполнения, совместимую с запрашиваемым вариантом. Хост может заставить shim пропустить оценку `pwszVersion` политики и `STARTUP_LOADER_SAFEMODE` загрузить `flags` точную версию, указанную в, передавая значение для параметра, как описано ниже.  
  
 Если абонент указывает нулевую `pwszVersion`для, последняя версия времени выполнения загружается. Прохождение null не дает хостам никакого контроля над тем, какая версия времени выполнения загружается. Хотя этот подход может быть уместным в некоторых сценариях, настоятельно рекомендуется, чтобы ухост поставлял определенную версию для загрузки.  
  
 `pwszBuildFlavor`  
 (в) Строка, которая определяет, загружать ли сервер или сборку рабочей станции CLR. Допустимые значения: `svr` и `wks`. Сборка сервера оптимизирована, чтобы использовать преимущества нескольких процессоров для сбора мусора, а сборка рабочих станций оптимизирована для клиентских приложений, работающих на однопроцессорной машине.  
  
 Если `pwszBuildFlavor` установка сведена на нет, сборка рабочей станции загружается. При работе на однопроцессорной машине сборка рабочей станции всегда загружается, даже если `pwszBuildFlavor` настроена на. `svr` Однако, `pwszBuildFlavor` если `svr` установлен и одновременное вывоз мусора `flags` указан (см. описание параметра), сборка сервера загружается.  
  
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
  
    2. Для неуправляемых интерфейсов `STARTUP_LEGACY_IMPERSONATION` хостинга `flags` установите флаг `CorBindToRuntimeEx` в параметре при вызове функции.  
  
     Режим совместимости версии 1 применяется ко всему процессу и ко всем доменам приложений в процессе.  
  
## <a name="remarks"></a>Remarks  
 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) `CorBindToRuntime` и выполнять ту же `CorBindToRuntimeEx` операцию, но функция позволяет установить флаги, чтобы указать поведение CLR.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Функция CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [Функция CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [Функция CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [Функция CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
