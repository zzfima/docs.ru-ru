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
ms.openlocfilehash: 5d28af09faae84b0482d438ae33f593f250490c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73196337"
---
# <a name="icordebugchaingetcallee-method"></a>Метод ICorDebugChain::GetCallee
Возвращает цепочку, вызванную этой цепочкой.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppChain`  
 заполняет Указатель на адрес объекта ICorDebugChain, который представляет вызываемую цепочку. Если эта цепочка выполняется в данный момент (то есть если эта цепочка не ожидает возврата вызванной цепочки), `ppChain` будет иметь значение null.  
  
## <a name="remarks"></a>Заметки  
 Эта цепочка будет ожидать возврата вызванной цепочки перед возобновлением выполнения. Вызываемая цепочка может находиться в другом потоке в случае маршалинга вызовов между потоками.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
