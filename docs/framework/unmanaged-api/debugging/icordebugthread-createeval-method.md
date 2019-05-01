---
title: Метод ICorDebugThread::CreateEval
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2016795e7b2c0588e2bd69e764fb96f7f90b24d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994075"
---
# <a name="icordebugthreadcreateeval-method"></a>Метод ICorDebugThread::CreateEval
Создает объект ICorDebugEval, которая собирает и предоставляет функциональные возможности ICorDebugThread.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppEval`  
 [out] Указатель на адрес `ICorDebugEval` объект, который собирает и предоставляет функциональные возможности для данного потока.  
  
## <a name="remarks"></a>Примечания  
 Объект выполнения будет отправлять новую цепочку в потоке перед выполнением этого вычисления. Это прервет вычисления, в данный момент выполняется в потоке до завершения оценки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
