---
title: Метод ICorDebugClass2::GetParameterizedType
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.GetParameterizedType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type:
- apiref
ms.openlocfilehash: 64537ab97c1256cc6f963999b027bafc25cbbccb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125729"
---
# <a name="icordebugclass2getparameterizedtype-method"></a>Метод ICorDebugClass2::GetParameterizedType
Возвращает объявление типа для этого класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `elementType`  
 окне Значение перечисления Корелементтипе, указывающее тип элемента для этого класса: Установите это значение в ELEMENT_TYPE_VALUETYPE, если это ICorDebugClass2 представляет тип значения. Присвойте этому параметру значение ELEMENT_TYPE_CLASS, если это `ICorDebugClass2` представляет сложный тип.  
  
 `nTypeArgs`  
 окне Число параметров типа, если тип является универсальным. Количество параметров типа (если таковое имеется) должно совпадать с числом, необходимым для класса.  
  
 `ppTypeArgs`  
 окне Массив указателей, каждый из которых указывает на объект ICorDebugType, представляющий параметр типа. Если класс не является универсальным, это значение равно null.  
  
 `ppType`  
 заполняет Указатель на адрес объекта `ICorDebugType`, который представляет объявление типа. Этот объект эквивалентен объекту <xref:System.Type> в управляемом коде.  
  
## <a name="remarks"></a>Заметки  
 Если класс не является универсальным, то есть если он не имеет параметров типа, `GetParameterizedType` просто получает объект типа среды выполнения, соответствующий классу. Для параметра `elementType` должен быть задан правильный тип элемента для класса: ELEMENT_TYPE_VALUETYPE, если класс является типом значения; в противном случае — ELEMENT_TYPE_CLASS.  
  
 Если класс принимает параметры типа (например, `ArrayList<T>`), можно использовать `GetParameterizedType` для создания объекта типа для экземпляра типа, такого как `ArrayList<int>`.  
  
## <a name="background-information"></a>Основные сведения  
 В .NET Framework версиях 1,0 и 1,1 каждый тип в метаданных можно напрямую сопоставить с типом в выполняемом процессе. Таким словами, тип метаданных и тип среды выполнения имеют одно представление в выполняющемся процессе. Однако один универсальный тип в метаданных может быть сопоставлен с множеством различных экземпляров типа в выполняющемся процессе. Например, тип метаданных `SortedList<K,V>` может сопоставляться с `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`и т. д. Таким образом, необходим способ для управления созданием экземпляров типа.  
  
 В .NET Framework версии 2,0 появился интерфейс `ICorDebugType`. Для универсального типа объект `ICorDebugClass` или `ICorDebugClass2` представляет тип, не являющийся экземпляром (`SortedList<K,V>`), а объект `ICorDebugType` представляет различные экземпляры типов. При наличии объекта `ICorDebugClass` или `ICorDebugClass2` можно создать объект `ICorDebugType` для любого экземпляра, вызвав метод `ICorDebugClass2::GetParameterizedType`. Можно также создать объект `ICorDebugType` для простого типа, например Int32, или для типа, не являющегося универсальным.  
  
 Введение объекта `ICorDebugType`, представляющего представление типа во время выполнения, оказывает воздействие на весь интерфейс API. Функции, которые ранее предпринимали `ICorDebugClass` или `ICorDebugClass2` объект или даже `CorElementType`, обобщены для получения объекта `ICorDebugType`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
