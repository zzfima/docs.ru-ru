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
ms.openlocfilehash: 41c5116d23655730f3586dc656aa69c8ae817b6c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792625"
---
# <a name="icordebugprocessgetthreadcontext-method"></a>Метод ICorDebugProcess::GetThreadContext
Возвращает контекст для данного потока в этом процессе.  
  
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
 окне Идентификатор потока, для которого извлекается контекст.  
  
 `contextSize`  
 [in] Размер массива `context`.  
  
 `context`  
 [вход, выход] Массив байтов, описывающих контекст потока.  
  
 Контекст указывает архитектуру процессора, на котором работает поток.  
  
## <a name="remarks"></a>Заметки  
 Отладчик должен вызывать этот метод вместо метода `GetThreadContext` Win32, так как поток может находиться в состоянии "перехвачено", в котором его контекст был временно изменен. Этот метод следует использовать только в том случае, если поток находится в машинном коде. Используйте [ICorDebugRegisterSet](icordebugregisterset-interface.md) для потоков в управляемом коде.  
  
 Возвращаемые данные — это структура контекста для текущей платформы. Как и в случае с методом `GetThreadContext` Win32, вызывающий объект должен инициализировать параметр `context` перед вызовом этого метода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
