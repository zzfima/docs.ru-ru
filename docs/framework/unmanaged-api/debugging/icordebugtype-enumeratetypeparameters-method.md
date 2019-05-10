---
title: Метод ICorDebugType::EnumerateTypeParameters
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b48e375286e709a2ce570769c9a0453765824ec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622673"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a>Метод ICorDebugType::EnumerateTypeParameters
Получает указатель интерфейса на ICorDebugTypeEnum, который содержит <xref:System.Type> параметры типа класса, который ссылается этот ICorDebugType.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppTyParEnum`  
 [out] Указатель на адрес `ICorDebugTypeEnum` , содержащий параметры типа.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `EnumerateTypeParameters` Если CorElementType значение, возвращаемое функцией [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_ PTR или ELEMENT_TYPE_FNPTR. Число параметров и их порядок зависит от типа:  
  
- ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE: Число параметров типа, содержащихся в `ICorDebugTypeEnum` , этот метод возвращает, будет зависеть от числа типов формальных параметров для соответствующего класса. Например, если тип является `class Dict<String,int32>`, затем `EnumerateTypeParameters` вернет `ICorDebugTypeEnum` , содержащий объекты, представляющие `String` и `int32` в последовательности.  
  
- ELEMENT_TYPE_FNPTR: Число параметров типа, содержащихся в `ICorDebugTypeEnum` будет иметь одно больше, чем число аргументов в объявлении функции. Первый параметр типа, содержащихся в `ICorDebugTypeEnum` тип возвращаемого значения для функции, и следующие параметры типа параметров функции.  
  
- ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF или ELEMENT_TYPE_PTR: Один параметр типа будет возвращаться. Например, если тип является типом массива, такие как `int32[]`,`EnumerateTypeParameters` вернет `ICorDebugTypeEnum` , содержащий объект, представляющий `int32`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
