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
ms.openlocfilehash: abc6cca185b318be016f92ac8c97d21f7af5940a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136779"
---
# <a name="ihostmalloc-interface"></a>Интерфейс IHostMalloc
Предоставляет методы, позволяющие среде CLR запрашивать детализированные выделения из кучи через узел.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|Запрашивает у узла выделение запрошенного объема памяти из кучи.|  
|[Метод DebugAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|Запрашивает, что узел выделяет запрошенный объем памяти из кучи, и дополнительно следит за местом выделения памяти.|  
|[Метод Free](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|Освобождает память, выделенную с помощью метода `Alloc`.|  
  
## <a name="remarks"></a>Заметки  
 Среда CLR получает указатель интерфейса на экземпляр `IHostMalloc`, вызывая метод [IHostMemoryManager:: CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
