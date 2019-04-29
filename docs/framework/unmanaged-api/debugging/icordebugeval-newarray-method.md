---
title: Метод ICorDebugEval::NewArray
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1abe307e3b9fa607912f98e456a11176eb17c56
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934762"
---
# <a name="icordebugevalnewarray-method"></a>Метод ICorDebugEval::NewArray
Выделяет новый массив элементов указанного типа и измерений.  
  
 Этот метод является устаревшим в .NET Framework версии 2.0. Используйте [ICorDebugEval2::NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) вместо этого.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `elementType`  
 [in] Значение перечисления CorElementType, показывающий тип элемента массива.  
  
 `pElementClass`  
 [in] Указатель на объект ICorDebugClass, указывающий класс элемента. Это значение может иметь значение null, если тип элемента является типом-примитивом.  
  
 `rank`  
 [in] Число измерений массива. В .NET Framework 2.0 это значение должно быть 1.  
  
 `dims`  
 [in] Размер в байтах каждого измерения массива.  
  
 `lowBounds`  
 [в] Необязательно. Нижняя граница каждого измерения массива. Если это значение указано, для каждого измерения предполагается нижнюю границу, равную нулю.  
  
## <a name="remarks"></a>Примечания  
 Массив всегда создается в домене приложения, в котором в настоящее время выполняется поток.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** 1.1, 1.0
