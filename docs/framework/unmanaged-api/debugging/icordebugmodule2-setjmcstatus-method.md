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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a56b5c31c26dbe5c5371fdb7a10c13ad11847117
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmodule2setjmcstatus-method"></a>Метод ICorDebugModule2::SetJMCStatus
Задает состояние "только мой код (") все методы для всех классов в этом ICorDebugModule2 указанное значение, за исключением тех, в `pTokens` массив, который задает его значение с противоположным.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `bIsJustMycode`  
 [in] Значение `true` при код отладки; в противном случае значение `false`.  
  
 `cTokens`  
 [in] Размер массива `pTokens`.  
  
 `pTokens`  
 [in] Массив `mdToken` значений, каждое из которых ссылается на метод, который будет в состоянии его JMC!`bIsJustMycode`.  
  
## <a name="remarks"></a>Примечания  
 Состояние JMC каждого метода, указанного в `pTokens` массива равен противоположность `bIsJustMycode` значение. Присвоено состояние всех методов в этом модуле `bIsJustMycode` значение.  
  
 `SetJMCStatus` Метод удаляет все предыдущие настройки JMC в этом модуле.  
  
 `SetJMCStatus` Метод возвращает значение HRESULT S_OK, если все функции успешно установлено. Он возвращает HRESULT CORDBG_E_FUNCTION_NOT_DEBUGGABLE, если некоторые функции, помеченные `true` не являются доступными для отладки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
