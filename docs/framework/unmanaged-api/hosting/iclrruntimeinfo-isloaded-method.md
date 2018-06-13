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
ms.openlocfilehash: 5ff1723cb481ee946e0c5c433009d3d6d7460cf5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434667"
---
# <a name="iclrruntimeinfoisloaded-method"></a>Метод ICLRRuntimeInfo::IsLoaded
Указывает ли общеязыковой среды выполнения (CLR), связанные с [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс загружается в процесс. Среда выполнения может быть загружен без ее запуск.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
#### <a name="parameters"></a>Параметры  
 `hndProcess`  
 [in] Дескриптор процесса.  
  
 `pbLoaded`  
 [out] `true` Если CLR загружается в процесс; в противном случае — `false`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|Параметр `pbLoaded` имеет значение null.|  
  
## <a name="remarks"></a>Примечания  
 Этот метод обеспечивает обратную совместимость со следующими функциями и интерфейсы:  
  
-   [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) интерфейса (API размещения платформы .NET Framework версии 1).  
  
-   [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) интерфейс (в платформе .NET Framework 2.0, API размещения).  
  
-   Не рекомендуется `CorBindTo*` функции (см. [устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) в API размещения платформы .NET Framework 2.0).  
  
 Узел может вызвать одну из устаревших `CorBindTo*` функции, например [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) функции для создания экземпляра определенной версии среды CLR. Узел может затем вызвать метод [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) метод и указать тот же номер версии, чтобы получить [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейса.  
  
 Если затем основное приложение вызывает `IsLoaded` метод в возвращенном [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс, `pbLoaded` возвращает `true`; в противном случае он возвращает `false`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
