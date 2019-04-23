---
title: Интерфейс IHostMalloc
ms.date: 03/30/2017
api_name:
- IHostMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc
helpviewer_keywords:
- IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2a7a29ef1dc85c2ad554995286e5137fcb104be
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136418"
---
# <a name="ihostmalloc-interface"></a>Интерфейс IHostMalloc
Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR), для выделения точного количества памяти из кучи через узел.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|Запрашивает выделение узла запрошенного объема памяти из кучи.|  
|[Метод DebugAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|Запрашивает, что узел выделение запрошенного объема памяти из кучи и Кроме того, отслеживать, где была выделена память.|  
|[Метод Free](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|Освобождает память, выделенную с помощью `Alloc` метод.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR получает указатель интерфейса на `IHostMalloc` экземпляра путем вызова [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
