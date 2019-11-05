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
ms.openlocfilehash: 0045285a3da22f468c2426bb3b9c4ae7e3e1d7c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132674"
---
# <a name="icordebugprocess5gettypefields-method"></a>Метод ICorDebugProcess5::GetTypeFields
Предоставляет сведения о полях, принадлежащих типу.  
  
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
 окне Идентификатор типа, сведения о поле которого извлекаются.  
  
 `celt`  
 окне Число объектов [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) , сведения о полях которых необходимо получить.  
  
 `fields`  
 заполняет Массив объектов [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) , которые предоставляют сведения о полях, принадлежащих типу.  
  
 `pceltNeeded`  
 заполняет Указатель на число объектов [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) , включаемых в `fields`.  
  
## <a name="remarks"></a>Заметки  
 Параметр `celt`, который указывает количество полей, сведения о полях которых использует метод для заполнения `fields`, должны соответствовать значению поля `COR_TYPE_LAYOUT::numFields`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
