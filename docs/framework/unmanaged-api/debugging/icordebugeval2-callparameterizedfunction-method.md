---
title: "Метод ICorDebugEval2::CallParameterizedFunction"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.CallParameterizedFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 720d9c4fb9b997538ee2bb18ac7987350f6bfb57
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2callparameterizedfunction-method"></a>Метод ICorDebugEval2::CallParameterizedFunction
Устанавливает для указанного ICorDebugFunction, который может быть вложен в класс, конструктор которого принимает вызов <xref:System.Type> параметры или сам может занять <xref:System.Type> параметров.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pFunction`  
 [in] Указатель на `ICorDebugFunction` объект, который представляет вызываемую функцию.  
  
 `nTypeArgs`  
 [in] Количество аргументов, которые принимает функция.  
  
 `ppTypeArgs`  
 [in] Массив указателей, каждый из которых указывает на объект ICorDebugType, представляющий аргумент функции.  
  
 `nArgs`  
 [in] Количество значений, переданных в функцию.  
  
 `ppArgs`  
 [in] Массив указателей, каждый из которых указывает на объект ICorDebugValue, представляющий значение, переданное аргументу функции.  
  
## <a name="remarks"></a>Примечания  
 `CallParameterizedFunction`Подобно [ICorDebugEval::CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) за исключением того, что функция может быть внутри класса с параметрами типов, может сам принимают параметры типа или оба. Аргументы типа должны быть заданы сначала для класса, а затем для функции.  
  
 Если функция находится в другом домене приложения, будет выполнен переход. Однако все аргументы типа и значения должны быть в целевом домене приложения.  
  
 Вычисление функции могут выполняться только в ограниченных сценариях. Если `CallParameterizedFunction` или `ICorDebugEval::CallFunction` завершается ошибкой, возвращенное значение HRESULT указывает наиболее общие возможную причину сбоя.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
