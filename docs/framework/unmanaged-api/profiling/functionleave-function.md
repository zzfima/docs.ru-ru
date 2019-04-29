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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b1fe219c4c852792390b48b0ea4d38adb702281
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598874"
---
# <a name="functionleave-function"></a>Функция FunctionLeave
Уведомляет профилировщик, что функция должна возвращать вызывающей стороне.  
  
> [!NOTE]
>  `FunctionLeave` Рекомендуется использовать функцию в .NET Framework 2.0. Она будет продолжать работать, но будет привести к снижению производительности. Используйте [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) вместо этого функцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `funcID`  
 [in] Идентификатор функции, которое возвращает.  
  
## <a name="remarks"></a>Примечания  
 `FunctionLeave` Функция является обратным вызовом; это необходимо реализовать. В реализации должен использоваться `__declspec`(`naked`) атрибут класса хранения.  
  
 Ядро выполнения не сохраняет значения регистров перед вызовом этой функции.  
  
- При входе необходимо сохранить все регистры, которые вы используете, включая те, в единицах с плавающей запятой (FPU).  
  
- При выходе необходимо восстановить стек путем выталкивания из всех параметров, которые были отправлены вызывающим кодом.  
  
 Реализация `FunctionLeave` не должен блокироваться, поскольку это приведет к задержке сборки мусора. Реализация не должны сбор мусора, так как стек может находиться в состоянии коллекции с поддержкой сборки мусора. При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionLeave` возвращает.  
  
 Кроме того `FunctionLeave` функция не должна вызывать управляемый код или каким-либо образом вызывать управляемое распределение памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>См. также

- [Функция FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [Функция FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [Функция FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [Метод SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Глобальные статические функции профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
