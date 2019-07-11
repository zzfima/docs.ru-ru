---
title: Метод ICorDebugEval::NewObject
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 362c01e0b08145919793cec011a856f0090e5c47
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752990"
---
# <a name="icordebugevalnewobject-method"></a>Метод ICorDebugEval::NewObject
Выделяет новый экземпляр объекта и вызывает заданный метод конструктора.  
  
 Этот метод является устаревшим в .NET Framework версии 2.0. Используйте [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) вместо этого.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pConstructor`  
 [in] К вызову конструктора.  
  
 `nArgs`  
 [in] Размер массива `ppArgs`.  
  
 `ppArgs`  
 [in] Массив объектов ICorDebugValue, каждый из которых представляет аргумент, передаваемый в конструктор.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>См. также

- [Метод NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)
