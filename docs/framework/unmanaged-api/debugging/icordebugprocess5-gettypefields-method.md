---
title: Метод ICorDebugProcess5::GetTypeFields
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
ms.openlocfilehash: 29006eba3d3a523fd24a461207ab12222a639782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178593"
---
# <a name="icordebugprocess5gettypefields-method"></a>Метод ICorDebugProcess5::GetTypeFields
Предоставляет информацию о полях, которые принадлежат к типу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `id`  
 (в) Идентификатор типа, информация о поле которого извлекается.  
  
 `celt`  
 (в) Количество [COR_FIELD](cor-field-structure.md) объектов, информация о поле которых должна быть извлечена.  
  
 `fields`  
 (ваут) Массив [COR_FIELD](cor-field-structure.md) объектов, предоставляющих информацию о полях, принадлежащих к типу.  
  
 `pceltNeeded`  
 (ваут) Указатель на количество [COR_FIELD](cor-field-structure.md) объектов, включенных в `fields`.  
  
## <a name="remarks"></a>Remarks  
 Параметр, `celt` который определяет количество полей, поле информации метод `fields`использует для заполнения, должен `COR_TYPE_LAYOUT::numFields` соответствовать значению поля.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
