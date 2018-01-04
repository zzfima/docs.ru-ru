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
ms.workload: dotnet
ms.openlocfilehash: e1690f5fe8f1417e6547ed94db8c71f079ebf5e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmalloc-interface"></a>Интерфейс IHostMalloc
Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR) для выделения точного количества памяти из кучи посредством узла.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|Запрашивает у узла выделение запрошенного объема памяти из кучи.|  
|[Метод DebugAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|Запрашивает выделение запрошенного объема памяти из кучи основное и дополнительное отслеживание, где была выделена память.|  
|[Метод Free](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|Освобождает память, выделенную с помощью `Alloc` метод.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR возвращает указатель интерфейса `IHostMalloc` экземпляр путем вызова [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
