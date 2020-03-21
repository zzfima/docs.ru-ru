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
ms.openlocfilehash: 9aeb7a294beb10f9c2968e6161c72fdc362c4991
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177063"
---
# <a name="functionenter2-function"></a>Функция FunctionEnter2
Уведомляет профайлера о том, что элемент управления передается функции, и предоставляет информацию о кадровом штабе и аргументах функции. Эта функция заменяет функцию [FunctionEnter.](functionenter-function.md)  
  
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

- `funcId`

  \[в» Идентификатор функции, к которой передается контроль.

- `clientData`

  \[в идентификаторе remapped функции, который профайлер ранее указал с помощью функции [FunctionIDMapper.](functionidmapper-function.md)
  
- `func`

  \[в `COR_PRF_FRAME_INFO` значении, которое указывает на информацию о кадре стека.
  
  Профайлер должен рассматривать это как непрозрачную ручку, которая может быть передана обратно в двигатель исполнения в методе [ICorProfilerInfo2::GetFunctionInfo2.](icorprofilerinfo2-getfunctioninfo2-method.md)  
  
- `argumentInfo`

  \[в» указатель на [структуру COR_PRF_FUNCTION_ARGUMENT_INFO,](cor-prf-function-argument-info-structure.md) которая определяет местоположения в памяти аргументов функции.

  Для того, чтобы получить `COR_PRF_ENABLE_FUNCTION_ARGS` доступ к информации аргумент, флаг должен быть установлен. Профайлер может использовать метод [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) для установки флагов событий.

## <a name="remarks"></a>Remarks  
 Значения `func` и `argumentInfo` параметры недействительны после возвращения `FunctionEnter2` функции, поскольку значения могут изменяться или быть уничтожены.  
  
 Функция `FunctionEnter2` является обратным вызовом; вы должны реализовать его. Реализация должна использовать `__declspec``naked`атрибут типа хранения .  
  
 Двигатель выполнения не сохраняет регистров перед вызовом этой функции.  
  
- При входе необходимо сохранить все регистры, которые вы используете, в том числе в блоке плавающей точки (FPU).  
  
- На выходе необходимо восстановить стек, выскочив все параметры, которые были проталкиваются абонентом.  
  
 Реализация не `FunctionEnter2` должна блокироваться, так как это приведет к задержке сбора мусора. Реализация не должна пытаться выбросить мусор, поскольку стек может быть не в удобном для сбора мусора состоянии. При попытке сбора мусора время выполнения `FunctionEnter2` будет блокироваться до возвращения.  
  
 Кроме того, `FunctionEnter2` функция не должна вызывать управляемый код или каким-либо образом вызывать управляемое распределение памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Функция FunctionLeave2](functionleave2-function.md)
- [Функция FunctionTailcall2](functiontailcall2-function.md)
- [Метод SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Глобальные статические функции профилирования](profiling-global-static-functions.md)
