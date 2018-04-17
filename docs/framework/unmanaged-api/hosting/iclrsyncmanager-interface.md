---
title: Интерфейс ICLRSyncManager
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 17a1e3073713b54cb7a68e6ba3ef2562d4fbcaeb
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="iclrsyncmanager-interface"></a>Интерфейс ICLRSyncManager
Определяет методы, позволяющие узла, чтобы получить сведения о запрашиваемых задачах и взаимоблокировки в реализации синхронизации.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md)|Запросы, которые общеязыковой среды выполнения (CLR) создают итератор для узла, который используется для определения набора задач, ожидающих блокировки чтения записи.|  
|[Метод DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md)|Запросы, что среда CLR уничтожить итератор, который был создан с помощью вызова `CreateRWLockOwnerIterator`.|  
|[Метод GetMonitorOwner](iclrsyncmanager-getmonitorowner-method.md)|Возвращает задачу, которой принадлежит указанный монитор.|  
|[Метод GetRWLockOwnerNext](iclrsyncmanager-getrwlockownernext-method.md)|Получает следующую задачу, ожидающих блокировки чтения записи.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Thread>  
 [Интерфейс IHostSyncManager](ihostsyncmanager-interface.md)  
 [Управляемые и неуправляемые потоки](https://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5(v=vs.100))  
 [Интерфейсы размещения](hosting-interfaces.md)
