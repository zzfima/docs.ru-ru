---
title: Метод ICorDebugProcess::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c137a10d5da94d04509385fc97d71535d33fae93
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758739"
---
# <a name="icordebugprocessgetthreadcontext-method"></a>Метод ICorDebugProcess::GetThreadContext
Получает контекст для данного потока в этом процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `threadID`  
 [in] Идентификатор потока, для которого требуется извлечь контекст.  
  
 `contextSize`  
 [in] Размер массива `context`.  
  
 `context`  
 [in, out] Массив байтов, описывающие контекст потока.  
  
 Контекст задает архитектуру процессора, на котором выполняется поток.  
  
## <a name="remarks"></a>Примечания  
 Отладчик должен вызвать этот метод вместо Win32 `GetThreadContext` метод, так как фактически поток может находиться в состоянии «перехваченного», в котором его контекст был временно изменен. Этот метод должен использоваться только в том случае, когда поток находится в машинном коде. Используйте [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) для потоков в управляемом коде.  
  
 Возвращаемые данные — это структура контекст для текущей платформы. Как и в случае с Win32 `GetThreadContext` метод, вызывающий объект должен инициализировать `context` параметра перед вызовом этого метода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
