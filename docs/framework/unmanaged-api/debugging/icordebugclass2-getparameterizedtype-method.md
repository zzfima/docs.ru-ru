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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1bfc503bfc2b278d7a7344b94cb089cd8e019890
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747766"
---
# <a name="icordebugclass2getparameterizedtype-method"></a>Метод ICorDebugClass2::GetParameterizedType
Получает объявление типа для этого класса.  
  
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
 [in] Значение перечисления CorElementType, показывающий тип элемента для данного класса: Это значение равно ELEMENT_TYPE_VALUETYPE при этом ICorDebugClass2 представляет тип значения. Это значение равно ELEMENT_TYPE_CLASS при этом `ICorDebugClass2` представляет сложный тип.  
  
 `nTypeArgs`  
 [in] Число параметров типа, если тип является универсальным. Число параметров типа (если таковые имеются) должно совпадать с номером, требуемых для класса.  
  
 `ppTypeArgs`  
 [in] Массив указателей, каждый из которых указывает на объект ICorDebugType, который представляет параметр типа. Если класс является не являющегося универсальным, это значение равно null.  
  
 `ppType`  
 [out] Указатель на адрес `ICorDebugType` объект, который представляет объявление типа. Этот объект эквивалентен <xref:System.Type> объект в управляемом коде.  
  
## <a name="remarks"></a>Примечания  
 Если класс является не являющегося универсальным, то есть, если он не имеет параметров типа, `GetParameterizedType` просто возвращает объект типа среды выполнения, соответствующий данному классу. `elementType` Параметра должно быть присвоено типом правильный элемент для данного класса: ELEMENT_TYPE_VALUETYPE, если класс является типом значения; в противном случае ELEMENT_TYPE_CLASS.  
  
 Если этот класс принимает параметры типа (например, `ArrayList<T>`), можно использовать `GetParameterizedType` для создания объекта типа для экземпляры типа, таких как `ArrayList<int>`.  
  
## <a name="background-information"></a>Основные сведения  
 В .NET Framework версий 1.0 и 1.1 каждый тип в метаданных может быть непосредственно сопоставить с типом выполняющегося процесса. Таким образом тип метаданных и тип среды выполнения было единое представление выполняющегося процесса. Тем не менее одного универсального типа в метаданных могут сопоставляться нескольким различным экземплярам типа в выполняющийся процесс. Например, тип метаданных `SortedList<K,V>` можно сопоставить с `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, и т. д. Таким образом вам нужен способ обрабатывать создание экземпляров типа.  
  
 В .NET Framework версии 2.0 вводит `ICorDebugType` интерфейс. Для универсального типа `ICorDebugClass` или `ICorDebugClass2` представляет объект типа без экземпляров (`SortedList<K,V>`) и `ICorDebugType` объект представляет различные типы созданным экземпляром. Учитывая `ICorDebugClass` или `ICorDebugClass2` объекта, можно создать `ICorDebugType` объекта для любого экземпляра путем вызова `ICorDebugClass2::GetParameterizedType` метод. Вы также можете создать `ICorDebugType` объект для простого типа, например Int32, или для неуниверсального типа.  
  
 Введение `ICorDebugType` объект для представления времени выполнения понятие типа имеет окажет влияние на протяжении всего API. Функции, которые ранее были `ICorDebugClass` или `ICorDebugClass2` объекта или даже `CorElementType` значение обобщены вступили `ICorDebugType` объекта.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
