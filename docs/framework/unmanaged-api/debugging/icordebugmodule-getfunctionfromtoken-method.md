---
title: Метод ICorDebugModule::GetFunctionFromToken
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetFunctionFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromToken
helpviewer_keywords:
- GetFunctionFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromToken method [.NET Framework debugging]
ms.assetid: 6fe12194-4ef7-43c1-9570-ade35ccf127a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 547986633172d6f5e6549ad2048833dc9fb0cef3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763465"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a>Метод ICorDebugModule::GetFunctionFromToken
Возвращает функцию, которое определяется токеном метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `methodDef`  
 [in] Объект `mdMethodDef` токен метаданных, который ссылается на метаданные функции.  
  
 `ppFunction`  
 [out] Указатель на адрес объекта интерфейса ICorDebugFunction, представляющий функцию.  
  
## <a name="remarks"></a>Примечания  
 `GetFunctionFromToken` Метод возвращает CORDBG_E_FUNCTION_NOT_IL HRESULT, если значение, переданное в `methodDef` не ссылается на метод Microsoft промежуточного языка MSIL.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
