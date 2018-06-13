---
title: Перечисление ETaskType
ms.date: 03/30/2017
api_name:
- ETaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ETaskType
helpviewer_keywords:
- ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c8609857f142000245aef4326c8ef7490e6d4c95
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430600"
---
# <a name="etasktype-enumeration"></a>Перечисление ETaskType
Содержит значения, указывающие тип задачи, представленного либо [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) или [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`TT_ADUNLOAD`|Интерфейс представляет задачу выгрузки домена приложения.|  
|`TT_DEBUGGERHELPER`|Интерфейс представляет вспомогательную задачу отладчика.|  
|`TT_FINALIZER`|Интерфейс представляет задачу метода завершения.|  
|`TT_GC`|Интерфейс представляет задачу сборки мусора.|  
|`TT_THREADPOOL_GATE`|Интерфейс представляет задачу потока логического.|  
|`TT_THREADPOOL_IOCOMPLETION`|Интерфейс представляет задачу потока ввода-вывода или задачу потока порта завершения.|  
|`TT_THREADPOOL_TIMER`|Интерфейс представляет задачу потока таймера.|  
|`TT_THREADPOOL_WAIT`|Интерфейс представляет задачу потока ожидания.|  
|`TT_THREADPOOL_WORKER`|Интерфейс представляет задачу рабочего потока.|  
|`TT_UNKNOWN`|Задача неизвестна.|  
|`TT_USER`|Интерфейс представляет задачу пользователя.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
