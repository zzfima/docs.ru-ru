---
title: Метод IGCHost::SetGCStartupLimits
ms.date: 03/30/2017
api_name:
- IGCHost.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83a1c03c209d68035b3615c83ec0ee13b94eb549
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54719954"
---
# <a name="igchostsetgcstartuplimits-method"></a>Метод IGCHost::SetGCStartupLimits
Задает размер сегмента и максимальный размер для поколения 0.  
  
> [!IMPORTANT]
>  Начиная с [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], можно задать размер сегмента и максимально возможного поколения 0 размер значения больше, чем `DWORD` с помощью [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `SegmentSize`  
 [in] Размер сегмента, используемой системой сбора мусора.  
  
 `MaxGen0Size`  
 [in] Максимальный размер поколения 0.  
  
## <a name="remarks"></a>Примечания  
 `SetGCStartupLimits` Метод может вызываться только один раз. Эти значения нельзя изменить позже.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** GCHost.idl GCHost.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IGCHost](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
