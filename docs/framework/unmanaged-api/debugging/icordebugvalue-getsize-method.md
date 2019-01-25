---
title: Метод ICorDebugValue::GetSize
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb0030a25dd48ab4236ec2b51891e0ac41aac902
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612623"
---
# <a name="icordebugvaluegetsize-method"></a>Метод ICorDebugValue::GetSize
Получает размер в байтах объекта «ICorDebugValue».  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pSize`  
 [out] Размер в байтах, значение объекта.  
  
## <a name="remarks"></a>Примечания  
 Если тип значения является ссылочным типом, этот метод возвращает размер указателя, а не размер объекта.  
  
 `ICorDebugValue::GetSize` Возвращает метод `COR_E_OVERFLOW` для объектов, размер которых превышает 4 ГБ на 64-разрядных платформах. Используйте [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) метод вместо этого для объектов, размер которых превышает 4 ГБ.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
