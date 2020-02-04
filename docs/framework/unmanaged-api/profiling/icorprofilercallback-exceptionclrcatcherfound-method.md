---
title: Метод ICorProfilerCallback::ExceptionCLRCatcherFound
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound method [.NET Framework profiling]
- ExceptionCLRCatcherFound method [.NET Framework profiling]
ms.assetid: 73fe8b4b-8f9a-4ba5-a10c-b26521396a66
topic_type:
- apiref
ms.openlocfilehash: a543e5119a3ad5580fb67c31dc0e59ab62eab571
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866496"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a>Метод ICorProfilerCallback::ExceptionCLRCatcherFound
Вызывается, когда блок `catch` для исключения находится внутри самой среды CLR. Этот метод является устаревшим в .NET Framework версии 2,0.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версия .NET Framework:** 1,0  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Метод ExceptionCLRCatcherExecute](icorprofilercallback-exceptionclrcatcherexecute-method.md)
