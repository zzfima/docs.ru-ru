---
title: "Метод ICLRRuntimeInfo::IsLoadable"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.IsLoadable
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ada33942af97f476de25c2ea3243818808e2dc9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfoisloadable-method"></a>Метод ICLRRuntimeInfo::IsLoadable
Указывает, возможна ли загрузка среды выполнения, связанных с этим интерфейсом в текущий процесс, принимая во внимание других сред выполнения, которые уже могли быть загружены в процесс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pbLoadable`  
 [out] `true` Если эта среда выполнения может быть загружена в текущем процессе; в противном случае — `false`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|Параметр `pbLoadable` имеет значение NULL.|  
  
## <a name="remarks"></a>Примечания  
 Если в процесс уже загружена другая среда выполнения, среда выполнения, связанных с этим интерфейсом можно загрузить для выполнения в процессе side-by-side `pbLoadable` возвращает `true`. Если две среды выполнения не может выполнять side-by-side в процессе, `pbLoadable` возвращает `false`. Например среда CLR версии 4 можно запустить side-by-side, в том же процессе, в среде CLR версии 2.0 или среда CLR версии 1.1. Тем не менее среда CLR версии 1.1 и среда CLR версии 2.0 не может выполняться side-by-side внутри процесса.  
  
 Если нет сред выполнения, загружаются в процесс, этот метод всегда возвращает `true`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICLRRuntimeInfo-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
