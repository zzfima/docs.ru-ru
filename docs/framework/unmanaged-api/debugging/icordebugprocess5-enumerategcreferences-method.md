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
ms.openlocfilehash: 2b5f66099eb4b1cb84d9911567cac4255bf20480
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocess5enumerategcreferences-method"></a>Метод ICorDebugProcess5::EnumerateGCReferences
Возвращает перечислитель для всех объектов, которые должны быть мусора в процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `enumerateWeakReferences`  
 [in] Логическое значение, указывающее, является ли слабые ссылки также перечисления. Если `enumerateWeakReferences` — `true`, `ppEnum` перечислитель включает строгих ссылок и слабых ссылок. Если `enumerateWeakReferences` — `false`, перечислитель включает только строгих ссылок.  
  
 `ppEnum`  
 [out] Указатель на адрес [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) , перечислитель для объектов для сбора мусора.  
  
## <a name="remarks"></a>Примечания  
 Этот метод позволяет определить полную цепочку корня для любого управляемого объекта в процессе и можно использовать, чтобы определить, почему объект все еще существует.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
