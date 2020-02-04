---
title: Метод ICorDebugRegisterSet::GetRegistersAvailable
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type:
- apiref
ms.openlocfilehash: b137b956e06a2b2954918e4024860f9b234e7583
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792097"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a>Метод ICorDebugRegisterSet::GetRegistersAvailable
Возвращает битовую маску, указывающую, какие регистры в этом [ICorDebugRegisterSet](icordebugregisterset-interface.md) в настоящее время доступны.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pAvailable`  
 заполняет Битовая маска, указывающая, какие регистры доступны в настоящее время.  
  
## <a name="remarks"></a>Заметки  
 Регистр может быть недоступен, если его значение не может быть определено для данной ситуации.  
  
 Возвращаемая маска содержит бит для каждого регистра (1 < < индексе регистра). Значение бита равно 1, если регистр доступен, или 0, если он недоступен.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugRegisterSet](icordebugregisterset-interface.md)
- [Интерфейс ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
