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
ms.openlocfilehash: 1fa1081afc77c8116d8858c187401555409b4dcd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a>Метод ICorProfilerCallback::JITCompilationStarted
Уведомляет профилировщик о начале just-in-time (JIT) компилятор для компиляции функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a>Параметры  
 `functionId`  
 [in] Идентификатор функции, для которого запускается компиляции.  
  
 `fIsSafeToBlock`  
 [in] Значение, указывающее профилировщику ли блокировка будет влиять на работу среды выполнения. Значение равно `true` Если блокировок может вызвать среды выполнения для ожидания вызывающего потока для возврата из этого обратного вызова; в противном случае `false`.  
  
 Несмотря на то что значение `true` не представляет угрозы для среды выполнения, он может исказить результаты профилирования.  
  
## <a name="remarks"></a>Примечания  
 Можно получить более чем одну пару `JITCompilationStarted` и [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) вызывает для каждой функции из-за способа среда выполнения обрабатывает класс конструкторы. Например среда выполнения начинает JIT-компиляции метода типа, но конструктор класса для класса B должна быть запущена. Таким образом, среда выполнения JIT-компиляцию конструктора для класса B и запускает его. Пока конструктор работает, он вызывает метод A, вследствие чего метода для JIT-компиляции еще раз. В этом сценарии первая JIT-компиляция метода A прерывается. Тем не менее обе попытки JIT-компиляции метода A выводятся с событиями JIT-компиляции. Если профилировщик будет заменить код на промежуточном языке (MSIL) для метода типа путем вызова [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) метод, необходимо сделать для обоих `JITCompilationStarted` события, но он может использовать того же блока MSIL для обоих.  
  
 Профилировщики должны поддерживать последовательность обратных вызовов JIT в случаях, где два потока одновременно осуществляют обратные вызовы. Например, поток A вызывает `JITCompilationStarted`. Тем не менее, прежде чем поток A вызывает метод `JITCompilationFinished`, поток B вызывает метод [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) с Идентификатором функция потоком `JITCompilationStarted` обратного вызова. Кажется, что идентификатор функции должно находиться допустимым из-за вызова `JITCompilationFinished` еще не получил профилировщиком. Однако в случае такого рода, идентификатор функции является допустимым.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Метод JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
