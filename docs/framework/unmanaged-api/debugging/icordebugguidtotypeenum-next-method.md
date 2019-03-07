---
title: Метод ICorDebugGuidToTypeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65eec8deb80caa017cb82b2c00a1f38ae487ae4d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489976"
---
# <a name="icordebugguidtotypeenumnext-method"></a>Метод ICorDebugGuidToTypeEnum::Next
Возвращает заданное число [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) экземпляров, которые сопоставляют идентификаторов GUID, чтобы сведения о типе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `celt`  
 [in] Число получаемых объектов сопоставления типа GUID.  
  
 `values`  
 [out] Массив указателей, каждый из которых указывает [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) объекта, сопоставляющего [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID для соответствующего объекта ICorDebugType.  
  
 `pceltFetched`  
 [out] Указатель на число [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) объектов, фактически возвращенных в `values`.  
  
## <a name="remarks"></a>Примечания  
  
## <a name="requirements"></a>Требования  
 **Платформы:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
