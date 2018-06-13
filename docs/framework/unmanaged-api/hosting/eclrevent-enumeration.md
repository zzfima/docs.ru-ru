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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63d79b0c1fed0178f8463174fe981f250d6f6fb5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430711"
---
# <a name="eclrevent-enumeration"></a>Перечисление EClrEvent
Описывает распространенные события языка среды CLR, для которых узел может регистрировать обратные вызовы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`Event_ClrDisabled`|Задает неустранимую ошибку среды CLR.|  
|`Event_DomainUnload`|Задает, выгрузкой конкретной <xref:System.AppDomain>.|  
|`Event_MDAFired`|Указывает, что сообщение управляемого помощника по отладке (MDA) был создан.|  
|`Event_StackOverflow`|Указывает, что произошла ошибка переполнения стека.|  
  
## <a name="remarks"></a>Примечания  
 Узел может регистрировать обратные вызовы для любых типов событий, описываемого `EClrEvent` путем вызова методов [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) интерфейса. Узел получает указатель на этот интерфейс путем вызова [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) метод.  
  
 `Event_CLRDisabled` И `Event_DomainUnload` события может вызываться несколько раз и из разных потоков, чтобы сообщить о выгрузке или отключении среды CLR.  
  
 `Event_MDAFired` Событие вызывает создание [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) экземпляр, содержащий сведения о сообщении MDA. Дополнительные сведения о помощниках MDA см. в разделе [Диагностика ошибок посредством управляемых помощников по отладке](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [Интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
