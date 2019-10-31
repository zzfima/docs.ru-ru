---
title: Метод ICorDebugModule2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type:
- apiref
ms.openlocfilehash: a0b70078dee88b270d8361aa9bddcb7d80df1db1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129473"
---
# <a name="icordebugmodule2setjmcstatus-method"></a>Метод ICorDebugModule2::SetJMCStatus
Задает для состояния Только мой код (JMC) всех методов всех классов в этом ICorDebugModule2 указанное значение, за исключением тех, которые заданы в массиве `pTokens`, для которого задается противоположное значение.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `bIsJustMycode`  
 окне Задайте значение `true`, если код должен быть отлажен. в противном случае задайте значение `false`.  
  
 `cTokens`  
 [in] Размер массива `pTokens`.  
  
 `pTokens`  
 окне Массив значений `mdToken`, каждый из которых ссылается на метод, для которого в качестве его состояния JMC задано значение!`bIsJustMycode`.  
  
## <a name="remarks"></a>Заметки  
 JMC состояние каждого метода, указанного в массиве `pTokens`, имеет значение, противоположное значению `bIsJustMycode`. Состояние всех остальных методов в этом модуле задается как значение `bIsJustMycode`.  
  
 Метод `SetJMCStatus` удаляет все предыдущие параметры JMC в этом модуле.  
  
 Метод `SetJMCStatus` возвращает значение S_OK HRESULT, если все функции заданы успешно. Он возвращает значение HRESULT CORDBG_E_FUNCTION_NOT_DEBUGGABLE, если некоторые функции, помеченные `true`, не могут быть отлажены.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
