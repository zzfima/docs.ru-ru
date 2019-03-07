---
title: Метод ICLRRuntimeInfo::IsLoaded
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd1d97d9f3a44e2237cfc7a9e054a5ecfa2ebb01
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470761"
---
# <a name="iclrruntimeinfoisloaded-method"></a>Метод ICLRRuntimeInfo::IsLoaded
Указывает, связан ли общеязыковой среды выполнения (CLR) [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс загружается в процесс. Среда выполнения может быть загружен без ее запуск.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a>Параметры  
 `hndProcess`  
 [in] Дескриптор процесса.  
  
 `pbLoaded`  
 [out] `true` Если CLR загружаются в процесс, в противном случае — `false`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|Параметр `pbLoaded` имеет значение NULL.|  
  
## <a name="remarks"></a>Примечания  
 Этот метод обеспечивает обратную совместимость с следующие функции и интерфейсы:  
  
-   [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) интерфейс (в API размещения платформы .NET Framework версии 1).  
  
-   [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) интерфейс (в платформе .NET Framework 2.0, интерфейс API размещения).  
  
-   Не рекомендуется `CorBindTo*` функции (см. в разделе [устаревшей функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) в .NET Framework 2.0, интерфейс API размещения).  
  
 Узел может вызвать одну из устаревших `CorBindTo*` функции, такие как [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) функции для создания экземпляра определенной версии среды CLR. Узел может затем вызвать метод [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) метод и указать тот же номер версии, чтобы получить [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс.  
  
 Если узел, затем вызывает метод `IsLoaded` метод возвращенного [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс, `pbLoaded` возвращает `true`; в противном случае он возвращает `false`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MetaHost.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
