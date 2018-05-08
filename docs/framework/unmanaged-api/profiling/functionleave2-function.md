---
title: Функция FunctionLeave2
ms.date: 03/30/2017
api_name:
- FunctionLeave2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave2
helpviewer_keywords:
- FunctionLeave2 function [.NET Framework profiling]
ms.assetid: 8cdac941-8b94-4497-b874-4e571785f3fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d6486a90d952208af89428423867a3daa4e8618
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="functionleave2-function"></a>Функция FunctionLeave2
Уведомляет профилировщик, функция вернет вызывающему объекту, а также сведения о стека фрейма и функция возвращаемое значение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `funcId`  
 [in] Идентификатор функции, которая возвращает.  
  
 `clientData`  
 [in] Идентификатор повторно сопоставленной функции, который ранее указанного профилировщик с помощью [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) функции.  
  
 `func`  
 [in] Объект `COR_PRF_FRAME_INFO` значение, которое указывает на сведения о кадре стека.  
  
 Профилировщик должен интерпретировать его как непрозрачный дескриптор, который может быть передан обратно в ядро выполнения в [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) метод.  
  
 `retvalRange`  
 [in] Указатель на [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) структура, которая задает расположение возвращаемое значение функции в памяти.  
  
 Чтобы получить доступ к информации возвращаемое значение `COR_PRF_ENABLE_FUNCTION_RETVAL` должен быть установлен флаг. Можно использовать профилировщик [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) метод, чтобы задать флаги событий.  
  
## <a name="remarks"></a>Примечания  
 Значения `func` и `retvalRange` параметры не допускаются после `FunctionLeave2` функция возвращает, так как значения, могут быть изменены или удалены.  
  
 `FunctionLeave2` Функция является обратным вызовом, необходимо произвести его. В реализации должен использоваться `__declspec`(`naked`) атрибут класса хранения.  
  
 Перед вызовом этой функции ядро выполнения не сохраняет значения регистров.  
  
-   При входе необходимо сохранить все используемые регистры, включая те, в единицах измерения с плавающей запятой (FPU).  
  
-   При выходе необходимо восстановить стек путем выталкивания из всех параметров, переведенных вызывающим кодом.  
  
 Реализация `FunctionLeave2` не должен блокироваться, поскольку это приведет к задержке сборки мусора. Реализация не должны предпринимать попытки сбора мусора, так как стек может находиться в состоянии понятного имени сбора мусора. При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionLeave2` возвращает.  
  
 Кроме того `FunctionLeave2` функции не следует вызывать управляемый код или каким-либо образом вызывать управляемое распределение памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Функция FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [Функция FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [Метод SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [Глобальные статические функции профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
