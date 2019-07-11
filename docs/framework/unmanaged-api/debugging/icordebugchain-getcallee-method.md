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
ms.openlocfilehash: 79743b78ea3d19bab4756b580d2feddd07e0a23b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744982"
---
# <a name="icordebugchaingetcallee-method"></a>Метод ICorDebugChain::GetCallee
Получает цепочку, вызванная этой цепочки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
