---
title: Метод ICorDebugObjectValue::IsValueClass
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.IsValueClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::IsValueClass
helpviewer_keywords:
- ICorDebugObjectValue::IsValueClass method [.NET Framework debugging]
- IsValueClass method [.NET Framework debugging]
ms.assetid: 13d89a4a-5d9d-4a79-9600-5e2a98c3d166
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12ba95eca2a103cffa07247a6ce474263e42e5ad
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487529"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a>Метод ICorDebugObjectValue::IsValueClass
Получает значение, указывающее, является ли значение этого объекта является типом значения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbIsValueClass`  
 [out] Указатель на логическое значение, которое является `true` Если значение объекта, представленного этот «ICorDebugObjectValue» является типом значения, а не ссылочный тип; в противном случае `pbIsValueClass` является `false`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также


