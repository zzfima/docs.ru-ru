---
title: "Метод ICorDebugObjectValue::GetFieldValue"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectValue.GetFieldValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33c3f368d9b78b899f54c989427ea1f660346487
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a>Метод ICorDebugObjectValue::GetFieldValue
Возвращает значение указанного поля указанного класса для этого значения объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pClass`  
 [in] Указатель на объект «ICorDebugClass», который представляет класс, для которого необходимо получить значение поля.  
  
 `fieldDef`  
 [in] `mdFieldDef` Маркер, который ссылается на метаданные, описывающие поля.  
  
 `ppValue`  
 [out] Указатель на объект «ICorDebugValue», представляющее значение указанного поля.  
  
## <a name="remarks"></a>Примечания  
 Класс, заданный в `pClass` параметр, должен быть в иерархии класса значения объекта, а поле должно быть полем этого класса.  
  
 `GetFieldValue` Метод для универсальных объектов и универсальные классы пройдет успешно. Например если MyDictionary\<V > наследует из словаря\<строка, V >, и значение объекта, которое имеет тип MyDictionary\<int32 > с передачей `ICorDebugClass` объект словаря\<K, V > будет успешно получен поле словаря\<string, int32 >.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
    
 
