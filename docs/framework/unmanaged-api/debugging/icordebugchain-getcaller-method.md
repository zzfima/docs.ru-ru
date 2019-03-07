---
title: Метод ICorDebugChain::GetCaller
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd65de77209f5a981c0a4c291f8573a61cf6335b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489557"
---
# <a name="icordebugchaingetcaller-method"></a>Метод ICorDebugChain::GetCaller
Получает цепочку, вызвавшей эту цепочку.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppChain`  
 [out] Указатель на адрес ICorDebugChain объект, представляющий цепочки вызовов.  
  
 Если эта цепочка была вызвана спонтанно (как можно добиться, если эта цепочка или отладчик инициализирован стека вызовов), `ppChain` будет иметь значение null.  
  
## <a name="remarks"></a>Примечания  
 Если вызов был маршалирован в потоки, цепочки вызовов возможно в другом потоке.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
