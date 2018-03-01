---
title: "Метод ICorDebugRegisterSet::GetRegisters"
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
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ddefb1ac5694bf1f213dd77e0ffc7f746b7e62cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregistersetgetregisters-method"></a>Метод ICorDebugRegisterSet::GetRegisters
Получает значение каждого регистра (на компьютере, который в данный момент выполняется код), который указан битовой маской.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `mask`  
 [in] Битовая маска, указывающая регистра, какие значения должны быть получены. Каждый бит соответствует регистру. Если бит присваивается одно, извлекается значение регистра; в противном случае — значение регистра не извлекается.  
  
 `regCount`  
 [in] Количество значений регистра требуется получить.  
  
 `regBuffer`  
 [out] Массив `CORDB_REGISTER` объектов, каждый из которых получает значение регистра.  
  
## <a name="remarks"></a>Примечания  
 Размер массива должно быть равно числу битов, значение в битовой маске. `regCount` Указывает количество элементов в буфере, которые будут получать значения регистра. Если `regCount` значение слишком мало для количества регистров, указанного маской, регистры с более будут отброшены из набора. Если `regCount` значение слишком велико, неиспользуемые `regBuffer` элементы будут изменены.  
  
 Если битовая маска указывает недоступный регистр, `GetRegisters` возвращает неопределенное значение для данного регистра.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [Интерфейс ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
