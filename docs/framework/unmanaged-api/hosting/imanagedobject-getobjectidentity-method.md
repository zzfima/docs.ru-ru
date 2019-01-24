---
title: Метод IManagedObject::GetObjectIdentity
ms.date: 03/30/2017
api_name:
- IManagedObject.GetObjectIdentity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3fbc4abe55d59c3140c5c180d5844404e357e3a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586316"
---
# <a name="imanagedobjectgetobjectidentity-method"></a>Метод IManagedObject::GetObjectIdentity
Получает идентификатор данного управляемого объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pBSTRGUID`  
 [out] Указатель на идентификатор GUID процесса, в котором размещен объект.  
  
 `AppDomainID`  
 [out] Указатель на идентификатор объекта домена приложения.  
  
 `pCCW`  
 [out] Указатель на индекс объекта в классической виртуальной таблице COM.  
  
## <a name="remarks"></a>Примечания  
 Идентификатор управляемого объекта включает GUID процесса, идентификатор домена приложения и индексу объекта в классической виртуальной таблице COM.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IManagedObject](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
