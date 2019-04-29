---
title: Метод ICorDebugEval::CreateValue
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c16f6d1334888fc389a7c39cf0a3865afca2085
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934749"
---
# <a name="icordebugevalcreatevalue-method"></a>Метод ICorDebugEval::CreateValue
Создает значение указанного типа, с начальным значением, равным нулю или null.  
  
 Этот метод является устаревшим в .NET Framework версии 2.0. Используйте [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) вместо этого.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `elementType`  
 [in] Значение [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) перечисление, указывающее тип значения.  
  
 `pElementClass`  
 [in] Указатель на [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) , указывающий класс значения, если тип не является типом-примитивом.  
  
 `ppValue`  
 [out] Указатель на адрес объекта «ICorDebugValue», который представляет значение.  
  
## <a name="remarks"></a>Примечания  
 `CreateValue` Создает `ICorDebugValue` объект заданного типа исключительно с целью его использования при вычислении функции. Этот объект значения можно использовать для передачи пользовательских констант в качестве параметров.  
  
 Если тип значения является типом-примитивом, его начальное значение равно нулю или иметь значение null. Используйте [ICorDebugGenericValue::SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) для задания значения типа-примитива.  
  
 Если значение `elementType` является ELEMENT_TYPE_CLASS, вы получаете «ICorDebugReferenceValue» (возвращается в `ppValue`) представляет ссылку на объект null. Этот объект можно использовать для передачи значения null, имеющий параметры ссылки на объект вычисление функции. Невозможно задать `ICorDebugValue` на любое другое; он всегда имеет значение null.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>См. также

- [Метод CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)
- [Интерфейс ICorDebugEval](icordebugeval-interface.md)
