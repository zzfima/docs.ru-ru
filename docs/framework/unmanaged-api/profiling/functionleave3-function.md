---
title: "Функция FunctionLeave3"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionLeave3
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionLeave3
helpviewer_keywords: FunctionLeave3 function [.NET Framework profiling]
ms.assetid: 5d798088-7992-48a0-ae55-d2a7ee31913f
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 11aa67a03cfb88910704c0f1d2f586f8dbed7d52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="functionleave3-function"></a>Функция FunctionLeave3
Уведомляет профилировщик о том, что элемент управления возвращается из функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
#### <a name="parameters"></a>Параметры  
 `functionOrRemappedID`  
 [in] Идентификатор функции, из которого возвращается.  
  
## <a name="remarks"></a>Примечания  
 `FunctionLeave3` Функция обратного вызова Уведомляет профилировщик при вызове функции, но не поддерживает проверку возвращаемого значения. Используйте [метод ICorProfilerInfo3::SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) для регистрации реализации этой функции.  
  
 `FunctionLeave3` Функция является обратным вызовом, необходимо произвести его. В реализации должен использоваться `__declspec(naked)` атрибут класса хранения.  
  
 Перед вызовом этой функции ядро выполнения не сохраняет значения регистров.  
  
-   При входе необходимо сохранить все используемые регистры, включая те, в единицах измерения с плавающей запятой (FPU).  
  
-   При выходе необходимо восстановить стек путем выталкивания из всех параметров, переведенных вызывающим кодом.  
  
 Реализация `FunctionLeave3` не должен блокироваться, поскольку это приведет к задержке сборки мусора. Реализация не должны предпринимать попытки сбора мусора, так как стек может находиться в состоянии понятного имени сбора мусора. При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionLeave3` возвращает.  
  
 `FunctionLeave3` Функция не должна вызывать управляемый код или вызвать распределения управляемой памяти каким-либо образом.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [SetFunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [Глобальные статические функции профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
