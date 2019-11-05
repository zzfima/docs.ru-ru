---
title: Метод ICorDebugEval2::NewParameterizedArray
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type:
- apiref
ms.openlocfilehash: 9476bcc9706e89fd3d7e0abc14031f70a0aa0ad0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084839"
---
# <a name="icordebugeval2newparameterizedarray-method"></a>Метод ICorDebugEval2::NewParameterizedArray
Выделяет новый массив указанного типа элемента и измерений.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pElementType`  
 окне Указатель на объект ICorDebugType, представляющий тип элемента, хранящегося в массиве.  
  
 `rank`  
 окне Число измерений массива. В .NET Framework версии 2,0 это значение должно быть равно 1.  
  
 `dims`  
 окне Размер каждого измерения массива в байтах.  
  
 `lowBounds`  
 [в] Необязательно. Нижняя граница каждого измерения массива. Если это значение пропущено, для каждого измерения предполагается Нижняя граница, равная нулю.  
  
## <a name="remarks"></a>Заметки  
 Элементы массива могут быть экземплярами универсального типа. Массив всегда создается в домене приложения, в котором в данный момент выполняется поток. В .NET Framework 2,0 значение `rank` должно быть равно 1.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
