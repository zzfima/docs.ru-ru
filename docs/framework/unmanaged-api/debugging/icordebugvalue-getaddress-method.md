---
title: Метод ICorDebugValue::GetAddress
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac550ee7b1d66612557b30d15c275c90cf09b8af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986860"
---
# <a name="icordebugvaluegetaddress-method"></a>Метод ICorDebugValue::GetAddress
Возвращает адрес объекта «ICorDebugValue», который находится в отлаживаемом процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pAddress`  
 [out] Указатель на `CORDB_ADDRESS` , указывающий адрес этого объекта значение.  
  
## <a name="remarks"></a>Примечания  
 Если значение недоступно, возвращается 0 (ноль). Это может произойти, если значение хотя бы частично в регистрах или хранится в дескрипторе сборщика мусора (`GCHandle`).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
