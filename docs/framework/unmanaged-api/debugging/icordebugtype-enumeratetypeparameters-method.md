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
ms.openlocfilehash: b2c381d093069f5ee86be1b19d75f5c2d69ad9fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791313"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a>Метод ICorDebugType::EnumerateTypeParameters
Возвращает указатель интерфейса на ICorDebugTypeEnum, содержащий параметры <xref:System.Type> класса, на который ссылается этот объект ICorDebugType.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppTyParEnum`  
 заполняет Указатель на адрес `ICorDebugTypeEnum`, который содержит параметры типа.  
  
## <a name="remarks"></a>Заметки  
 Можно использовать `EnumerateTypeParameters`, если значение Корелементтипе, возвращаемое с помощью [ICorDebugType:: GetType](icordebugtype-gettype-method.md) , ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR или ELEMENT_TYPE_FNPTR. Количество параметров и их порядок зависит от типа:  
  
- ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE: количество параметров типа, содержащихся в `ICorDebugTypeEnum`, возвращаемых этим методом, будет зависеть от числа формальных параметров типа для соответствующего класса. Например, если тип — `class Dict<String,int32>`, `EnumerateTypeParameters` возвратит `ICorDebugTypeEnum`, содержащий объекты, представляющие `String` и `int32` в последовательности.  
  
- ELEMENT_TYPE_FNPTR: количество параметров типа, содержащихся в `ICorDebugTypeEnum`, будет больше, чем число аргументов, принимаемых функцией. Первый параметр типа, содержащийся в `ICorDebugTypeEnum`, является типом возвращаемого значения для функции, а последующие параметры типа являются параметрами функции.  
  
- ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF или ELEMENT_TYPE_PTR: будет возвращен один параметр типа. Например, если тип является массивом типа, например `int32[]`,`EnumerateTypeParameters` вернет `ICorDebugTypeEnum`, содержащий объект, представляющий `int32`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
