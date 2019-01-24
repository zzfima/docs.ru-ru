---
title: Метод ICorDebugRegisterSet::GetRegisters
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee56a7f343de999d68a71d9eac04eed6e06b444e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568898"
---
# <a name="icordebugregistersetgetregisters-method"></a>Метод ICorDebugRegisterSet::GetRegisters
Получает значение каждого из регистров (на компьютере, на который в данный момент выполняется код), который указан битовой маской.  
  
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
 [in] Битовую маску, которая указывает, зарегистрируйтесь, какие значения должны быть получены. Каждый бит соответствует регистру. Если немного присваивается одно, извлекается значение регистра; в противном случае значение регистра не извлекается.  
  
 `regCount`  
 [in] Количество значений регистров требуется получить.  
  
 `regBuffer`  
 [out] Массив `CORDB_REGISTER` объектов, каждый из которых получает значение регистра.  
  
## <a name="remarks"></a>Примечания  
 Размер массива должно быть равно числу битов на один в битовой маске. `regCount` Параметр указывает число элементов в буфер для получения значений регистров. Если `regCount` значение слишком мал для числа регистрами, указанными в маске, регистры с более будет усечено из набора. Если `regCount` значение слишком велико, неиспользуемые `regBuffer` элементы будут изменены.  
  
 Если битовая маска указывает регистр, который недоступен, `GetRegisters` возвращает неопределенное значение для этого регистра.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [Интерфейс ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
