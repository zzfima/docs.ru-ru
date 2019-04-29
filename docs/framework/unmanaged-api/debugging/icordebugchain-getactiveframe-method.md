---
title: Метод ICorDebugChain::GetActiveFrame
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c14b48a29993a65a0a0ab9fcb63bcb1e0d882042
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645374"
---
# <a name="icordebugchaingetactiveframe-method"></a>Метод ICorDebugChain::GetActiveFrame
Получает активный (то есть самой последней) кадра в цепочке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppFrame`  
 [out] Указатель на адрес ICorDebugFrame объект, представляющий активный (то есть самой последней) кадра в цепочке.  
  
## <a name="remarks"></a>Примечания  
 Если нет кадров управляемого стека, `ppFrame` задано значение null.  
  
 Если активная рамка не доступен, вызов будет успешным и `ppFrame` будет иметь значение null. Активные кадры будет недоступен для цепочек, инициирована из-за CHAIN_ENTER_UNMANAGED, а также для некоторых цепей, инициированных из-за CHAIN_CLASS_INIT. См. в разделе перечисление CorDebugChainReason.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
