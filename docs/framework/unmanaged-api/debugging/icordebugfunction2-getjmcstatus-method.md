---
title: Метод ICorDebugFunction2::GetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d23a0a489cfe13201b7798920feb3528db3b0709
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988667"
---
# <a name="icordebugfunction2getjmcstatus-method"></a>Метод ICorDebugFunction2::GetJMCStatus
Получает значение, указывающее, отмечена ли функция, представляемая этим объектом ICorDebugFunction2 как пользовательский код.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbIsJustMyCode`  
 [out] Указатель на логическое значение, которое является `true`, если эта функция помечается как код пользователя; в противном случае значение равно `false`.  
  
## <a name="remarks"></a>Примечания  
 Если функция, представленный данным `ICorDebugFunction2` невозможна, `pbIsJustMyCode` всегда будет `false`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
