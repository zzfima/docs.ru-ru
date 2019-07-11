---
title: Метод ICorDebugProcess2::ClearUnmanagedBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fb566ff2e5e2b0bcb096cead243ed65a904a914
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736977"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a>Метод ICorDebugProcess2::ClearUnmanagedBreakpoint
Удаляет ранее заданной точки останова по заданному адресу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `address`  
 [in] Объект `CORDB_ADDRESS` значение, указывающее адрес, по которому была задана точка останова.  
  
## <a name="remarks"></a>Примечания  
 Указанный точки останова будет ранее заданные предыдущим вызовом [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 `ClearUnmanagedBreakpoint` Метод может вызываться во время работы отлаживаемого процесса.  
  
 `ClearUnmanagedBreakpoint` Метод возвращает код ошибки, если присоединен отладчик в режиме только для управляемых или если точка останова не существует по указанному адресу.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
