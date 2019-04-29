---
title: Метод ICorDebugEval::GetResult
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8e7fcb4f44d6bdf6f18c93b1046b549331621a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667123"
---
# <a name="icordebugevalgetresult-method"></a>Метод ICorDebugEval::GetResult
Получает результаты этой оценки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppResult`  
 [out] Указатель на адрес объекта ICorDebugValue, представляющий результаты этой оценки, если оценка.  
  
## <a name="remarks"></a>Примечания  
 `GetResult` Метод допустим только в том случае, после завершения оценки.  
  
 Если оценка обычно `ppResult` указывает результаты. Если он завершается с исключением, результатом является исключение. Если оценка выполнялась для нового объекта, результатом является ссылка на новый объект.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
