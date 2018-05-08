---
title: Интерфейс ICLRSyncManager
ms.date: 03/30/2017
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
ms.openlocfilehash: 1b87ccc3d6c3e957d0384499048032e35247093a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
