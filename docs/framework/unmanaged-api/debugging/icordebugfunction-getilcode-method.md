---
title: Метод ICorDebugFunction::GetILCode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f34a2fe2bb1f92e75f77c086b03776ec59495600
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482110"
---
# <a name="icordebugfunctiongetilcode-method"></a>Метод ICorDebugFunction::GetILCode
Получает экземпляр ICorDebugCode, представляющее код промежуточного языка MSIL Microsoft, связанного с данным объектом ICorDebugFunction.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppCode`  
 [out] Указатель на `ICorDebugCode` экземпляра, или значение null, если функция не была скомпилирована в MSIL.  
  
## <a name="remarks"></a>Примечания  
 Если изменить и продолжить была разрешена в этой функции `GetILCode` метод получит код MSIL, соответствующий этой функции измененная версия кода в системе common language runtime (CLR).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
