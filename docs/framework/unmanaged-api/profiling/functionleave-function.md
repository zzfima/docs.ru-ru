---
title: Функция FunctionLeave
ms.date: 03/30/2017
api_name:
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
ms.openlocfilehash: a9ab8c81c995bbec41db217c904e03dd70351aee
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866888"
---
# <a name="functionleave-function"></a>Функция FunctionLeave
Уведомляет профилировщик о том, что функция собирается вернуть вызывающему объекту.  
  
> [!NOTE]
> Функция `FunctionLeave` является устаревшей в .NET Framework 2,0. Он будет продолжать работать, но будет приводить к снижению производительности. Вместо этого используйте функцию [FunctionLeave2](functionleave2-function.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>Параметры

- `funcID`

  \[in] Идентификатор возвращаемой функции.

## <a name="remarks"></a>Заметки  
 Функция `FunctionLeave` является обратным вызовом. его необходимо реализовать. Реализация должна использовать атрибут класса хранения `__declspec`(`naked`).  
  
 Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.  
  
- Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).  
  
- При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.  
  
 Реализация `FunctionLeave` не должна блокироваться, так как она приведет к задержке сборки мусора. Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, понятном для сборки мусора. Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionLeave`.  
  
 Кроме того, функция `FunctionLeave` не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:** 1,1, 1,0  
  
## <a name="see-also"></a>См. также:

- [Функция FunctionEnter2](functionenter2-function.md)
- [Функция FunctionLeave2](functionleave2-function.md)
- [Функция FunctionTailcall2](functiontailcall2-function.md)
- [Метод SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Глобальные статические функции профилирования](profiling-global-static-functions.md)
