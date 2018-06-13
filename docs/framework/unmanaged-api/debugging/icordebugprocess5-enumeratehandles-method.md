---
title: Метод ICorDebugProcess5::EnumerateHandles
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f2177702c6c5999033d0852a932e52c0725fb8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422663"
---
# <a name="icordebugprocess5enumeratehandles-method"></a>Метод ICorDebugProcess5::EnumerateHandles
Возвращает перечислитель для маркеров объектов в процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
#### <a name="parameters"></a>Параметры  
 `types`  
 [in] Побитовое сочетание [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) значения, которое указывает тип маркеров для включения в коллекции.  
  
 `ppENum`  
 [out] Указатель на адрес [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) , перечислитель для объектов для сбора мусора.  
  
## <a name="remarks"></a>Примечания  
 `EnumerateHandles` является вспомогательная функция, которая поддерживает проверку таблицы дескрипторов. Это похоже на [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) метода, за исключением того, вместо того чтобы заполнение [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) коллекции со всеми объектами для сбора мусора, он включает только те объекты, которые имеют дескрипторы из таблицы дескрипторов.  
  
 `types` Параметр указывает типы дескрипторов для включения в коллекции. `types` может иметь любое из следующих трех возможных членов [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) перечисления:  
  
-   `CorHandleStrongOnly` (маркеры для строгих ссылок только).  
  
-   `CorHandleWeakOnly` (маркеры для только слабые ссылки).  
  
-   `CorHandleAll` (все дескрипторы).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
