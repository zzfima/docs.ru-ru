---
title: Метод ICorDebugFunction2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15b102be5a792f982edeb320199576bdddbd859a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugfunction2setjmcstatus-method"></a>Метод ICorDebugFunction2::SetJMCStatus
Обозначает функцию, представленную в этом ICorDebugFunction2 только мой код пошаговое выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `bIsJustMyCode`  
 [in] Значение `true` пометить ее как код пользователя; в противном случае — значение `false`.  
  
## <a name="return-values"></a>Возвращаемые значения  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|Функция была успешно отмечена.|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|Функция не может быть помечена как код пользователя, так как он не может быть отлажен.|  
  
## <a name="remarks"></a>Примечания  
 Пошаговым только мой код будет пропускать код, не написанный пользователем. Пользовательский код должен быть подмножеством отлаживаемого кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
