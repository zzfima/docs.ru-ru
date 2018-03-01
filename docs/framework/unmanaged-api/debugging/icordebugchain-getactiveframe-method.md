---
title: "Метод ICorDebugChain::GetActiveFrame"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7498e031b74bd904b908342b663e4421432e6d95
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchaingetactiveframe-method"></a>Метод ICorDebugChain::GetActiveFrame
Получает активный (то есть последней) кадра в цепочке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppFrame`  
 [out] Указатель на адрес объекта ICorDebugFrame, представляющий активный (то есть самые последние) кадра в цепочке.  
  
## <a name="remarks"></a>Примечания  
 Если не управляемый кадр стека, `ppFrame` задано значение null.  
  
 Если активная рамка не доступен, то вызов завершится успешно и `ppFrame` будет иметь значение null. Активные кадры не будет доступен для запуска из-за CHAIN_ENTER_UNMANAGED цепочек, а также для некоторых цепей, инициированных из-за CHAIN_CLASS_INIT. См. Перечисление CorDebugChainReason.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
