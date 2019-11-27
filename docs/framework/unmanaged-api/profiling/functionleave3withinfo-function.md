---
title: Функция FunctionLeave3WithInfo
ms.date: 03/30/2017
api_name:
- FunctionLeave3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3WithInfo
helpviewer_keywords:
- FunctionLeave3WithInfo function [.NET Framework profiling]
ms.assetid: 5fa68a67-ced6-41c6-a2c0-467060fd0692
topic_type:
- apiref
ms.openlocfilehash: a62f402fbfae6188ab0423ea7a55a4dfc6cb4112
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427399"
---
# <a name="functionleave3withinfo-function"></a>Функция FunctionLeave3WithInfo
Уведомляет профилировщик о том, что управление возвращается из функции, и предоставляет маркер, который может быть передан [методу ICorProfilerInfo3:: GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) для получения кадра стека и возвращаемого значения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionIDOrClientID`  
 окне Идентификатор функции, из которой возвращается элемент управления.  
  
 `eltInfo`  
 [in] Непрозрачный дескриптор, представляющий сведения об указанном кадре стека. Этот маркер действителен только во время обратного вызова, к которому он передается.  
  
## <a name="remarks"></a>Заметки  
 Метод обратного вызова `FunctionLeave3WithInfo` уведомляет профилировщик о вызове функций и позволяет профилировщику использовать [метод ICorProfilerInfo3:: GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) для проверки возвращаемого значения. Чтобы получить доступ к сведениям о возвращаемом значении, необходимо установить флаг `COR_PRF_ENABLE_FUNCTION_RETVAL`. Профилировщик может использовать [метод ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) для установки флагов событий, а затем использовать [метод ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) для регистрации реализации этой функции.  
  
 Функция `FunctionLeave3WithInfo` является обратным вызовом. его необходимо реализовать. Реализация должна использовать атрибут класса хранения `__declspec(naked)`.  
  
 Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.  
  
- Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).  
  
- При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.  
  
 Реализация `FunctionLeave3WithInfo` не должна блокироваться, так как она приведет к задержке сборки мусора. Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, удобном для сборки мусора. Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionLeave3WithInfo`.  
  
 Функция `FunctionLeave3WithInfo` не должна вызывать управляемый код или вызывать управляемое выделение памяти каким-либо образом.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)
- [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [SetFunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [Глобальные статические функции профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
