---
title: Метод ICorDebugObjectValue::GetFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
ms.openlocfilehash: 002c6cccb3ddf29b831ba5e14baa5e51f1b82433
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095880"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a>Метод ICorDebugObjectValue::GetFieldValue
Возвращает значение указанного поля указанного класса для данного значения объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pClass`  
 окне Указатель на объект "ICorDebugClass", представляющий класс, для которого необходимо получить значение поля.  
  
 `fieldDef`  
 окне Токен `mdFieldDef`, который ссылается на метаданные, описывающие поле.  
  
 `ppValue`  
 заполняет Указатель на объект "ICorDebugValue", представляющий значение указанного поля.  
  
## <a name="remarks"></a>Заметки  
 Класс, указанный в параметре `pClass`, должен находиться в иерархии класса значения объекта, а поле должно быть полем этого класса.  
  
 Метод `GetFieldValue` по-прежнему будет выполняться для универсальных объектов и универсальных классов. Например, если Мидиктионари\<V > наследуется из словаря\<String, V >, а значение объекта имеет тип Мидиктионари\<Int32 >, передача `ICorDebugClass`ного объекта для Dictionary\<K, V > успешно получит поле\<словаря String, Int32 >.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
