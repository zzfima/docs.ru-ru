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
ms.openlocfilehash: b52a0e7f993629c1005883723c734996d75300a7
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868438"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a>Метод ICorProfilerInfo4::InitializeCurrentThread
Инициализирует текущий поток перед последовательными вызовами API профилировщика в том же потоке, что позволяет избежать взаимоблокировки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a>Заметки  
 Рекомендуется вызывать `InitializeCurrentThread` в любом потоке, который будет вызывать API профилировщика при наличии приостановленных потоков. Этот метод обычно используется выборочными профилировщиками, которые создают собственный поток для вызова метода [ICorProfilerInfo2::D остаккснапшот](icorprofilerinfo2-dostacksnapshot-method.md) для выполнения проверки стека, пока целевой поток приостанавливается. Вызывая `InitializeCurrentThread` один раз, когда профилировщик сначала создает поток выборки, профилировщики могут гарантировать, что отложенная инициализация для каждого потока, которая в противном случае будет выполняться средой CLR во время первого вызова `DoStackSnapshot`, теперь может быть безопасно, когда другие потоки не будут приостановлены.  
  
> [!NOTE]
> `InitializeCurrentThread` выполняет инициализацию заранее для завершения задач, которые принимают блокировки и могут быть взаимоблокировками. Вызовите `InitializeCurrentThread`, только если нет приостановленных потоков.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo4](icorprofilerinfo4-interface.md)
- [Интерфейсы профилирования](profiling-interfaces.md)
- [Профилирование](index.md)
