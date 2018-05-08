---
title: Метод ICorDebugThread::GetActiveFrame
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a1bbe5674ba11b5ee6033c65f229d698eff15ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugthreadgetactiveframe-method"></a>Метод ICorDebugThread::GetActiveFrame
Получает указатель интерфейса на этот объект ICorDebugThread активного кадра (последней).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppFrame`  
 [out] Указатель на адрес объекта интерфейса ICorDebugFrame, который представляет кадр.  
  
## <a name="remarks"></a>Примечания  
 `ppFrame` Параметр имеет значение null, если нет рамка в данный момент активна.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
