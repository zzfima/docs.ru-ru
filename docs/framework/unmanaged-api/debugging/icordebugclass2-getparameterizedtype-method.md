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
ms.openlocfilehash: 6a5b3a28c7250a16e78e199bceff7c9e64517319
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408217"
---
# <a name="icordebugclass2getparameterizedtype-method"></a>Метод ICorDebugClass2::GetParameterizedType
Возвращает объявление типа для этого класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `elementType`  
 [in] Значение CorElementType перечисление, которое указывает тип элемента для данного класса: это значение равно ELEMENT_TYPE_VALUETYPE при этом ICorDebugClass2 представляет тип значения. Это значение равно ELEMENT_TYPE_CLASS при этом `ICorDebugClass2` представляет сложный тип.  
  
 `nTypeArgs`  
 [in] Число параметров типа, если тип является универсальным. Число параметров типа (если имеется) должно соответствовать числу, требуемым для класса.  
  
 `ppTypeArgs`  
 [in] Массив указателей, каждый из которых указывает на объект ICorDebugType, который представляет параметр типа. Если класс является неуниверсальным, это значение равно null.  
  
 `ppType`  
 [out] Указатель на адрес `ICorDebugType` , представляющий объявление типа. Этот объект эквивалентен <xref:System.Type> объекта в управляемом коде.  
  
## <a name="remarks"></a>Примечания  
 Если класс является неуниверсальных, то есть, если он не имеет параметров типа, `GetParameterizedType` просто возвращает объект типа среды выполнения, соответствующий данному классу. `elementType` Параметра должно быть присвоено типом правильный элемент для данного класса: ELEMENT_TYPE_VALUETYPE, если класс является типом значения; в противном случае ELEMENT_TYPE_CLASS.  
  
 Если класс принимает параметры типа (например, `ArrayList<T>`), можно использовать `GetParameterizedType` , чтобы создать объект типа экземпляры типа, такие как `ArrayList<int>`.  
  
## <a name="background-information"></a>Основные сведения  
 В .NET Framework версий 1.0 и 1.1 каждый тип в метаданных может быть напрямую сопоставлен с типом выполняющегося процесса. Таким образом тип метаданных и тип среды выполнения было единое представление выполняющегося процесса. Однако одного универсального типа в метаданных можно сопоставить нескольким различным экземплярам типа в выполняемом процессе. Например, тип метаданных `SortedList<K,V>` можно сопоставить с `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, и т. д. Таким образом вам необходим способ для обработки экземпляра типа.  
  
 .NET Framework версии 2.0 появился `ICorDebugType` интерфейса. Для универсального типа `ICorDebugClass` или `ICorDebugClass2` представляет объект типа без экземпляров (`SortedList<K,V>`) и `ICorDebugType` объект представляет экземпляр различных типов. Получает `ICorDebugClass` или `ICorDebugClass2` объекта, можно создать `ICorDebugType` объекта для любого экземпляра путем вызова `ICorDebugClass2::GetParameterizedType` метод. Можно также создать `ICorDebugType` объекта для простого типа, например, Int32, или для неуниверсального типа.  
  
 Введение `ICorDebugType` объект для представления времени выполнения понятие типа имеет оказывает влияние на протяжении API. Функции, которые ранее были `ICorDebugClass` или `ICorDebugClass2` объекта или даже `CorElementType` значение обобщены, чтобы воспользоваться `ICorDebugType` объекта.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
