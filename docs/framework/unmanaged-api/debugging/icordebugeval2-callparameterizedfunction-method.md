---
title: Метод ICorDebugEval2::CallParameterizedFunction
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CallParameterizedFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2779cfaecfdd241b5317ac8b467222e045d48049
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753319"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a>Метод ICorDebugEval2::CallParameterizedFunction
Устанавливает для указанного ICorDebugFunction, который может быть вложен в класс, конструктор которого принимает вызов <xref:System.Type> параметры или сам может занять <xref:System.Type> параметров.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pFunction`  
 [in] Указатель на `ICorDebugFunction` объект, который представляет функцию для вызова.  
  
 `nTypeArgs`  
 [in] Число аргументов, функция принимает.  
  
 `ppTypeArgs`  
 [in] Массив указателей, каждый из которых указывает ICorDebugType объект, представляющий аргумент функции.  
  
 `nArgs`  
 [in] Число значений, переданных в функцию.  
  
 `ppArgs`  
 [in] Массив указателей, каждый из которых указывает ICorDebugValue объект, представляющий значение передается в качестве аргумента функции.  
  
## <a name="remarks"></a>Примечания  
 `CallParameterizedFunction` Подобно [ICorDebugEval::CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) за исключением того, что функция может быть внутри класса с параметрами типа, может сам принимают параметры типа или оба. Аргументы типа должны быть заданы сначала для класса, а затем для функции.  
  
 Если функция находится в другом домене приложения, будет выполнен переход. Тем не менее все аргументы типа и значения должны быть в целевом домене приложения.  
  
 Вычисление функции могут выполняться только в ограниченном числе сценариев. Если `CallParameterizedFunction` или `ICorDebugEval::CallFunction` завершается сбоем, возвращенное значение HRESULT указывает наиболее общие возможные причины сбоя.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
