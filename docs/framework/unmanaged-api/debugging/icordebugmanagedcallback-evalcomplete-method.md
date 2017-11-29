---
title: "Метод ICorDebugManagedCallback::EvalComplete"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.EvalComplete
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::EvalComplete
helpviewer_keywords:
- ICorDebugManagedCallback::EvalComplete method [.NET Framework debugging]
- EvalComplete method [.NET Framework debugging]
ms.assetid: f74ab4eb-cd1b-407c-a66d-8ec0d85647f3
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6211a5f0038c6244f7732e0c0ba854aaa1e6092e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a>Метод ICorDebugManagedCallback::EvalComplete
Уведомляет отладчик о завершении вычисления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pAppDomain`  
 [in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в которой была выполнена оценка.  
  
 `pThread`  
 [in] Указатель на объект ICorDebugThread, представляющий поток, в которой была выполнена оценка.  
  
 `pEval`  
 [in] Указатель на объект ICorDebugEval, который представляет код, который выполняется вычисление.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICorDebugManagedCallback-интерфейс](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
