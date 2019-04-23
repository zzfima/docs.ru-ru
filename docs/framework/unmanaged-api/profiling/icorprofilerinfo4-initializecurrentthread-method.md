---
title: Метод ICorProfilerInfo4::InitializeCurrentThread
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9fd0900e61c57d105439d83430284dc8634d2a1e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223606"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a>Метод ICorProfilerInfo4::InitializeCurrentThread
Инициализирует текущий поток до последующих вызовов API в одном потоке, поэтому можно избежать этой взаимоблокировки профилировщика.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a>Примечания  
 Мы рекомендуем вызывать `InitializeCurrentThread` в любом потоке, который будет вызывать профилировщик API, несмотря на наличие приостановки потоков. Этот метод обычно используется выборочными профилировщиками, которые создают собственные потоку на вызов метода [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) способ выполнения стека проходит, когда целевой поток приостановлен. Путем вызова `InitializeCurrentThread` после Когда профилировщик сначала создает поток выборки, средства профилирования можно обеспечить инициализации отложенной поток, в противном случае среда CLR выполнит во время первого вызова `DoStackSnapshot` теперь можно выполнять безопасно когда нет других потоков, Состояние приостановки.  
  
> [!NOTE]
>  `InitializeCurrentThread` производит инициализацию заранее, чтобы завершить задачи, которые принимают блокировок и может принимать участие во взаимоблокировке. Вызовите `InitializeCurrentThread` только в том случае, если нет приостановленных потоков.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
