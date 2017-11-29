---
title: "Метод ICorDebugComObjectValue::GetCachedInterfacePointers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugComObjectValue::GetCachedInterfacePointers
api_location: mscordbi.dll
f1_keywords: ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 607300d6b46f3ee20545c50872b99df483b1614c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a>Метод ICorDebugComObjectValue::GetCachedInterfacePointers
Возвращает интерфейс необработанные указатели, кэшируются на текущем вызываемой оболочки времени выполнения (RCW).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
#### <a name="parameters"></a>Параметры  
 `bIInspectableOnly`  
 [in] Значение, указывающее, является ли метод будет возвращать только [!INCLUDE[wrt](../../../../includes/wrt-md.md)] интерфейсы (`IInspectable` интерфейсы) или все COM-интерфейсы, кэшируемых вызываемой оболочки времени выполнения (RCW).  
  
 `celt`  
 [in] Количество объектов, чьи адреса должны быть получены.  
  
 `pceltFetched`  
 [out] Указатель на число `CORDB_ADDRESS` значения, фактически извлеченных в `ptrs`.  
  
 `ptrs`  
 Указатель на начальный адрес массива `CORDB_ADDRESS` значений, содержащих адреса кэшированных объектов интерфейса.  
  
## <a name="remarks"></a>Примечания  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugComObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
