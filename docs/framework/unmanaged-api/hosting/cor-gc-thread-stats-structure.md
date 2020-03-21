---
title: Структура COR_GC_THREAD_STATS
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS
helpviewer_keywords:
- COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type:
- apiref
ms.openlocfilehash: 64e0c466edcd8863244e6ed184c18422b5f66875
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178269"
---
# <a name="cor_gc_thread_stats-structure"></a>Структура COR_GC_THREAD_STATS
Содержит статистику по потоку, относящуюся к сбору мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a>Члены  
  
|Участник|Описание|  
|------------|-----------------|  
|`PerThreadAllocation`|Количество байтов памяти, выделенных на потоке, связанном с текущим `COR_GC_THREAD_STATS` экземпляром. Это число очищается до нуля каждый раз, когда происходит сбор мусора с нулевым поколением.|  
|`Flags`|Количество байтов, повышенных до более высокого поколения на последнем сборе мусора.|  
  
## <a name="remarks"></a>Remarks  
 [ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) принимает выходный `COR_GC_THREAD_STATS`параметр типа.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** GCHost.idl  
  
 **Библиотека:** Включено в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
