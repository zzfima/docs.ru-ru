---
title: Интерфейс ICLRIoCompletionManager
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
ms.openlocfilehash: b63d4269a8d48ee49016a4c51d63bf81bdba8da2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141028"
---
# <a name="iclriocompletionmanager-interface"></a>Интерфейс ICLRIoCompletionManager
Реализует метод обратного вызова, который позволяет узлу уведомлять среду CLR о состоянии указанных запросов ввода-вывода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|Сообщает среде CLR о состоянии запроса ввода-вывода, сделанного с помощью вызова метода [IHostIoCompletionManager:: BIND](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) .|  
  
## <a name="remarks"></a>Заметки  
 Узел реализует абстракцию завершения ввода-вывода с помощью интерфейса [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) . Среда CLR делает запросы ввода-вывода через этот интерфейс, и узел уведомляет среду выполнения о результатах таких запросов с помощью интерфейса `ICLRIoCompletionManager`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [Интерфейс IHostThreadPoolManager](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
