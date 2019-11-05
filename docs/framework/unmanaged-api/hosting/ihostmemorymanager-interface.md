---
title: Интерфейс IHostMemoryManager
ms.date: 03/30/2017
api_name:
- IHostMemoryManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager
helpviewer_keywords:
- IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type:
- apiref
ms.openlocfilehash: bc05d76795f20d28d6d2899d61dc4674ebfdca8c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128652"
---
# <a name="ihostmemorymanager-interface"></a>Интерфейс IHostMemoryManager
Предоставляет методы, позволяющие среде CLR выполнять запросы к виртуальной памяти через основное приложение вместо использования стандартных функций виртуальной памяти Win32.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод AcquiredVirtualAddressSpace](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|Уведомляет узел о том, что среда CLR получила указанную память из операционной системы.|  
|[Метод CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|Возвращает указатель интерфейса на экземпляр [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) , который используется для запроса выделения памяти из кучи, созданного узлом.|  
|[Метод GetMemoryLoad](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|Возвращает объем используемой в данный момент физической памяти, сообщаемой узлом.|  
|[Метод NeedsVirtualAddressSpace](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|Уведомляет узел о том, что среда CLR будет пытаться использовать указанную память.|  
|[Метод RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|Регистрирует указатель на функцию обратного вызова, которая вызывается хостом для уведомления среды CLR о текущей загрузке памяти на компьютере.|  
|[Метод ReleasedVirtualAddressSpace](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|Уведомляет узел о том, что среда CLR завершила работу с заданной памятью.|  
|[Метод VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|Служит логической оболочкой для соответствующей функции Win32, которая резервирует или фиксирует область страниц в виртуальном адресном пространстве вызывающего процесса.|  
|[Метод VirtualFree](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|Служит логической оболочкой для соответствующей функции Win32, которая выдает, выдает или освобождает и отменяет выделение области страниц в виртуальном адресном пространстве вызывающего процесса.|  
|[Метод VirtualProtect](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|Служит логической оболочкой для соответствующей функции Win32, которая изменяет защиту в области зафиксированных страниц в виртуальном адресном пространстве вызывающего процесса.|  
|[Метод VirtualQuery](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|Служит логической оболочкой для соответствующей функции Win32, которая получает сведения о диапазоне страниц в виртуальном адресном пространстве вызывающего процесса.|  
  
## <a name="remarks"></a>Заметки  
 `IHostMemoryManager` также предоставляет методам среды CLR возможность получить указатель, с помощью которого можно сделать запросы к памяти в куче и получить уровень нехватки памяти в процессе, сообщаемый узлом.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
