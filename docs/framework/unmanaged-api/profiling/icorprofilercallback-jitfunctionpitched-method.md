---
title: Метод ICorProfilerCallback::JITFunctionPitched
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b35605b4208953ae71d7eb4ba6b6384930952b2b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485100"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a>Метод ICorProfilerCallback::JITFunctionPitched
Уведомляет профилировщик, функция, которая была just-in-time (JIT)-компиляции был удален из памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionId`  
 [in] Идентификатор функции, который был удален.  
  
## <a name="remarks"></a>Примечания  
 При вызове удаленной функции, профилировщик получит новые события JIT-компиляции при ее повторной компиляции. В настоящее время компилятор JIT среды CLR не удаляет функции из памяти, поэтому этот обратный вызов в настоящее время не используется и не будут приниматься профилировщиком.  
  
 Значение `functionId` недопустима до ее повторной компиляции. Если функция перекомпилируется, же `functionId` значение будет использоваться.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
