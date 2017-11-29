---
title: "Функция FunctionTailcall"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionTailcall
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionTailcall
helpviewer_keywords: FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8bc0d72ad9c11cb36803cc606b460181b44033f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="functiontailcall-function"></a>Функция FunctionTailcall
Уведомляет профилировщик о том, что текущей выполняемой функции собирается выполнить вызов с префиксом tail в другую функцию.  
  
> [!NOTE]
>  `FunctionTailcall` Функция рекомендуется в .NET Framework версии 2.0. Она будет продолжать работать, но повлечет за собой снижение производительности. Используйте [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) вместо этого функцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `funcID`  
 [in] Идентификатор текущей выполняемой функции, внесет с префиксом tail.  
  
## <a name="remarks"></a>Примечания  
 Целевая функция вызова с префиксом tail будет использовать текущий кадр стека и возвратит непосредственно вызывающему объекту функции, сделанные с префиксом tail. Это означает, что [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) не будет выдан обратного вызова для функции, которая является целевой для вызова с префиксом tail.  
  
 `FunctionTailcall` Функция является обратным вызовом, необходимо произвести его. В реализации должен использоваться `__declspec`(`naked`) атрибут класса хранения.  
  
 Перед вызовом этой функции ядро выполнения не сохраняет значения регистров.  
  
-   При входе необходимо сохранить все используемые регистры, включая те, в единицах измерения с плавающей запятой (FPU).  
  
-   При выходе необходимо восстановить стек путем выталкивания из всех параметров, переведенных вызывающим кодом.  
  
 Реализация `FunctionTailcall` не должен блокироваться, поскольку это приведет к задержке сборки мусора. Реализация не должны предпринимать попытки сбора мусора, так как стек может находиться в состоянии понятного имени сбора мусора. При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionTailcall` возвращает.  
  
 Кроме того `FunctionTailcall` функции не следует вызывать управляемый код или каким-либо образом вызывать управляемое распределение памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>См. также  
 [Функция FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [Функция FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [Метод SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [Глобальные статические функции профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
