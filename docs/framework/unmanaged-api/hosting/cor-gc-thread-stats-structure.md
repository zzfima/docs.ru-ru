---
title: "Структура COR_GC_THREAD_STATS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_THREAD_STATS
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_GC_THREAD_STATS
helpviewer_keywords: COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10366d183ed7fd7386609e4c5726df0cea4e29a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="corgcthreadstats-structure"></a>Структура COR_GC_THREAD_STATS
Содержит статистику потоков сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`PerThreadAllocation`|Число байтов памяти, выделенной в потоке, который связан с текущим `COR_GC_THREAD_STATS` экземпляра. Это число обнуляется каждый раз, когда выполняется сборка мусора нулевого поколения.|  
|`Flags`|Число байтов продвигаются в поколение более высокого уровня при самой последней сборки мусора.|  
  
## <a name="remarks"></a>Примечания  
 [ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) принимает выходной параметр типа `COR_GC_THREAD_STATS`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** GCHost.idl  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Структуры размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [IHostTask-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
