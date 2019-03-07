---
title: Метод ICorDebugChain::GetCallee
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed5a7657affde335acf79952d77bbdb7ac42c7a0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490467"
---
# <a name="icordebugchaingetcallee-method"></a>Метод ICorDebugChain::GetCallee
Получает цепочку, вызванная этой цепочки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppChain`  
 [out] Указатель на адрес ICorDebugChain объект, представляющий вызываемый цепочки. Если эта цепочка выполняемый в текущий момент (то есть, если эта цепочка не находится в состоянии для вызываемой цепочки для возврата), `ppChain` будет иметь значение null.  
  
## <a name="remarks"></a>Примечания  
 Эта цепочка будет ожидать, чтобы вернуть свое выполнение вызванной цепочка. Вызванная цепь может находиться в другом потоке, в случае маршалированного вызовы между потоками.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
