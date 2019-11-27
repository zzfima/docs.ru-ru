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
ms.openlocfilehash: 9bb3934be4a2f4de4a3a235a00522c801331e1eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448428"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a>Метод ICorProfilerCallback::JITFunctionPitched
Оповещает профилировщик о том, что JIT-скомпилированная функция была удалена из памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionId`  
 окне Идентификатор удаленной функции.  
  
## <a name="remarks"></a>Примечания  
 Если вызывается Удаленная функция, профилировщик получит новые события JIT-компиляции при повторной компиляции функции. В настоящее время JIT-компилятор среды CLR не удаляет функции из памяти, поэтому этот обратный вызов сейчас не используется и не будет получен профилировщиком.  
  
 Значение `functionId` недопустимо, пока функция не будет перекомпилирована. При повторной компиляции функции будет использоваться то же значение `functionId`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
