---
title: Функция FunctionEnter
ms.date: 03/30/2017
api_name:
- FunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter
helpviewer_keywords:
- FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type:
- apiref
ms.openlocfilehash: ad34592223433f0bf541c390674bcf96839b6ca8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440815"
---
# <a name="functionenter-function"></a>Функция FunctionEnter
Уведомляет профилировщик о передаче управления в функцию.  
  
> [!NOTE]
> Функция `FunctionEnter` является устаревшей в .NET Framework версии 2,0, и ее использование приведет к снижению производительности. Вместо этого используйте функцию [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `funcID`  
 окне Идентификатор функции, которой передается элемент управления.  
  
## <a name="remarks"></a>Заметки  
 Функция `FunctionEnter` является обратным вызовом. его необходимо реализовать. Реализация должна использовать атрибут класса хранения `__declspec`(`naked`).  
  
 Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.  
  
- Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).  
  
- При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.  
  
 Реализация `FunctionEnter` не должна блокироваться, так как она приведет к задержке сборки мусора. Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, понятном для сборки мусора. Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionEnter`.  
  
 Кроме того, функция `FunctionEnter` не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:** 1,1, 1,0  
  
## <a name="see-also"></a>См. также

- [Функция FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [Функция FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [Функция FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [Метод SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Глобальные статические функции профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
