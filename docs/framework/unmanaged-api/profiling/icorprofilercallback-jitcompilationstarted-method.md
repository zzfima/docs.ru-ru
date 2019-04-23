---
title: Метод ICorProfilerCallback::JITCompilationStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b75eebd8d9bf439a0317521a61c06ece3745be0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075325"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a>Метод ICorProfilerCallback::JITCompilationStarted
Уведомляет профилировщик, что компилятор just-in-time (JIT) начал компиляцию функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionId`  
 [in] Идентификатор функции, для которого выполняется запуск компиляции.  
  
 `fIsSafeToBlock`  
 [in] Значение, указывающее профилировщику ли блокировка повлияет на работу среды выполнения. Значение равно `true` Если блокировок может вызвать среды выполнения для вызывающего потока для возврата из этого обратного вызова; в противном случае `false`.  
  
 Несмотря на то что значение `true` не представляет угрозы для среды выполнения, он может исказить результаты профилирования.  
  
## <a name="remarks"></a>Примечания  
 Возможно, для получения более чем одну пару `JITCompilationStarted` и [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) вызывает для каждой функции из-за способа выполнения конструкторы класса дескрипторов. Например среда выполнения начинает JIT-компиляцию метода, но конструктор класса для класса B нужно выполнить. Таким образом, среда выполнения JIT-компиляцию конструктора для класса B и запускает его. Во время работы конструктора, он делает вызов метода А, который вызывает метод A, который нужно JIT-компиляции, чтобы снова. В этом случае первый JIT-компиляцию метода A прерывается. Тем не менее обе попытки JIT-компиляцию метода A выводятся с событиями JIT-компиляции. Если профилировщик будет заменить код на промежуточном языке (MSIL) для метода типа путем вызова [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) метод, она должна будет работать для обоих `JITCompilationStarted` события, но он может использовать того же блока MSIL для обоих ресурсов.  
  
 Профилировщики должны поддерживать последовательность обратных вызовов JIT в случаях, где два потока одновременно осуществляют обратных вызовов. Например, поток A вызывает `JITCompilationStarted`. Тем не менее, прежде чем поток A вызывает `JITCompilationFinished`, поток B вызывает [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) с Идентификатором потока A, который функция `JITCompilationStarted` обратного вызова. Может показаться, что идентификатор функции должно находиться допустимым так как вызов `JITCompilationFinished` еще не получил профилировщиком. Тем не менее в случае такого рода, идентификатор функции является допустимым.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Метод JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
