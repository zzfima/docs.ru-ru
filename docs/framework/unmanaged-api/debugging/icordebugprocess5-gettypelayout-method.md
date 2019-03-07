---
title: Метод ICorDebugProcess5::GetTypeLayout
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffef0b7296e2742d6e6207f66f91273f41652469
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57483762"
---
# <a name="icordebugprocess5gettypelayout-method"></a>Метод ICorDebugProcess5::GetTypeLayout
Получает сведения о расположении объекта в памяти, на основе его идентификатора типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a>Параметры  
 `id`  
 [in] Объект [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) маркер, указывающий тип требуемого, макет.  
  
 `pLayout`  
 [out] Указатель на [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) структуру, содержащую сведения о расположении объекта в памяти.  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugProcess5::GetTypeLayout` Метод предоставляет сведения об объекте на основе его [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), который возвращается количество других [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) методы. Информация предоставляется по [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) структуру, которая заполняется с помощью метода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Структура COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)
- [Интерфейс ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
