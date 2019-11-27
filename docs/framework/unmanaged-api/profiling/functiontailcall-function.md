---
title: Функция FunctionTailcall
ms.date: 03/30/2017
api_name:
- FunctionTailcall
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall
helpviewer_keywords:
- FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type:
- apiref
ms.openlocfilehash: c83a55a74542d94559b50b89ef784de0bd55d0db
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427346"
---
# <a name="functiontailcall-function"></a>Функция FunctionTailcall
Уведомляет профилировщик о том, что выполняемая в данный момент функция собирается выполнить вызов другой функции с префиксом tail.  
  
> [!NOTE]
> Функция `FunctionTailcall` устарела в .NET Framework версии 2,0. Он будет продолжать работать, но будет приводить к снижению производительности. Вместо этого используйте функцию [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `funcID`  
 окне Идентификатор выполняемой в данный момент функции, которая собирается выполнить вызов с префиксом tail.  
  
## <a name="remarks"></a>Заметки  
 Целевая функция вызова с префиксом tail будет использовать текущий кадр стека и будет возвращаться непосредственно вызывающему объекту функции, которая выполнила вызов с префиксом tail. Это означает, что обратный вызов [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) не будет выдаваться для функции, которая является целевым объектом для вызова с префиксом tail.  
  
 Функция `FunctionTailcall` является обратным вызовом. его необходимо реализовать. Реализация должна использовать атрибут класса хранения `__declspec`(`naked`).  
  
 Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.  
  
- Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).  
  
- При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.  
  
 Реализация `FunctionTailcall` не должна блокироваться, так как она приведет к задержке сборки мусора. Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, понятном для сборки мусора. Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionTailcall`.  
  
 Кроме того, функция `FunctionTailcall` не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:** 1,1, 1,0  
  
## <a name="see-also"></a>См. также

- [Функция FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [Функция FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [Метод SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Глобальные статические функции профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
