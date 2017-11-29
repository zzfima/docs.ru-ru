---
title: "Интерфейс IHostMalloc"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMAlloc
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMAlloc
helpviewer_keywords: IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f788456065a5508441b9fec38ad4a7f531f9f303
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmalloc-interface"></a>Интерфейс IHostMalloc
Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR) для выделения точного количества памяти из кучи посредством узла.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Alloc-метод](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|Запрашивает у узла выделение запрошенного объема памяти из кучи.|  
|[DebugAlloc-метод](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|Запрашивает выделение запрошенного объема памяти из кучи основное и дополнительное отслеживание, где была выделена память.|  
|[Free-метод](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|Освобождает память, выделенную с помощью `Alloc` метод.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR возвращает указатель интерфейса `IHostMalloc` экземпляр путем вызова [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IHostMemoryManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
