---
title: Метод ICorDebugController::Detach
ms.date: 03/30/2017
api_name:
- ICorDebugController.Detach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85a9bde77f7c393756ec1d3e7d30b96392aa6a94
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749635"
---
# <a name="icordebugcontrollerdetach-method"></a>Метод ICorDebugController::Detach
Отключает отладчик от процесса или домена приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a>Примечания  
 Процесса или домена приложения продолжит выполнение, как правило, но объект «ICorDebugProcess» или «ICorDebugAppDomain» больше не является допустимым и обратные вызовы не произойдет.  
  
 В .NET Framework версии 2.0 Если включена отладка неуправляемого кода, этот метод завершится ошибкой из-за ограничений операционных систем.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
