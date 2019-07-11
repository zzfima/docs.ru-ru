---
title: Метод ICorDebugProcess::SetThreadContext
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b949961e854facf8414c81c47f995b2ac57af3f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755384"
---
# <a name="icordebugprocesssetthreadcontext-method"></a>Метод ICorDebugProcess::SetThreadContext
Задает контекст для данного потока в этом процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `threadID`  
 [in] Идентификатор потока, для которого необходимо задать контекст.  
  
 `contextSize`  
 [in] Размер массива `context`.  
  
 `context`  
 [in] Массив байтов, описывающие контекст потока.  
  
 Контекст задает архитектуру процессора, на котором выполняется поток.  
  
## <a name="remarks"></a>Примечания  
 Отладчик должен вызвать этот метод вместо Win32 `SetThreadContext` работать, поскольку фактически поток может находиться в состоянии «перехваченного», в котором его контекст был временно изменен. Этот метод должен использоваться только в том случае, когда поток находится в машинном коде. Используйте [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) для потоков в управляемом коде. Никогда не требуется изменения контекста потока во время события отладки (OOB)-каналу.  
  
 Данные, передаваемые должно быть структурой контекст для текущей платформы.  
  
 Этот метод может привести к повреждению среды выполнения при неправильном.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
