---
title: Метод ICorDebugType::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd68df77adafb8b21e7684b28fe978722ca37e16
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736794"
---
# <a name="icordebugtypegetclass-method"></a>Метод ICorDebugType::GetClass
Получает указатель на интерфейс ICorDebugClass, представляющий универсального типа без экземпляров.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppClass`  
 [out] Указатель на адрес `ICorDebugClass` интерфейс, который представляет универсального типа без экземпляров.  
  
## <a name="remarks"></a>Примечания  
 `GetClass` может вызываться только при определенных условиях. Вызовите [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) перед вызовом `GetClass`. Если `ICorDebugType::GetType` возвращает значение CorElementType ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, `GetClass` может вызываться для получения типа без экземпляров для универсального типа.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
