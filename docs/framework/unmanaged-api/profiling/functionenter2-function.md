---
title: Функция FunctionEnter2
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
ms.openlocfilehash: f4deec3e2b49b5cd6a924af8024e775c5c549f97
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440859"
---
# <a name="functionenter2-function"></a>Функция FunctionEnter2
Уведомляет профилировщик о передаче управления в функцию и предоставляет сведения о кадре стека и аргументах функции. Эта функция заменяет функцию [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `funcId`  
 окне Идентификатор функции, которой передается элемент управления.  
  
 `clientData`  
 окне Идентификатор повторно сопоставленной функции, заданный ранее профилировщиком с помощью функции [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) .  
  
 `func`  
 окне Значение `COR_PRF_FRAME_INFO`, указывающее на сведения о кадре стека.  
  
 Профилировщик должен рассматривать это как непрозрачный маркер, который можно передать обратно в подсистему выполнения метода [ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) .  
  
 `argumentInfo`  
 окне Указатель на структуру [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) , указывающую расположения в памяти аргументов функции.  
  
 Чтобы получить доступ к сведениям об аргументах, необходимо установить флаг `COR_PRF_ENABLE_FUNCTION_ARGS`. Профилировщик может использовать метод [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) для установки флагов событий.  
  
## <a name="remarks"></a>Заметки  
 Значения параметров `func` и `argumentInfo` недопустимы после возврата функции `FunctionEnter2`, поскольку значения могут измениться или быть уничтожены.  
  
 Функция `FunctionEnter2` является обратным вызовом. его необходимо реализовать. Реализация должна использовать атрибут класса хранения `__declspec`(`naked`).  
  
 Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.  
  
- Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).  
  
- При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.  
  
 Реализация `FunctionEnter2` не должна блокироваться, так как она приведет к задержке сборки мусора. Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, понятном для сборки мусора. Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionEnter2`.  
  
 Кроме того, функция `FunctionEnter2` не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [Функция FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [Метод SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Глобальные статические функции профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
