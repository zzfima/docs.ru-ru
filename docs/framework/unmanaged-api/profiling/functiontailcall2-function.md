---
title: Функция FunctionTailcall2
ms.date: 03/30/2017
api_name:
- FunctionTailcall2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall2
helpviewer_keywords:
- FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type:
- apiref
ms.openlocfilehash: 60276327617ae24e9bdcebf958613c21d3808429
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175191"
---
# <a name="functiontailcall2-function"></a>Функция FunctionTailcall2
Уведомляет профайлера о том, что функция выполнения в настоящее время собирается выполнить хвостовой вызов другой функции, и предоставляет информацию о кадре стека.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,
    [in] UINT_PTR           clientData,
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a>Параметры

- `funcId`

  \[в» идентификатор в настоящее время выполнения функции, которая собирается сделать хвост вызова.

- `clientData`

  \[в» Идентификатор функции remapped, который профайлер ранее определил через [FunctionIDMapper](functionidmapper-function.md), в настоящее время исполняя функцию которая около сделать звонок кабеля.
  
- `func`

  \[в `COR_PRF_FRAME_INFO` значении, которое указывает на информацию о кадре стека.

  Профайлер должен рассматривать это как непрозрачную ручку, которая может быть передана обратно в двигатель исполнения в методе [ICorProfilerInfo2::GetFunctionInfo2.](icorprofilerinfo2-getfunctioninfo2-method.md)

## <a name="remarks"></a>Remarks  
 Целевая функция хвостового вызова будет использовать текущую рамку стека и вернется непосредственно к вызывающему функции, сделавшейней хвостовой вызов. Это означает, что обратный вызов [FunctionLeave2](functionleave2-function.md) не будет выдан для функции, которая является целью хвостового вызова.  
  
 Значение `func` параметра не действителен `FunctionTailcall2` после возврата функции, поскольку значение может измениться или быть уничтожено.  
  
 Функция `FunctionTailcall2` является обратным вызовом; вы должны реализовать его. Реализация должна использовать `__declspec``naked`атрибут типа хранения .  
  
 Двигатель выполнения не сохраняет регистров перед вызовом этой функции.  
  
- При входе необходимо сохранить все регистры, которые вы используете, в том числе в блоке плавающей точки (FPU).  
  
- На выходе необходимо восстановить стек, выскочив все параметры, которые были проталкиваются абонентом.  
  
 Реализация не `FunctionTailcall2` должна блокироваться, так как это приведет к задержке сбора мусора. Реализация не должна пытаться выбросить мусор, поскольку стек может быть не в удобном для сбора мусора состоянии. При попытке сбора мусора время выполнения `FunctionTailcall2` будет блокироваться до возвращения.  
  
 Кроме того, `FunctionTailcall2` функция не должна вызывать управляемый код или каким-либо образом вызывать управляемое распределение памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Функция FunctionEnter2](functionenter2-function.md)
- [Функция FunctionLeave2](functionleave2-function.md)
- [Метод SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Глобальные статические функции профилирования](profiling-global-static-functions.md)
