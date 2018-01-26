---
title: "Метод ICorProfilerCallback4::ReJITCompilationStarted"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.ReJITCompilationStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 903db06089f7c68843b503c94483087ff9fce636
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>Метод ICorProfilerCallback4::ReJITCompilationStarted
Уведомляет профилировщик, что компилятор just-in-time (JIT) запущена в повторной компиляции функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ReJITCompilationStarted(    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a>Параметры  
 `functionId`  
 [in] Идентификатор функции, начатое JIT-компилятором для перекомпиляции.  
  
 `rejitId`  
 [in] Повторная компиляция идентификатор новой версии функции.  
  
 `fIsSafeToBlock`  
 [in] `true` для указания, что блокировка может послужить причиной среды выполнения для ожидания вызывающего потока для возврата из этого обратного вызова; `false` для указания, что блокировка не повлияет на работу среды выполнения. Значение `true` не представляет угрозы для среды выполнения, но может повлиять на результаты профилирования.  
  
## <a name="remarks"></a>Примечания  
 Можно получить более чем одну пару `ReJITCompilationStarted` и [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) метод вызывает для каждой функции из-за способа выполнения конструкторы класса дескрипторов. Например среда выполнения начинает перекомпилировать метод A, но конструктор класса для класса B должна быть запущена. Таким образом среда выполнения повторных компиляций конструктора для класса B и запускает его. Пока конструктор работает, он вызывает метод A, вызывая метод A попытку повторной компиляции. В этом случае перекомпиляция первый метод A прерывается. Тем не менее оба предпринимается попытка повторной компиляции метода являются этот отчет события перекомпиляции JIT-компилятора.  
  
 Профилировщики должны поддерживать последовательность обратных вызовов для перекомпиляции JIT в случаях, где два потока одновременно осуществляют обратные вызовы. Например, поток A вызывает `ReJITCompilationStarted`; тем не менее, прежде чем поток A вызывает метод [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), поток B вызывает метод [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) с идентификатор функции из `ReJITCompilationStarted` обратного вызова для потока, а. Кажется, что идентификатор функции должно находиться допустимым из-за вызова [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) еще не получил профилировщиком. Однако в этом случае идентификатор функции является допустимым.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Интерфейс ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [Метод JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)  
 [Метод ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
