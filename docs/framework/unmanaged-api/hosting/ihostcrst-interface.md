---
title: "Интерфейс IHostCrst"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3a9ed2b390ad741d90f9179ef5101d328d3b639d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcrst-interface"></a>Интерфейс IHostCrst
Служит в качестве узла представления критической секции для работы с потоками.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод Enter](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|Переходит в критической секции.|  
|[Метод Leave](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|Покидает критическую секцию.|  
|[Метод SetSpinCount](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|Задает счетчик прокруток для критической секции.|  
|[Метод TryEnter](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|Пытается ввести критическую секцию и сообщает об успехе или сбоя немедленно.|  
  
## <a name="remarks"></a>Примечания  
 `IHostCrst`позволяет общеязыковой среды выполнения (CLR) для взаимодействия непосредственно с представлением узла критическую секцию, а не с помощью функций Win32, таких как `EnterCriticalSection` или `LeaveCriticalSection`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [Интерфейс IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
