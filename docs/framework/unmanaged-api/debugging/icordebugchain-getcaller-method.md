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
ms.openlocfilehash: 1a0b5d702e9718ce6ac537beae67fc190b152b9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugchaingetcaller-method"></a>Метод ICorDebugChain::GetCaller
Получает цепь, вызвавшую данную цепь.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppChain`  
 [out] Указатель на адрес объекта ICorDebugChain, который представляет цепочки вызовов.  
  
 Если эта цепь была вызвана спонтанно (как это может произойти, если эта цепочка или отладчиком инициализирован стек вызовов), `ppChain` будет иметь значение null.  
  
## <a name="remarks"></a>Примечания  
 Цепочки вызовов может быть в другом потоке, если вызов был маршалинг между потоками.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
