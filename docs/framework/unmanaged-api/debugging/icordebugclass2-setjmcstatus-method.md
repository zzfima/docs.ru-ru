---
title: Метод ICorDebugClass2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23f248625753c15a4798ea69a1eb3b377b79f95d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747751"
---
# <a name="icordebugclass2setjmcstatus-method"></a>Метод ICorDebugClass2::SetJMCStatus
Для каждого метода класса задает значение, указывающее, является ли метод определяемого пользователем кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `bIsJustMyCode`  
 [in] Значение `true` для указания, что метод определяется пользователем кода; в противном случае — значение `false`.  
  
## <a name="remarks"></a>Примечания  
 Только мой код (JMC) несопоставимого пропустит не пользовательский код. Пользовательский код должен представлять собой подмножество отлаживаемый код.  
  
 `SetJMCStatus` Возвращает значение HRESULT S_FALSE, если не удается задать значение для любого метода, даже если он успешно устанавливает значение для всех других методов.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
