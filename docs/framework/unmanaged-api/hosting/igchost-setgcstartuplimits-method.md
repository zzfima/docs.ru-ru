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
ms.openlocfilehash: 87ba947b9564f82f8daf8cd2ba0acac5cc3587ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928664"
---
# <a name="igchostsetgcstartuplimits-method"></a>Метод IGCHost::SetGCStartupLimits
Задает размер сегмента и максимальный размер для поколения 0.  
  
> [!IMPORTANT]
> Начиная с .NET Framework 4,5 можно задать размер сегмента и максимальный размер поколения 0 в значениях `DWORD` , превышающих использование метода [IGCHost2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `SegmentSize`  
 окне Размер сегмента, используемого системой сборки мусора.  
  
 `MaxGen0Size`  
 окне Максимальный размер для поколения 0.  
  
## <a name="remarks"></a>Примечания  
 `SetGCStartupLimits` Метод может быть вызван только один раз. Эти значения нельзя изменить позже.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Гчост. idl, Гчост. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IGCHost](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
