---
title: Метод ICorDebugGenericValue::SetValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::SetValue
helpviewer_keywords:
- ICorDebugGenericValue::SetValue method [.NET Framework debugging]
- SetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: ed4c6458-0435-44fc-8e78-8ba00be362f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83aebad108a743d25b8ea93c99060d10bf5c3980
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebuggenericvaluesetvalue-method"></a>Метод ICorDebugGenericValue::SetValue
Копирует новое значение из указанного буфера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pFrom`  
 [in] Указатель на буфер, из которого необходимо скопировать значение.  
  
## <a name="remarks"></a>Примечания  
 Для ссылочных типов значение является ссылкой, не содержимое.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
