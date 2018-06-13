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
ms.openlocfilehash: acffd24ae9d5aad5f48058eec036f912ee016289
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415988"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a>Метод ICorDebugModule::GetFunctionFromToken
Возвращает функцию, которая указывается токеном метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `methodDef`  
 [in] Объект `mdMethodDef` токен метаданных, который ссылается на функции метаданных.  
  
 `ppFunction`  
 [out] Указатель на адрес объекта интерфейса ICorDebugFunction, представляющим функцию.  
  
## <a name="remarks"></a>Примечания  
 `GetFunctionFromToken` Метод возвращает CORDBG_E_FUNCTION_NOT_IL HRESULT, если значение, переданное в `methodDef` не ссылается на метод Microsoft промежуточного языка MSIL.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
