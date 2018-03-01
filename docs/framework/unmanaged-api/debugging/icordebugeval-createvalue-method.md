---
title: "Метод ICorDebugEval::CreateValue"
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
- ICorDebugEval.CreateValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64d55a951795cc5efc1bfc624dbe07575be153aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalcreatevalue-method"></a>Метод ICorDebugEval::CreateValue
Создает значение заданного типа с начальным значением, равным нулю или null.  
  
 Этот метод является устаревшим в .NET Framework версии 2.0. Используйте [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) вместо него.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `elementType`  
 [in] Значение [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) перечисления, которое указывает тип значения.  
  
 `pElementClass`  
 [in] Указатель на [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) объекта, указывающее класс значения, если тип не является типом-примитивом.  
  
 `ppValue`  
 [out] Указатель на адрес объекта «ICorDebugValue», который представляет значение.  
  
## <a name="remarks"></a>Примечания  
 `CreateValue`Создает `ICorDebugValue` объект заданного типа с единственной целью его использования при вычислении функции. Этот объект значения можно использовать для передачи пользовательских констант в качестве параметров.  
  
 Если тип значения является типом-примитивом, его начальное значение равно нулю или иметь значение null. Используйте [ICorDebugGenericValue::SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) требуется задать значение простого типа.  
  
 Если значение `elementType` — ELEMENT_TYPE_CLASS, вы получаете «ICorDebugReferenceValue» (возвращается в `ppValue`) представляет ссылку на объект null. Этот объект можно использовать для передачи значения null вычисление функции, который имеет параметры ссылки на объект. Не удается задать `ICorDebugValue` к любому другому объекту; он всегда возвращает значение null.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>См. также  
    
 [Метод CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)  
 ICorDebugValue
