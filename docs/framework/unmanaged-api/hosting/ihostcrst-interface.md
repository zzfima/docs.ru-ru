---
title: "Интерфейс IHostCrst"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst
helpviewer_keywords: IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 59485d7a642ba8b3233d5d077062e89fb2ac9b14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrst-interface"></a>Интерфейс IHostCrst
Служит в качестве узла представления критической секции для работы с потоками.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[ENTER-метод](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|Переходит в критической секции.|  
|[Leave-метод](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|Покидает критическую секцию.|  
|[Setspincount-метод](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|Задает счетчик прокруток для критической секции.|  
|[TryEnter-метод](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|Пытается ввести критическую секцию и сообщает об успехе или сбоя немедленно.|  
  
## <a name="remarks"></a>Примечания  
 `IHostCrst`позволяет общеязыковой среды выполнения (CLR) для взаимодействия непосредственно с представлением узла критическую секцию, а не с помощью функций Win32, таких как `EnterCriticalSection` или `LeaveCriticalSection`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICLRSyncManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [Ihostsyncmanager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
