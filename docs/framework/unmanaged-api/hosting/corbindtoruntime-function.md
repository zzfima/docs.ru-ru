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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e15b1ab33dd6ab5e9cd9887000c0f91e0bd4a9a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496655"
---
# <a name="corbindtoruntime-function"></a>Функция CorBindToRuntime
Позволяет неуправляемым основным приложениям загружать в процесс общеязыковой среды выполнения (CLR).  
  
 Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
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
  
## <a name="parameters"></a>Параметры  
 `pwszVersion`  
 [in] Строка, описывающая версию среды CLR, вы хотите загрузить.  
  
 Номер версии в .NET Framework состоит из четырех частей, разделенных точками: *major.minor.build.revision*. Строка, передаваемая как `pwszVersion` должно начинаться с символа «v», следуют первые три части номера версии (например, «v1.0.1529»).  
  
 В некоторых версиях среды CLR, устанавливаются вместе с инструкцию политики, которая указывает совместимости с предыдущими версиями среды CLR. По умолчанию оболочка загрузки оценивает `pwszVersion` от операторов политик и загружает последнюю версию среды выполнения, совместима с запрашиваемой. Основное приложение может вынудить оболочку пропустить оценку политики и загрузить точной версии, указанной в `pwszVersion` , передав значение `STARTUP_LOADER_SAFEMODE` для `flags` параметра, как описано ниже.  
  
 Если вызывающая сторона задает значение null для `pwszVersion`, загружается последняя версия среды выполнения. Передачу значений null дает узлу не управляет, по которому загружается версия среды выполнения. Несмотря на то, что этот подход может быть полезным в некоторых сценариях, настоятельно рекомендуется указывать определенную версию для загрузки.  
  
 `pwszBuildFlavor`  
 [in] Строковое значение, указывающее, следует ли загружать на сервере или рабочей станции сборки среды CLR. Допустимые значения: `svr` и `wks`. Построение сервера оптимизирован так, чтобы воспользоваться преимуществами нескольких процессоров для сборки мусора и построение рабочей станции оптимизировано для клиентских приложений на однопроцессорном компьютере.  
  
 Если `pwszBuildFlavor` имеет значение null, загружается построение рабочей станции. При выполнении на однопроцессорном компьютере всегда загружается построение рабочей станции, даже если `pwszBuildFlavor` присваивается `svr`. Тем не менее если `pwszBuildFlavor` присваивается `svr` и указывается параллельной сборки мусора (см. в описании `flags` параметр), загружается построение сервера.  
  
 `rclsid`  
 [in] `CLSID` Компонентного класса, реализующий [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) или [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) интерфейс. Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.  
  
 `riid`  
 [in] `IID` Запрошенного интерфейса из `rclsid`. Поддерживаемые значения: IID_ICorRuntimeHost и IID_ICLRRuntimeHost.  
  
 `ppv`  
 [out] Указатель на возвращенный интерфейс `riid`.  
  
## <a name="remarks"></a>Примечания  
 Если `pwszVersion` указывает версию среды выполнения, которая не существует, `CorBindToRuntimeEx` возвращает HRESULT со значением CLR_E_SHIM_RUNTIMELOAD.  
  
## <a name="execution-context-and-flow-of-windows-identity"></a>Контекст выполнения и поток удостоверения Windows  
 В версии 1 среды CLR <xref:System.Security.Principal.WindowsIdentity> объекта не проходит через асинхронные точки, такие как новые потоки, пулы потоков или обратные вызовы таймера. В версии 2.0 среды CLR <xref:System.Threading.ExecutionContext> объект включает некоторые сведения о текущем потоке и проходит через все асинхронные точки, но не через границы домена приложения. Аналогичным образом <xref:System.Security.Principal.WindowsIdentity> объекта, также проходит через все асинхронные точки. Таким образом текущий олицетворения в потоке, если таковой имеется, он проходит.  
  
 Можно изменить последовательность из двух способов:  
  
1.  Изменив <xref:System.Threading.ExecutionContext> параметры потока на основе отдельного потока (см. в разделе <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, и <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> методов).  
  
2.  Изменив режим по умолчанию процесс в режиме совместимости версии 1, где <xref:System.Security.Principal.WindowsIdentity> объекта не проходит через все асинхронные точки, вне зависимости от <xref:System.Threading.ExecutionContext> параметры в текущем потоке. Как изменить режим по умолчанию зависит от того, используются ли управляемый исполняемый файл или неуправляемый интерфейс размещения загружать среду CLR.  
  
    1.  Для управляемых исполняемых файлов, необходимо задать `enabled` атрибут [ \<legacyImpersonationPolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) элемент `true`.  
  
    2.  Неуправляемые интерфейсы размещения, задать `STARTUP_LEGACY_IMPERSONATION` флаг в `flags` параметра при вызове `CorBindToRuntimeEx` функции.  
  
     Режим совместимости версии 1 применяется ко всему процессу и для всех доменов приложений в процессе.  
  
## <a name="remarks"></a>Примечания  
 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) и `CorBindToRuntime` выполнить те же операции, но `CorBindToRuntimeEx` функция позволяет задавать флаги для определения поведения этой СРЕДЫ.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Функция CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [Функция CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [Функция CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [Функция CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
