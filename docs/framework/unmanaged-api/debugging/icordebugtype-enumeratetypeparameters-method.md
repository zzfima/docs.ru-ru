---
title: "Метод ICorDebugType::EnumerateTypeParameters"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugType.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d4b864b2b5fd4f2a6ed03218ce6e7b6f3bf62202
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a>Метод ICorDebugType::EnumerateTypeParameters
Получает указатель интерфейса на ICorDebugTypeEnum, который содержит <xref:System.Type> параметры ссылается ICorDebugType класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppTyParEnum`  
 [out] Указатель на адрес `ICorDebugTypeEnum` , содержащий параметры типа.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `EnumerateTypeParameters` Если CorElementType значение, возвращаемое [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_ PTR или ELEMENT_TYPE_FNPTR. Число параметров и их порядок зависит от типа:  
  
-   После ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE: число параметров типа, содержащихся в `ICorDebugTypeEnum` , этот метод возвращает, будет зависеть от числа типов формальных параметров для соответствующего класса. Например, если тип является `class Dict<String,int32>`, затем `EnumerateTypeParameters` вернет `ICorDebugTypeEnum` , содержащий объекты, представляющие `String` и `int32` в последовательности.  
  
-   ELEMENT_TYPE_FNPTR: Число параметров типа, содержащихся в `ICorDebugTypeEnum` будет иметь одно превышает число аргументов в объявлении функции. Первый параметр типа, содержащийся в `ICorDebugTypeEnum` возвращаемый тип функции, а следующие параметры типа являются параметрами функции.  
  
-   ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF или ELEMENT_TYPE_PTR: будет возвращаться один параметр типа. Например, если тип является типом массива, такие как `int32[]`,`EnumerateTypeParameters` вернет `ICorDebugTypeEnum` , содержащий объект, представляющий `int32`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
