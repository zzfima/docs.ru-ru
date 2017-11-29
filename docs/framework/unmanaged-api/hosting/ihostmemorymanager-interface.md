---
title: "Интерфейс IHostMemoryManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager
helpviewer_keywords: IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 415539be0dbed8e0cf3f9d6e5c79bf4cfac09fe2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmemorymanager-interface"></a>Интерфейс IHostMemoryManager
Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR), чтобы запросы виртуальной памяти через узел, вместо использования стандартных функций Win32 виртуальной памяти.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Acquiredvirtualaddressspace-метод](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|Уведомляет узел, что общеязыковой среды выполнения (CLR) получила указанную память от операционной системы.|  
|[Метод CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|Возвращает указатель интерфейса [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) экземпляр, используемый для запроса выделения памяти из кучи, созданные узлом.|  
|[Getmemoryload-метод](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|Возвращает объем физической памяти, используемой в данный момент, о котором сообщает узла.|  
|[NeedsVirtualAddressSpace-метод](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|Уведомляет основное приложение, среда CLR будет пытаться использовать указанный объем памяти.|  
|[Registermemorynotificationcallback-метод](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|Регистрирует указатель на функцию обратного вызова, который основное приложение вызывает для уведомления среды CLR о текущей загруженности памяти на компьютере.|  
|[Releasedvirtualaddressspace-метод](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|Уведомляет узел, что среда CLR завершила использование указанной памяти.|  
|[VirtualAlloc-метод](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|Служит в качестве логической программой-оболочкой для соответствующей функции Win32, которая резервирует или фиксирует диапазон страниц в виртуальном адресном пространстве вызывающего процесса.|  
|[VirtualFree-метод](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|Служит в качестве логической программой-оболочкой для соответствующей функции Win32, которая освобождает, разблокирует или освобождает и разблокирует диапазон страниц в пределах виртуального адресного пространства вызывающего процесса.|  
|[VirtualProtect-метод](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|Служит в качестве логической программой-оболочкой для соответствующей функции Win32, которая изменяет защиту в области зафиксированных страниц в виртуальном адресном пространстве вызывающего процесса.|  
|[VirtualQuery-метод](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|Служит в качестве логической программой-оболочкой для соответствующей функции Win32, которая получает сведения о диапазоне страниц в виртуальном адресном пространстве вызывающего процесса.|  
  
## <a name="remarks"></a>Примечания  
 `IHostMemoryManager`также предоставляет методы для среды CLR получить указатель, посредством которого можно осуществлять запросы памяти в куче и получать уровень нехватки памяти в процессе, предоставленным узлом.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IHostMalloc-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
