---
title: "Функция FunctionTailcall2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionTailcall2
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionTailcall2
helpviewer_keywords: FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9d6ccb08bc09bea2ec9e9a49333c92da8cb5695
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="functiontailcall2-function"></a>Функция FunctionTailcall2
Уведомляет профилировщик, что текущей выполняемой функции собирается выполнить вызов с префиксом tail в другую функцию и предоставляет сведения о кадре стека.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `funcId`  
 [in] Идентификатор текущей выполняемой функции, внесет с префиксом tail.  
  
 `clientData`  
 [in] Идентификатор повторно сопоставленной функции, который ранее указанного профилировщик с помощью [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), текущей выполняемой функции, внесет с префиксом tail.  
  
 `func`  
 [in] Объект `COR_PRF_FRAME_INFO` значение, которое указывает на сведения о кадре стека.  
  
 Профилировщик должен интерпретировать его как непрозрачный дескриптор, который может быть передан обратно в ядро выполнения в [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) метод.  
  
## <a name="remarks"></a>Примечания  
 Целевая функция вызова с префиксом tail будет использовать текущий кадр стека и возвратит непосредственно вызывающему объекту функции, сделанные с префиксом tail. Это означает, что [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) не будет выдан обратного вызова для функции, которая является целевой для вызова с префиксом tail.  
  
 Значение `func` недопустимый параметр после `FunctionTailcall2` функция возвращает, так как значение, могут быть изменены или удалены.  
  
 `FunctionTailcall2` Функция является обратным вызовом, необходимо произвести его. В реализации должен использоваться `__declspec`(`naked`) атрибут класса хранения.  
  
 Перед вызовом этой функции ядро выполнения не сохраняет значения регистров.  
  
-   При входе необходимо сохранить все используемые регистры, включая те, в единицах измерения с плавающей запятой (FPU).  
  
-   При выходе необходимо восстановить стек путем выталкивания из всех параметров, переведенных вызывающим кодом.  
  
 Реализация `FunctionTailcall2` не должен блокироваться, поскольку это приведет к задержке сборки мусора. Реализация не должны предпринимать попытки сбора мусора, так как стек может находиться в состоянии понятного имени сбора мусора. При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionTailcall2` возвращает.  
  
 Кроме того `FunctionTailcall2` функции не следует вызывать управляемый код или каким-либо образом вызывать управляемое распределение памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Функция FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [Функция FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [Метод SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [Глобальные статические функции профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
