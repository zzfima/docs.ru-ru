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
ms.openlocfilehash: 38b00d903fdd7301415a8df7642e12366178fd10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413944"
---
# <a name="icordebugevalnewarray-method"></a>Метод ICorDebugEval::NewArray
Выделяет новый массив с заданным типом элементов и измерений.  
  
 Этот метод является устаревшим в .NET Framework версии 2.0. Используйте [ICorDebugEval2::NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) вместо него.  
  
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
  
#### <a name="parameters"></a>Параметры  
 `elementType`  
 [in] Значение CorElementType перечисление, которое указывает тип элемента массива.  
  
 `pElementClass`  
 [in] Указатель на объект ICorDebugClass, указывающий класс элемента. Это значение может быть null, если тип элемента является типом-примитивом.  
  
 `rank`  
 [in] Число измерений массива. В .NET Framework 2.0 это значение должно быть 1.  
  
 `dims`  
 [in] Размер в байтах для каждого измерения массива.  
  
 `lowBounds`  
 [в] Необязательно. Нижняя граница каждого измерения массива. Если это значение указано, для каждого измерения предполагается нижнюю границу, равную нулю.  
  
## <a name="remarks"></a>Примечания  
 Массив всегда создается в домене приложения, в котором в настоящее время выполняется поток.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** 1.1, 1.0
