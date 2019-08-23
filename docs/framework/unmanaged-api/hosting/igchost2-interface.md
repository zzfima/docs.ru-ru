---
title: Интерфейс IGCHost2
ms.date: 03/30/2017
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21ce9cbd007858c0f39e12622eff819154ab83f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928621"
---
# <a name="igchost2-interface"></a>Интерфейс IGCHost2
Предоставляет методы для получения сведений о системе сборки мусора и для управления некоторыми аспектами сборки мусора.  
  
> [!NOTE]
> Для новой разработки рекомендуется вместо этого использовать интерфейс [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) .  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|Задает размер сегмента и максимальный размер для поколения 0. Включает поколение 0 и размеры сегментов, превышающие `DWORD`.|  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Гчост. idl, Гчост. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Интерфейсы размещения CLR](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [Кокласс CorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
