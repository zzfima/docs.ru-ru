---
title: "Метод ICorDebugProcess::SetThreadContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugProcess.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a7d40d455ea17b8df2acd77a1222ac6b080116c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocesssetthreadcontext-method"></a>Метод ICorDebugProcess::SetThreadContext
Задает контекст для данного потока в этом процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 `threadID`  
 [in] Идентификатор потока, для которого требуется задать контекст.  
  
 `contextSize`  
 [in] Размер массива `context`.  
  
 `context`  
 [in] Массив байтов, описывающие контекст потока.  
  
 Контекст задает архитектуру процессора, на котором выполняется поток.  
  
## <a name="remarks"></a>Примечания  
 Отладчик должен вызвать этот метод вместо Win32 `SetThreadContext` работать, поскольку фактически поток может находиться в состоянии «крадеными», в котором его контекст был временно изменен. Этот метод следует использовать только в том случае, когда поток находится в машинном коде. Используйте [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) для потоков в управляемом коде. Никогда не требуется изменить контекст потока во время события отладки по каналу (OOB).  
  
 Переданные данные должны быть структурой контекста для текущей платформы.  
  
 Этот метод может привести к повреждению среды выполнения при неправильном.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
