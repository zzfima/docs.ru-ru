---
title: Метод ICorDebugGenericValue::GetValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::GetValue
helpviewer_keywords:
- ICorDebugGenericValue::GetValue method [.NET Framework debugging]
- GetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: 4e95d7cb-144d-4ccf-8a69-d605f4744be2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53db4dcb13303c9e7bdd77a46b3c9526364bac06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995649"
---
# <a name="icordebuggenericvaluegetvalue-method"></a>Метод ICorDebugGenericValue::GetValue
Значение этого универсального копируется в указанный буфер.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pTo`  
 [out] Указатель на значение, представленное этим объектом ICorDebugGenericValue. Значение может быть простым типом или ссылочным типом (то есть указатель).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
