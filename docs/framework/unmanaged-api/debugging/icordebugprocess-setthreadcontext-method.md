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
ms.openlocfilehash: 3c57021061c1566b369cdd43847e3994cf54e2da
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139675"
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
 окне Идентификатор потока, для которого задается контекст.  
  
 `contextSize`  
 [in] Размер массива `context`.  
  
 `context`  
 окне Массив байтов, описывающих контекст потока.  
  
 Контекст указывает архитектуру процессора, на котором работает поток.  
  
## <a name="remarks"></a>Заметки  
 Отладчик должен вызывать этот метод вместо функции Win32 `SetThreadContext`, так как поток может находиться в состоянии "перехвачено", в котором его контекст был временно изменен. Этот метод следует использовать только в том случае, если поток находится в машинном коде. Используйте [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) для потоков в управляемом коде. Никогда не нужно изменять контекст потока во время события нестандартного управления (OOB).  
  
 Передаваемые данные должны быть структурой контекста для текущей платформы.  
  
 Этот метод может повредить среду выполнения при неправильном использовании.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
