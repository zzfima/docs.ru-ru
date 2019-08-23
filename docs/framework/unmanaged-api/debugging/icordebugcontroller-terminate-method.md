---
title: Метод ICorDebugController::Terminate
ms.date: 03/30/2017
api_name:
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee1c30809567097e67b6b1e40f5534429d748abd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964371"
---
# <a name="icordebugcontrollerterminate-method"></a>Метод ICorDebugController::Terminate
Завершает процесс с указанным кодом выхода.  
  
> [!NOTE]
> Этот метод является оболочкой для функции Win32 `TerminateProcess` . Таким образом `Terminate` , использует код выхода точно так же, как функция Win32 `TerminateProcess` использует ее.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `exitCode`  
 окне Числовое значение, которое является кодом выхода. Допустимые числовые значения определяются в Винбасе. h.  
  
## <a name="remarks"></a>Примечания  
 Если процесс останавливается при `Terminate` вызове, процесс должен быть продолжен с помощью метода [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) , чтобы отладчик получал подтверждение завершения с помощью [ICorDebugManagedCallback:: ](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)Обратный вызов ExitProcess или [ICorDebugManagedCallback:: ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) .  
  
> [!NOTE]
> Этот метод не реализуется доменом приложения. Это значит, что он не реализован на <xref:System.AppDomain> уровне.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
