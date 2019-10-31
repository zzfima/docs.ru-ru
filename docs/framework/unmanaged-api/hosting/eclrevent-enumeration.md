---
title: Перечисление EClrEvent
ms.date: 03/30/2017
api_name:
- EClrEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrEvent
helpviewer_keywords:
- EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type:
- apiref
ms.openlocfilehash: ee749fd40f440e92f1d1b09c2ea5e7bdd51f1cbe
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131138"
---
# <a name="eclrevent-enumeration"></a>Перечисление EClrEvent
Описывает события среды CLR, для которых узел может регистрировать обратные вызовы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`Event_ClrDisabled`|Указывает неустранимую ошибку среды CLR.|  
|`Event_DomainUnload`|Задает выгрузку конкретного <xref:System.AppDomain>.|  
|`Event_MDAFired`|Указывает, что создано сообщение помощника по отладке управляемого кода (MDA).|  
|`Event_StackOverflow`|Указывает, что произошла ошибка переполнения стека.|  
  
## <a name="remarks"></a>Заметки  
 Узел может регистрировать обратные вызовы для любого из типов событий, описываемых `EClrEvent` путем вызова методов интерфейса [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) . Узел получает указатель на этот интерфейс путем вызова метода [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) .  
  
 События `Event_CLRDisabled` и `Event_DomainUnload` могут вызываться более одного раза и из разных потоков для сигнализации выгрузки или отключения среды CLR.  
  
 Событие `Event_MDAFired` вызывает создание экземпляра [мдаинфо](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) , содержащего подробные сведения о сообщении MDA. Дополнительные сведения о помощниках MDA см. в разделе [Диагностика ошибок с помощью помощников по отладке управляемого](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [Интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
