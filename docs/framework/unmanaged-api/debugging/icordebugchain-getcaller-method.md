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
ms.openlocfilehash: 5a07550d44857526e8ab4ded9f1827ef12e3bba4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192136"
---
# <a name="icordebugchaingetcaller-method"></a>Метод ICorDebugChain::GetCaller
Возвращает цепочку, вызвавшую эту цепь.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppChain`  
 заполняет Указатель на адрес объекта ICorDebugChain, который представляет вызывающую цепочку.  
  
 Если эта цепочка была вызвана недостаточной (как в случае, если эта цепочка или отладчик инициализируют стек вызовов), `ppChain` будет иметь значение null.  
  
## <a name="remarks"></a>Заметки  
 Вызывающая цепочка может находиться в другом потоке, если вызов был маршалирован в потоках.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
