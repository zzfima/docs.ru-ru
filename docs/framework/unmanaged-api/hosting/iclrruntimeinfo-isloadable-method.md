---
title: Метод ICLRRuntimeInfo::IsLoadable
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4937c86be434ef5e97ec72763b7c53d5435bcaf4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774023"
---
# <a name="iclrruntimeinfoisloadable-method"></a>Метод ICLRRuntimeInfo::IsLoadable
Указывает ли среда выполнения, связанных с этим интерфейсом могут быть загружены в текущий процесс, с учетом других сред выполнения, которые уже могут быть загружены в процесс.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbLoadable`  
 [out] `true` Если эта среда выполнения может быть загружена в текущем процессе; в противном случае `false`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|Параметр `pbLoadable` имеет значение null.|  
  
## <a name="remarks"></a>Примечания  
 Если в процесс уже загружена другая среда выполнения и среды выполнения, связанных с этим интерфейсом, которые могут быть загружены для выполнения-process side-by-side, `pbLoadable` возвращает `true`. Если две среды выполнения не может выполняться side-by-side в процессе, `pbLoadable` возвращает `false`. Например среда CLR (CLR) версии 4 можно запустить side-by-side, в том же процессе, в среде CLR версии 2.0 или среда CLR версии 1.1. Однако среда CLR версии 1.1 и среда CLR версии 2.0 не могут выполняться side-by-side в процессе.  
  
 Если нет сред выполнения загружаются в процесс, этот метод всегда возвращает `true`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MetaHost.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
