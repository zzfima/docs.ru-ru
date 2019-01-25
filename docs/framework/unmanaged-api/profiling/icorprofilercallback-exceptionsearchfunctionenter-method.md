---
title: Метод ICorProfilerCallback::ExceptionSearchFunctionEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionEnter
helpviewer_keywords:
- ExceptionSearchFunctionEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionEnter method [.NET Framework profiling]
ms.assetid: bfd54573-b7e6-4bd1-a184-7f08a8b39fae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c2f27eccc506ce7145b383132260ad4e470f8906
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519233"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a>Метод ICorProfilerCallback::ExceptionSearchFunctionEnter
Уведомляет профилировщик о начале этапа поиска обработки исключений поиск функции с целью найти обработчик для текущего исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a>Параметры  
 `functionId`  
 [in] Идентификатор функции, которая была введена.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Метод ExceptionSearchFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)
