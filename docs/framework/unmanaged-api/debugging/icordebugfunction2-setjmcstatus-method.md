---
title: "Метод ICorDebugFunction2::SetJMCStatus"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction2.SetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ecbcd5b8171a169fbfdd7175d3d9dfbbcb3855f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
