---
title: Метод ICorDebugProcess5::EnumerateGCReferences
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54e2648765d896c189cc2deb5590a0a2a9b3f410
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476491"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a>Метод ICorDebugProcess5::EnumerateGCReferences
Получает перечислитель для всех объектов, которые должны быть удалены сборщиком мусора в процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `enumerateWeakReferences`  
 [in] Логическое значение, указывающее ли слабые ссылки, которые необходимо перечислить. Если `enumerateWeakReferences` — `true`, `ppEnum` перечислитель включает строгих ссылок и слабых ссылок. Если `enumerateWeakReferences` является `false`, перечислитель включает только строгих ссылок.  
  
 `ppEnum`  
 [out] Указатель на адрес [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) то есть перечислитель для объектов мусора.  
  
## <a name="remarks"></a>Примечания  
 Этот метод позволяет определить полную цепочку корня для любого управляемого объекта в процессе и может использоваться, чтобы определить, почему объект все еще существует.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
