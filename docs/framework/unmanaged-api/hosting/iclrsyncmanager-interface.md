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
ms.openlocfilehash: 4b949466c5557415ec06bac601380675beed7fd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549867"
---
# <a name="iclrsyncmanager-interface"></a>Интерфейс ICLRSyncManager
Определяет методы, позволяющие узла для получения сведений о запрошенных задач и для выявления взаимоблокировок в реализации синхронизации.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md)|Запросы, которые среда CLR (CLR) создают итератор для узла для определения набора задач, ожидающих блокировки чтения и записи.|  
|[Метод DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md)|Запрашивает, что среда CLR уничтожить итератор, который был создан с помощью вызова `CreateRWLockOwnerIterator`.|  
|[Метод GetMonitorOwner](iclrsyncmanager-getmonitorowner-method.md)|Получает задачу, которой принадлежит указанный монитор.|  
|[Метод GetRWLockOwnerNext](iclrsyncmanager-getrwlockownernext-method.md)|Получает следующую задачу, ожидающую текущей блокировки чтения и записи.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Threading.Thread>
- [Интерфейс IHostSyncManager](ihostsyncmanager-interface.md)
- [Управляемые и неуправляемые потоки](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))
- [Интерфейсы размещения](hosting-interfaces.md)
