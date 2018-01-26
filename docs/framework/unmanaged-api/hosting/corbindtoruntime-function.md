---
title: "Функция CorBindToRuntime"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorBindToRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CorBindToRuntime
helpviewer_keywords: CorBindToRuntime function [.NET Framework hosting]
ms.assetid: 799740aa-46ec-4532-95da-6444565b4971
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e6ce976961eedaa58ad265a133c15b2f27a8985
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corbindtoruntime-function"></a>Функция CorBindToRuntime
Позволяет неуправляемым узлам загрузки общеязыковой среды выполнения (CLR) в процесс.  
  
 Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,   
    [in]  LPCWSTR     pwszBuildFlavor,   
    [in]  REFCLSID    rclsid,   
    [in]  REFIID      riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pwszVersion`  
 [in] Строка, описывающая версию среды CLR, которую требуется загрузить.  
  
 Номер версии платформы .NET Framework состоит из четырех частей, разделенных точками: *major.minor.build.revision*. Строка, переданная как `pwszVersion` должно начинаться с символа «v», следуют первые три части номера версии (например, «v1.0.1529»).  
  
 Некоторые версии среды CLR устанавливаются с помощью оператора политики, указывающее, совместимость с предыдущими версиями среды CLR. По умолчанию оболочка загрузки проверяет `pwszVersion` от инструкции политики и загружает последнюю версию среды выполнения, которая совместима со запрашиваемой. Основное приложение может вынудить оболочку пропустить оценку политики и загрузить точное версия, указанная в `pwszVersion` , передав значение `STARTUP_LOADER_SAFEMODE` для `flags` параметра, как описано ниже.  
  
 Если вызывающий объект задает значение null для `pwszVersion`, загружается последняя версия среды выполнения. Значение null не позволяет узла без управления, по которому загрузки версии среды выполнения. Несмотря на то, что такой подход может быть полезным в некоторых сценариях, настоятельно рекомендуется указывать определенную версию для загрузки.  
  
 `pwszBuildFlavor`  
 [in] Строка, указывающая, следует ли загружать сервера или рабочей станции сборки среды CLR. Допустимые значения: `svr` и `wks`. Построение сервера оптимизировано для использования нескольких процессоров для сборки мусора, а построение рабочей станции оптимизировано для клиентских приложений на однопроцессорного компьютера.  
  
 Если `pwszBuildFlavor` имеет значение null, загружается построение рабочей станции. На компьютере одним процессором всегда загружается построение рабочей станции, даже если `pwszBuildFlavor` равно `svr`. Тем не менее если `pwszBuildFlavor` равно `svr` и указывается параллельная сборка мусора (см. в описании `flags` параметра), загружается построение сервера.  
  
 `rclsid`  
 [in] `CLSID` Компонентного класса, который реализует или [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) или [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) интерфейса. Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.  
  
 `riid`  
 [in] `IID` Запрашиваемого интерфейса из `rclsid`. Поддерживаемыми значениями являются IID_ICorRuntimeHost и IID_ICLRRuntimeHost.  
  
 `ppv`  
 [out] Возвращаемый указатель интерфейса на `riid`.  
  
## <a name="remarks"></a>Примечания  
 Если `pwszVersion` указывает версию среды выполнения, которая не существует, `CorBindToRuntimeEx` возвращает значение HRESULT CLR_E_SHIM_RUNTIMELOAD.  
  
## <a name="execution-context-and-flow-of-windows-identity"></a>Контекст выполнения и поток идентификации Windows  
 В версии 1 среды CLR <xref:System.Security.Principal.WindowsIdentity> объекта не проходит через асинхронные точки, например новых потоков, пулов потоков или обратные вызовы таймера. В среде CLR версии 2.0 <xref:System.Threading.ExecutionContext> объект включает некоторые сведения о текущий выполняемый поток и проходит через все асинхронные точки, но не через границы домена приложения. Аналогичным образом <xref:System.Security.Principal.WindowsIdentity> объект проходит через все асинхронные точки. Таким образом олицетворение текущего потока, если таковые имеются, он проходит.  
  
 Можно изменить поток двумя способами:  
  
1.  Путем изменения <xref:System.Threading.ExecutionContext> параметры для подавления потока для каждого потока (в разделе <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, и <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> методов).  
  
2.  Изменив режимом по умолчанию процесс в режиме совместимости версии 1, где <xref:System.Security.Principal.WindowsIdentity> объекта не проходит через все асинхронные точки независимо от <xref:System.Threading.ExecutionContext> параметры в текущем потоке. Как изменить режим по умолчанию зависит от того, используются ли управляемый исполняемый файл или неуправляемый интерфейс размещения для загрузки среды CLR.  
  
    1.  Для управляемых исполняемых файлов, необходимо задать `enabled` атрибут [ \<legacyImpersonationPolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) элемент `true`.  
  
    2.  Неуправляемые интерфейсы размещения, задать `STARTUP_LEGACY_IMPERSONATION` флаг в `flags` параметра при вызове `CorBindToRuntimeEx` функции.  
  
     Режим совместимости с версией 1 применяется ко всему процессу и для всех доменов приложений в процессе.  
  
## <a name="remarks"></a>Примечания  
 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) и `CorBindToRuntime` выполнить ту же операцию, но `CorBindToRuntimeEx` функция позволяет задать флаги для задания поведения среды CLR.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Функция CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [Функция CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [Функция CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [Функция CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
