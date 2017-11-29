---
title: "Метод ICorDebugProcess5::GetTypeFields"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetTypeFields
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7a64e754a77c7d730d921f8a8c1547dd18b66d77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5gettypefields-method"></a>Метод ICorDebugProcess5::GetTypeFields
Сведения о полях, которые принадлежат к типу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `id`  
 [in] Идентификатор типа, сведения о поле которого извлекается.  
  
 `celt`  
 [in] Число [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) объектов, поле сведения о которой требуется получить.  
  
 `fields`  
 [out] Массив [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) объектов, которые предоставляют сведения о полях, которые относятся к типу.  
  
 `pceltNeeded`  
 [out] Указатель на число [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) объекты, включенные в `fields`.  
  
## <a name="remarks"></a>Примечания  
 `celt` Параметр, который задает количество полей, сведения о поле, метод использует для заполнения `fields`, должен соответствовать значению `COR_TYPE_LAYOUT::numFields` поля.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
