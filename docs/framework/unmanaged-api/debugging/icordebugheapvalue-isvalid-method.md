---
title: Метод ICorDebugHeapValue::IsValid
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e1edb1d25a62a9a689c397339740e563d986c8b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478769"
---
# <a name="icordebugheapvalueisvalid-method"></a>Метод ICorDebugHeapValue::IsValid
Получает значение, указывающее, является ли допустимым объект, представленный этой ICorDebugHeapValue.  
  
 Этот метод был объявлен устаревшим в .NET Framework версии 2.0.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbValid`  
 [out] Указатель на логическое значение, указывающее, допустим ли это значение в куче.  
  
## <a name="remarks"></a>Примечания  
 Значение является недопустимым, если удален сборщиком мусора.  
  
 Этот метод использовать не рекомендуется. В .NET Framework 2.0, все значения являются действительными до [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) вызывается во время которого значения становятся недействительными.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
