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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8778edf9ac6e32d5dab3a53a6d9cc643a8df13b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107917"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a>Метод ICorDebugObjectValue::GetFieldValue
Получает значение указанного поля заданного класса для этого значения объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pClass`  
 [in] Указатель на объект, представляющий класс, для которого необходимо получить значение поля «ICorDebugClass».  
  
 `fieldDef`  
 [in] `mdFieldDef` Маркер, который ссылается на метаданные, описывающие поле.  
  
 `ppValue`  
 [out] Указатель на объект «ICorDebugValue», который представляет значение указанного поля.  
  
## <a name="remarks"></a>Примечания  
 Класс, заданный в `pClass` параметр, должен быть в иерархии значение объекта класса, а поле должно быть полем этого класса.  
  
 `GetFieldValue` Метод все равно заканчивается успешно для универсальных объектов и классов. Например если MyDictionary\<V > наследует из словаря\<string, V >, и значение объекта, которое имеет тип MyDictionary\<int32 >, передав `ICorDebugClass` объект словаря\<K, V > будет получить поля словаря\<string, int32 >.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
