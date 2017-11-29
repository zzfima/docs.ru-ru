---
title: "Метод ICorDebugEval2::NewParameterizedArray"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.NewParameterizedArray
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cf7f8fb0d3418f863f2cd1531dc32b7e64c2b8a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2newparameterizedarray-method"></a>Метод ICorDebugEval2::NewParameterizedArray
Выделяет новый массив с заданным типом элементов и измерений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pElementType`  
 [in] Указатель на объект ICorDebugType, представляющий тип элементов, которые хранятся в массиве.  
  
 `rank`  
 [in] Число измерений массива. В платформе .NET Framework версии 2.0 это значение должно быть 1.  
  
 `dims`  
 [in] Размер в байтах для каждого измерения массива.  
  
 `lowBounds`  
 [в] Необязательно. Нижняя граница каждого измерения массива. Если это значение указано, для каждого измерения предполагается нижнюю границу, равную нулю.  
  
## <a name="remarks"></a>Примечания  
 Элементы массива могут быть экземпляры универсального типа. Массив всегда создается в домене приложения, в котором в настоящее время выполняется поток. В .NET Framework версии 2.0 значение `rank` должно иметь значение 1.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
