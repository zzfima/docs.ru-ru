---
title: Метод ICLRMetaHost::EnumerateLoadedRuntimes
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateLoadedRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5a0c577975b1c16234fda649b54bcdd9f1ae59e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494882"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a>Метод ICLRMetaHost::EnumerateLoadedRuntimes
Возвращает перечисление, которое содержит допустимый [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) указатель на интерфейс для каждой версии CLR (CLR), загружается в данном процессе. Этот метод заменяет [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `hndProcess`  
 [in] Дескриптор процесса для проверки на наличие загруженных сред выполнения.  
  
 `ppEnumerator`  
 [out] <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> Перечисление [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейсов, связанных с каждой среды CLR, загруженные процессом.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|Параметр `ppEnumerator` имеет значение null.|  
  
## <a name="remarks"></a>Примечания  
 Этот метод является список всех загрузки среды выполнения, даже если они загружены с устаревшие функции, такие как [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MetaHost.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
